* Сообщение об ошибке, произошедшей на странице 
([ThrowError](https://github.com/mrmkmcib2/jsons/blob/master/ThrowError.json))

Вызывается при возникновении ошибки. Список типов и кодов возможных ошибок будет оговариваться отдельно. Пока можно пробрасывать сетевые ошибки с errorType='httpResponseError', code='<http код ошибки>', text='<(необязательно) текст ошибки>'
```
{
	type: 'ThrowError',
	payload: {
		errorType: '<httpResponseError || businessError || ...>',
		code: '<Error Code>',
		text: '<Some Information about error>'
	}
}
```
* Открыть карточку клиента с вкладкой аналитика 
[GlobalClientSearch](https://github.com/mrmkmcib2/jsons/blob/master/OpenClientCardAnalyticsTab.json)
```
{
	type: 'OpenClientCardAnalyticsTab',
	payload: {
		currentUrl: '<anchor of current url (part after #) to return back to it, e.g. #/kpi/1>'
		route:{
			type: '<holding || le_ent>',
			clientId: '<Client (holding or le_ent) identifier>',
			kpiId: '<Number of kpiId>',
			all: '<all || empty row>'
		}
	}	
}
```
* Показать строку поиска
[GlobalClientSearch](https://github.com/mrmkmcib2/jsons/blob/master/GlobalClientSearch.json)
```
{
	type: 'GlobalClientSearch'
}
```
