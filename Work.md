###�������� � ��������� �������������
����, ��� �� ������ ������� ��������?
��� ��� ����������� ��������� �������:
```
/youthcoind --start-mining arg
```
��� arg ���������� ���������� �������.
###��� ��������� �������?
��������� Daemon � Wallet � ������ RPC. Daemoon �������� � ������� ������. ��� Wallet ���������� ���������� ��������� ����.

��������:

```
simplewallet --wallet-file=example_wallet.bin --pass=12345 --rpc-bind-port=8082
```

����������: ���� �� ������, ����� ��� Daemon �������� �������� ���������� � ������� ������� ������ ���������� ����������, �� ������ ��������� ����� �� ���������� �����������: --rpc-bind-ip=0.0.0.0 --rpc-bind-port=arg . �� ����� ������ ������� IP-����� ������ ��� ������� simplewallet. ���� ��������� �������� ������� ���:

```
-- daemon-address=arg
```

simplewallet ������������ � ���������� ������ �� �����: port 
--daemon-host=arg
cinnects simplewallet � ���������� ������ �� ���� arg ������ localhost 
--daemon-port=arg
simplewallet ������������ � ���������� ������ localhost � ����� arg ������ 8081
����� �������� ����, �� ������ ������ simplewallet ��������� �������:

������: 

```
simplewallet --wallet-file=example_wallet.bin --pass=12345 --daemon-address=123.123.1.1:8082
simplewallet --wallet-file=example_wallet.bin --pass=12345 --daemon-host=123.123.1.1
simplewallet --wallet-file=example_wallet.bin --pass=12345 --daemon-port=8082
```

���������� ������� �������� ������� �� ���������, ��������� ��� ������������ �������������. �� ���������� ����� ������ �������� �������������.

��� ��������� �������� � ������� ���������� �������� ������������ ����� get_payments.

��������:

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

��� �������� ����������� ����� transfer.

������ ����������:

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
amount - ����� �������;
adress - ����������;
fee - ������� �� ������ ��������� � �������� �������(��� ������ �����, ��� ���� ��� ��������� � ������ ���������� � ������ ������������� �������).
payment_id �� �������� ������������, ���� �� ����������� ������������ ���������.