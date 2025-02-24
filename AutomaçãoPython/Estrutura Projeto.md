**1. Visão Geral do Projeto**

**Objetivo:**

Desenvolver uma automação em Python para extrair dados financeiros específicos de um PDF que contenha o DRE e o Balancete, mapeando esses valores para planilhas pré-formatadas. É fundamental que a atualização seja feita somente para o mês corrente, preservando os dados dos meses anteriores e mantendo a integridade das fórmulas e cálculos já existentes.

**2. Dados a Serem Extraídos**

Os dados devem ser extraídos e inseridos conforme os seguintes indicadores:

• **Q1 - Receita/Faturamento:**

• Receita líquida, operacional e bruta (DRE) – valor acumulado desde 09/2020 até o mês atual.

• **Q2 - Receita vs Custos:**

• Valores extraídos diretamente do DRE.

• **Q3 - Despesas Totais:**

• Valor final extraído do DRE.

• **Q4 - Receita Operacional:**

• Dados provenientes tanto do DRE quanto do Balancete.

• **Q5 - Liquidez Imediata:**

• Ativo disponível e passivo circulante (Balancete).

• **Q6 - Liquidez Corrente:**

• Comparação entre ativo circulante e passivo circulante (Balancete).

• **Q7 - Liquidez Geral:**

• Soma de ativo circulante e realizável a longo prazo versus soma de passivo circulante e não circulante (Balancete).

• **Q8 - Endividamento:**

• Relação entre capital de terceiros (passivo - PL) e ativo total (Balancete).

• **Q9 - Composição do Endividamento:**

• Proporção de passivo circulante em relação ao passivo total (Balancete).

• **Q10 - Garantia Capital de Terceiros:**

• Patrimônio líquido, passivo circulante e passivo não circulante (Balancete).

**3. Regras e Restrições da Automação**

1. **Não sobrescrever dados anteriores:**

Cada mês deve manter seus dados históricos intactos.

2. **Atualização apenas do mês corrente:**

O script deve identificar a posição correta na planilha e inserir somente os valores referentes ao mês atual.

1. **Preservação da estrutura:**

As fórmulas e o layout das planilhas pré-formatadas não podem ser alterados.

2. **Mapeamento correto dos dados:**

É essencial que a automação encontre com precisão os campos no PDF e os vincule às células correspondentes na planilha.

3. **Extração dos totais:**

Apenas os valores finais dos indicadores devem ser copiados, evitando a transferência de linhas com informações detalhadas.

**4. Tecnologias e Bibliotecas Recomendadas**


**Leitura e Processamento de PDF:**

• **pdfplumber:**

Excelente para extrair tabelas e textos de PDFs, facilitando a identificação dos quadros no DRE e Balancete.

• **PyMuPDF (fitz) ou pdfminer.six:**

Alternativas para casos em que seja necessário um controle mais refinado sobre o layout.

  

**Manipulação de Planilhas:**

• **pandas:**

Útil para estruturar e manipular os dados extraídos antes da inserção.

• **openpyxl:**

Ideal para manipular planilhas Excel, possibilitando a atualização de células sem afetar as fórmulas.

• **xlwings:**

Para interação direta com o Excel, se houver necessidade de manter cálculos dinâmicos ou realizar operações em tempo real.

  

**Outras Tecnologias:**

• **Python:**

Linguagem principal para implementar a lógica de extração e automação.

• **NumPy:**

Pode ser utilizado para operações matemáticas e financeiras, se necessário.

• **SQLAlchemy:**

Caso haja a necessidade de armazenamento temporário ou consulta a dados extraídos.

  

**Extras:**

• **Streamlit ou Flask:**

Se for necessário desenvolver uma interface gráfica para upload do PDF e monitoramento do processo.

• **Google Sheets API:**

Para integração com planilhas online, caso o ambiente de trabalho seja baseado em nuvem.

**5. Fluxo de Automação Proposto**

4. **Leitura do PDF:**

• Utilizar **pdfplumber** ou **PyMuPDF** para identificar e extrair as seções referentes ao DRE e Balancete.

• Desenvolver um parser que localize os quadros e identifique os valores finais dos indicadores.

5. **Processamento dos Dados:**

• Mapear os valores extraídos para cada indicador (Q1 a Q10).

• Se necessário, realizar somas acumuladas (como em Q1) e cálculos comparativos (liquidez, endividamento, etc.).

6. **Atualização da Planilha:**

• Carregar a planilha pré-formatada usando **pandas** e **openpyxl** ou **xlwings**.

• Identificar a coluna referente ao mês corrente, garantindo que os dados anteriores permaneçam inalterados.

• Inserir os dados extraídos apenas na posição correta e nos campos designados.

7. **Validação e Integridade:**

• Após a inserção, validar se os valores foram corretamente mapeados.

• Certificar-se de que as fórmulas e a estrutura da planilha não foram comprometidas durante o processo.

