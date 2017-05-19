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
([OpenClientCardAnalyticsTab](https://github.com/mrmkmcib2/jsons/blob/master/OpenClientCardAnalyticsTab.json))

Вызывается при нажатии на строку холдинга или юр.лица на всех экранах со списком холдингов и юр.лиц.
currentUrl - часть url текущей страницы после # (включая его). Нужен для реализации кнопки 'Назад' на той странице, куда произойдет переход.
clientId - идентификатор холдинга или идентификатор юр. лица.
```
{
	type: 'OpenClientCardAnalyticsTab',
	payload: {
		currentUrl: '<anchor of current url (part after #) to return back to it, e.g. #/kpi/1>'
		route:{
			type: '<holding || le_ent>',
			clientId: '<Client (holding or le_ent) identifier>',
			kpiId: '<Number of kpiId>',
			all: '<all || empty row>',
			url: '<anchor of the next page, equals to href of link>'
		}
	}	
}
```
* Открыть карточку клиента с вкладкой продукты 
```
Вызывается при нажатии на любую строку с типом продукта на дашборде Комплексность.
([OpenClientCardProductsTab](https://github.com/mrmkmcib2/jsons/blob/master/OpenClientCardProductsTab.json))

{
  type: 'OpenClientCardProductsTab',
  payload: {
    currentUrl: '<anchor of current url (part after #) to return back to it, e.g. #/kpi/1>',
    clientId: '<client identifier>',
  }
}
```
* Открыть карточку сделки 
Вызывается при нажатии на строку сделки в дашборде Pipeline .
```
{
  type: 'OpenDealCard',
  payload: {
    currentUrl: '<anchor of current url (part after #) to return back to it, e.g. #/kpi/1>',
    clientId: '<client identifier>',
    dealId: '<deal identifier>'
  }
}
```
* Показать строку поиска
([GlobalClientSearch](https://github.com/mrmkmcib2/jsons/blob/master/GlobalClientSearch.json))

Вызывается, когда инпут глобального поиска ловит фокус. На всех экранах, где присутствует инпут глобального поиска.
```
{
	type: 'GlobalClientSearch'
}
```
* Инпут поиска поймал фокус


Вызывается, когда инпут поиска на дашбордах холдинга или юр.лица (то есть на #holding/ или #le_ent/) ловит фокус.
inputTop - абсолютное значение top элемента (расстояние от верха страницы до верха инпута в пикселях)
```
{
	type: 'SearchLineOnFocus',
	inputTop: '<absolute top value of input element (element.getBoundingClientRect().top)>'
}
```
* Инпут поиска потерял фокус


Вызывается, когда инпут поиска на дашбордах холдинга или юр.лица (то есть на #holding/ или #le_ent/) по некредитным доходам теряет фокус.
```
{
	type: 'SearchLineOnBlur',
}
```
