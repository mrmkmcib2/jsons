# jsons

## Сообщение об ошибке, произошедшей на странице
```
{
	type: 'ShowError',
	payload: {
		errorType: '<httpResponseError || businessError || ...>',
		code: '<Error Code>',
		text: '<Some Information about error>'
	}
}
```
## Открыть карточку клиента с вкладкой аналитика
```
}
	type: 'OpenClientCardAnalyticsTab',
	payload: {
		route:{
			type: '<holding || le_ent>',
			clientId: '<Client (holding or le_ent) identifier>',
			kpiId: '<Number of kpiId>',
			all: '<all || empty row>'
		}
	}	
}
```
