# seginfo-scram

Trabalho de Segurança da Informação na faculdade. A ideia era implementar autenticação no estilo SCRAM (desafio–resposta com salt) usando Python e sockets, sem framework, Alice é o servidor, Bob o cliente, e Charles é o atacante no meio pra estudar replay / MiTM.

Information Security coursework: a small SCRAM-style auth demo in plain Python sockets, plus a MiTM/replay scenario.

## Estrutura

- `part1-auth/` — cadastro e login com salt + hash
- `part2-mitm/` — versão com nonces / HMAC e MiTM ligado pra testar replay (tem um log de exemplo em `somativa2B.txt`)

## Como rodar - Part 1

Dois terminais, dentro de `part1-auth/`:

```bash
python3 Alice.py
python3 Bob.py
```

Se quiser o ataque, mexe em `ativar_MiTM` no `MyHashLib.py` e sobe o `Charles.py` também (em geral: Charles → Alice → Bob).

## Part2

Copia o `senhas.json` que o part1 gerou pra pasta do part2 (ou cadastra de novo) e roda o mesmo esquema. No part2 o MiTM costuma já estar ativo no código.

`senhas.json` fica fora do Git.
