# iterchat
Разработать быстрый асинхронный чат с использованием итераторов/генераторов


## TODO list

1. ± Создадим глобальный объект, где будем хранить сообщения всех пользователей.
2. ± При подключении новых клиентов, мы должны выводить из этого объекта все сообщения, которые нам отправили пользователи к текущему моменту.
3. При отправке любого сообщения от клиента, этот клиент должен получать все сообщения из глобального буффера, которых у него нет.
	- Создать роут (endpoint), отнаследовав стандартный из tornado RequestHandler. 
	- С "клиента" при отправке сообщения через websocket должен уходить "сигнал" о том, что необходимо получить обновленное содержание MessageBuffer всех остальных клиентов.
			
			- отправить с клиента на endpoint "/message/update" сообщение об обновлении содержимого чата; 
			- прислать с сервера содержимое, которого нет у клиента;

	- сервер должен для каждого клиента проверить какие сообщения ему нужно отправить и сформировать массив таких сообщений и отправить ему.

4. Каждый пользователь должен иметь уникальный идентификатор для того, чтобы можно было использовать его персональные сообщения, привязывать их к этому идентификатору.


4. Реализовать сохранение сообщений пользователей в базе данных и при возможности возвращаться к прошлым сессиям чата.
5. Реализовать подсчет сообщений пользователя, итерацию по ним с использованием итераторов/генераторов.
