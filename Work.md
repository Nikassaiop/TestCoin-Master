###Работаем с созданной криптовалютой
Итак, как же начать процесс майнинга?
Для это вписывается следующая команда:
```
/youthcoind --start-mining arg
```
где arg замещается актуальным адресом.
###Как запустить кошелек?
Запускаем Daemon и Wallet в режиме RPC. Daemoon работает в обычном режиме. Для Wallet необходимо установить незанятый порт.

Например:

```
simplewallet --wallet-file=example_wallet.bin --pass=12345 --rpc-bind-port=8082
```

Примечание: Если вы хотите, чтобы ваш Daemon принимал входящие соединения с внешней стороны вашего локального компьютера, вы должны запустить Демон со следующими аргументами: --rpc-bind-ip=0.0.0.0 --rpc-bind-port=arg . Вы также должны указать IP-адрес демона при запуске simplewallet. Есть несколько способов сделать это:

```
-- daemon-address=arg
```

simplewallet подключается к экземпляру демона на хосте: port 
--daemon-host=arg
cinnects simplewallet к экземпляру демона на узле arg вместо localhost 
--daemon-port=arg
simplewallet подключается к экземпляру демона localhost в порту arg вместо 8081
Чтобы подвести итог, вы должны начать simplewallet следующим образом:

Пример: 

```
simplewallet --wallet-file=example_wallet.bin --pass=12345 --daemon-address=123.123.1.1:8082
simplewallet --wallet-file=example_wallet.bin --pass=12345 --daemon-host=123.123.1.1
simplewallet --wallet-file=example_wallet.bin --pass=12345 --daemon-port=8082
```

Обновление статуса кошелька вручную не требуется, поскольку оно производится автоматически. Не запускайте более одного кошелька единовременно.

Для получения сведений о статусе получаемых платежей используется метод get_payments.

Например:

```
{
"jsonrpc":"2.0",
"method":"get_payments",
"params":
{
"payment_id": "78cc4b76a48bd50ab955ac61a0c04e4a82079fbcf27298f87b39c76aefccbcc9"
}
}

```

Для передачи применяется метод transfer.

Пример выполнения:

```
{
  "jsonrpc":"2.0",
  "method":"transfer",
  "params":
    {
      "destinations":
        [
          {
            "amount":11111,
            "address":"248iCFTjpRKGdoD34B6nJVfgLLgnoucNhMYWeTVAAkpoQQV6yVve2sxh6QVxSh4HW213Wy5siw8eBa5k2G1sV639QzFWqGD"
          },
          {
            "amount":22222,
            "address":"248iCFTjpRKGdoD34B6nJVfgLLgnoucNhMYWeTVAAkpoQQV6yVve2sxh6QVxSh4HW213Wy5siw8eBa5k2G1sV639QzFWqGD"
           }
        ],
      "payment_id":"", 
      "fee":1000000,
      "mixin":0,
      "unlock_time":0
    }
}
```
amount - Сумма платежа;
adress - Получатель;
fee - сколько вы готовы выплатить в качестве награды(чем больше даете, тем выше ваш приоритет в списке транзакций в случае загруженности каналов).
payment_id не является обязательным, если вы пользуетесь единственным кошельком.