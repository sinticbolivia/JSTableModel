# JSTableModel
A javascript library to handle html table data in a single way.
You can place info into table and serialize table data based on user entries.

# Usage Mode
The javascript class required jQuery, It was built using jQuery 2.x, i think it can works with old versions as well (not tested).

```
<div id="table-home"></div>
<script>
var model = {
	key_field: 'score_id',
	columns: [
		{
			label: 'HOME PLAYER', class:'', type:'select', value_key: 'idplayer', 
			options: [
				{text: 'Player 1', value:1},
				{text: 'Player 2', value:2},
				{text: 'Player 3', value:3}
			]
		},
		{label: 'TOTAL POINTS', class: '', type:'number', value_key: 'total_points'},
		{
			label: 'GAMES', class: '', type:'select', value_key: 'game_status',
			options: [
				{text: 'Wins', value:'wins'},
				{text: 'Lost', value:'lost'},
				{text: 'Not Played', value:'not_played'}
			]
		},
		{label: '10-0', class:'', type:'number',value_key:'ten_cero'},
		{label: 'ERO', class: '', type:'number', value_key: 'ero'},
		{label: '1st attempt', class: '', type:'number', value_key: 'first_attempt'},
	]
};
var table_home = new SBTableModel(model, document.getElementById('table-home'));
table_home.Build();
</script>
```
# Serializing Table Data
By default the Serialize method builds a JSON array with a object per row.
You can serialize table data into form-data by using

table.Serialize('form');

It will returns a forms like forma, so you can send it by using GET or POST method.
```
<script>
table_home.Serialize();
</script>
```
# Example
<img src="http://sinticbolivia.net/JSTableModel/Inventory-System-Edit-Purchase-Order.png" alt=""/><br/>
<b>Setting The Model</b>
```
var model = {
	"key_field":"product_hash",
	"columns":[
		{"label":"Num","class":"","type":"count"},	
		{"label":"ID","class":"","type":"static","value_key":"product_id","show":true},
		{"label":"Code","class":"","type":"static","value_key":"product_code"},
		{"label":"Product","class":"","type":"static","value_key":"product_name"},
		{"label":"Batch","class":"","type":"text","value_key":"batch_code"},
		{"label":"Expiration Date","class":"","type":"text","value_key":"expiration_date"},
		{"label":"Quantity","class":"","type":"number","value_key":"quantity"},
		{"label":"Price","class":"","type":"text","value_key":"supply_price"},
		{"label":"Discount","class":"","type":"text","value_key":"discount"},
		{"label":"Total","class":"","type":"static","value_key":"total"},
		{"label":"Actions","class":"","type":"buttons",
			"buttons":
			[
				{
					"label":"Remove",
					"callback":"mb_purchase.DeleteItem",
					"data":["product_id"]
				}
			]
		}
	],
	"OnAddItem":"mb_purchase.OnAddItem",
	"OnChange":"mb_purchase.OnChange"
};
```

The above table will return this result after call Serialize method

```
[ 
  {
    "item_id": 45, 
    "product_id": 819, 
    "order_id": 8, 
    "batch_id": null, 
    "batch_code": "", 
    "name": "Fenobarbital", 
    "quantity": 10, 
    "quantity_received": 0, 
    "supply_price": 20, 
    "subtotal": 200, 
    "tax_rate": null, 
    "total_tax": null, 
    "discount": 10, 
    "total": 190, 
    "r_subtotal": null, 
    "r_total_tax": null, 
    "r_total": null, 
    "status": "waiting_stock", 
    "expiration_date": "04-10-2017", 
    "last_modification_date": "2017-10-05 00:02:01", 
    "creation_date": "2017-10-05 00:02:01", 
    "product_code": "ELAB623", 
    "product_name": "Fenobarbital", 
    "product_hash": "819:ELAB623"
  },
  {
      "item_id": 46, 
    "product_id": 1114, 
    "order_id": 8, 
    "batch_id": null, 
    "batch_code": "", 
    "name": "Viadil compuesto", 
    "quantity": 50, 
    "quantity_received": 0, 
    "supply_price": 1.5, 
    "subtotal": 75, 
    "tax_rate": null, 
    "total_tax": null, 
    "discount": 0, 
    "total": 75, 
    "r_subtotal": null, 
    "r_total_tax": null, 
    "r_total": null, 
    "status": "waiting_stock", 
    "expiration_date": "10-10-2017", 
    "last_modification_date": "2017-10-05 00:02:01", 
    "creation_date": "2017-10-05 00:02:01", 
    "product_code": "ANVI01", 
    "product_name": "Viadil compuesto", 
    "product_hash": "1114:ANVI01"
  },
  {
      "item_id": 47, 
    "product_id": 1008, 
    "order_id": 8, 
    "batch_id": null, 
    "batch_code": "", 
    "name": "Administracion de Amoxicilina de 500 mg", 
    "quantity": 500, 
    "quantity_received": 0, 
    "supply_price": 0.5, 
    "subtotal": 250, "tax_rate": null, 
    "total_tax": null, 
    "discount": 0, 
    "total": 250, 
    "r_subtotal": null, 
    "r_total_tax": null, 
    "r_total": null, 
    "status": "waiting_stock", 
    "expiration_date": "22-10-2017", 
    "last_modification_date": "2017-10-05 00:02:01", 
    "creation_date": "2017-10-05 00:02:01", 
    "product_code": "ANBI2", 
    "product_name": "Administracion de Amoxicilina de 500 mg", 
    "product_hash": "1008:ANBI2"
  }

]
```
# About Author
I am a developer self motivated working as CEO on Sintic Bolivia company.<br/>
I like to work on OpenSource project to share my knowledge and useful tools built around all my expertise working on projects.<br/>

# Support
If you like this project, help me to support it by buying me a coffee.<br/>
Buy me a coffe by following the next link<br/>
<a href="https://paypal.me/sinticbolivia" style="text-align:center;">
	<img src="https://pics.paypal.com/00/p/Mjc5MDY5NjItYTBiYS00M2I1LThiZWItNGNjNmVjOGM5Y2U1/image_2.JPG" alt="" /><br/>
<img src="https://camo.githubusercontent.com/bb217cc672bb9b7ecffa9bcc75dd0d7a3776af53/687474703a2f2f6772617065736a732e636f6d2f696d672f70706d652e706e67" alt="PayPalMe" style="max-width:100%;"><br/>
	Buy me a coffee
</a>
