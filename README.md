#  в чем разница между токеном доступа и токеном обновления?

#  Токен доступа

Маркер доступа — это строка, представляющая авторизацию, выданную клиенту. Токены представляют определенные области и продолжительность доступа, 
предоставляемые владельцем ресурса и принудительно применяемые сервером ресурсов и сервером авторизации.
Токен доступа помещается в заголовок авторизации нашего запроса и обычно выглядит как «Bearer h090Yuuyuiyv». 
Это проверяется API, который вызывает клиент.
Маркер доступа обычно имеет формат JWT, но вы можете использовать любой другой формат.
JWT доступа обычно недолговечны, потому что их сложно (хотя и возможно) отозвать централизованно.
Ответственность за токен доступа заключается в доступе к данным до истечения срока их действия.

#  Токен обновления

Токен обновления выдается (вместе с токеном доступа) клиенту сервером авторизации.
Токен обновления отвечает за запрос нового токена доступа, когда срок действия существующего токена доступа истек.
Мы также можем получить дополнительные токены доступа с такой же или более узкой областью действия из токенов обновления.
Выдача токена обновления не является обязательной по усмотрению сервера авторизации.
Токен обновления — это долгоживущий токен.
Только клиенты, которые могут безопасно защитить токены обновления, должны использовать токены обновления.
Идентификационный токен

# ID-токен — это личность пользователя.
Как и токен доступа, он также обычно имеет формат JWT, но не обязательно.
Идентификационный токен не должен содержать никакой информации об авторизации или аудитории, 
поскольку его задача — просто идентифицировать пользователя.

https://medium.com/@greekykhs/springsecurity-what-is-the-difference-between-access-and-refresh-token-65296bcb13fc