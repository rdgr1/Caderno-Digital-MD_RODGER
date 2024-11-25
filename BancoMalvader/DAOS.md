```java
package dao;

import model.Usuario;
import java.sql.*;

public class UsuarioDAO {

    public void inserirUsuario(Usuario usuario) throws SQLException {
        String sql = "INSERT INTO usuario (nome, cpf, data_nascimento, telefone, tipo_usuario, senha) VALUES (?, ?, ?, ?, ?, ?)";

        try (Connection conn = ConnectionFactory.getConnection();
             PreparedStatement stmt = conn.prepareStatement(sql, Statement.RETURN_GENERATED_KEYS)) {

            stmt.setString(1, usuario.getNome());
            stmt.setString(2, usuario.getCpf());
            stmt.setDate(3, Date.valueOf(usuario.getDataNascimento()));
            stmt.setString(4, usuario.getTelefone());
            stmt.setString(5, usuario.getTipoUsuario().toString());
            stmt.setString(6, usuario.getSenha());

            stmt.executeUpdate();
            try (ResultSet generatedKeys = stmt.getGeneratedKeys()) {
                if (generatedKeys.next()) {
                    usuario.setId(generatedKeys.getInt(1));
                }
            }
        }
    }

    public Usuario buscarUsuarioPorCpf(String cpf) throws SQLException {
        String sql = "SELECT * FROM usuario WHERE cpf = ?";
        Usuario usuario = null;

        try (Connection conn = ConnectionFactory.getConnection();
             PreparedStatement stmt = conn.prepareStatement(sql)) {

            stmt.setString(1, cpf);
            try (ResultSet rs = stmt.executeQuery()) {
                if (rs.next()) {
                    usuario = new Usuario(
                            rs.getInt("id_usuario"),
                            rs.getString("nome"),
                            rs.getString("cpf"),
                            rs.getDate("data_nascimento").toLocalDate(),
                            rs.getString("telefone"),
                            rs.getString("tipo_usuario"),
                            rs.getString("senha")
                    );
                }
            }
        }
        return usuario;
    }
    
    public void atualizarUsuario(Usuario usuario) throws SQLException {
        String sql = "UPDATE usuario SET nome = ?, data_nascimento = ?, telefone = ?, senha = ? WHERE id_usuario = ?";

        try (Connection conn = ConnectionFactory.getConnection();
             PreparedStatement stmt = conn.prepareStatement(sql)) {

            stmt.setString(1, usuario.getNome());
            stmt.setDate(2, Date.valueOf(usuario.getDataNascimento()));
            stmt.setString(3, usuario.getTelefone());
            stmt.setString(4, usuario.getSenha());
            stmt.setInt(5, usuario.getId());

            stmt.executeUpdate();
        }
    }
    
    public void deletarUsuario(int idUsuario) throws SQLException {
        String sql = "DELETE FROM usuario WHERE id_usuario = ?";

        try (Connection conn = ConnectionFactory.getConnection();
             PreparedStatement stmt = conn.prepareStatement(sql)) {

            stmt.setInt(1, idUsuario);
            stmt.executeUpdate();
        }
    }
}

```