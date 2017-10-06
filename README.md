# JSTableModel
A javascript library to handle html table data in a single way.
You can place info into table and serialize table data based on user entries.

# Usage Mode
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
Buy me a coffe by following the next link
<a href="paypal.me/sinticbolivia" style="text-align:center;">
	<img src="https://pics.paypal.com/00/p/Mjc5MDY5NjItYTBiYS00M2I1LThiZWItNGNjNmVjOGM5Y2U1/image_2.JPG" alt="" /><br/>
<img src="https://camo.githubusercontent.com/bb217cc672bb9b7ecffa9bcc75dd0d7a3776af53/687474703a2f2f6772617065736a732e636f6d2f696d672f70706d652e706e67" alt="PayPalMe" style="max-width:100%;"><br/>
	Buy me a coffee
</a>
