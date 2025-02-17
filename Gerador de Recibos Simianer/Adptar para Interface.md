## Fluxo:
- Configurar Aparência:
	```python
	ctk.set_appearence_mode('dark')
	```
- Criar Janela Principal :
```python
	app = ctk.Ctk()
	# Definindo Titulo
	app.title('Gerador de Recibos <Nome>')	
	# Definindo Dimensões
	app.geometry('widthXheight+Xpos+Ypos')
	# Setando ico Bitmap
	app.iconbitmap(bitmap=PATH_BIT_MAP)
```
- Setando Cores da Aperência:
```python
	# Label e Input CSS
	corner_radius = 8;
	width_label = 275;
	height_label = 35;
	font = "";
	# Label 
	anchor = "";
	color_font ="";
	# Input
	placeholder_color = "";\
	border_color="";
	border_width=2;
	fg_color="";
```
- Array para Labels e Inputs PlaceHolders
```python
	campos_input = ['Exemplo','Exemplo']
	campos_place = ['Exemplo_place','Exemplo_place']
``` 

### Campos Pillow 
```python
campos = {

"tipo_recibo": (900, 1576),

"valor_total": (888, 1749),

"valor_total_extenso": (1150, 1741),

"nome_recebedor": (673, 2005),

"cpf_recebedor": (1630, 2003),

"valor_importancia": (860, 2087),

"diarias": (1589, 2088),

"periodo": (810, 2175),

"n_apartamento": (1770, 2173),

"data_acrobat": (1630, 2752),

"data_acrobat2": (1450, 2910),

"data_acrobat3": (1449, 2955),

"codigo": (1978, 265)

}****
```