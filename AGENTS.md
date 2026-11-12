# AGENTS.md – O que é este projeto

Olá! Se és um assistente de IA (ou uma pessoa) a pegar neste repositório, começa por aqui.

## Em poucas palavras

Isto é um **trabalho prático da cadeira de Segurança**. O objetivo é montar uma rede no
**Cisco Packet Tracer** (7 routers, 4 switches, 6 PCs/servidores) e ir-lhe acrescentando
camadas de segurança: passwords, SSH, RADIUS/AAA, ACLs, firewall por zonas, IPS e um túnel IPsec.

O enunciado completo está em [ENUNCIADO.md](ENUNCIADO.md) e o diagrama em [topologia.png](topologia.png).

**Valor de X = 10.** Todas as redes `192.X.n.0/24` do diagrama são `192.10.n.0/24`.

## Regras para quem ajudar neste projeto

- **Escrever em português de Portugal**, de forma simples, como se estivesses a explicar a um colega.
- Os comandos têm de funcionar **no Packet Tracer**, não só num router real. O PT não suporta tudo
  (por exemplo, algumas opções de IPS ou de AAA). Na dúvida, avisar.
- Os routers 1941 do PT não têm portas FastEthernet: onde o diagrama diz `Fa0/0`/`Fa0/1` usamos `G0/0`/`G0/1`.
- Se mudares um IP, uma password ou um nome, muda-o em **todo o lado**: `configs/`, `etapas/`,
  `README.md` e `configs/PCs-e-Servidores.md`. Estes ficheiros têm de bater certo uns com os outros.
- Todas as passwords têm de ter **pelo menos 10 caracteres** (Etapa 5).
- Cada etapa deve ter sempre uma parte **"Verificar"**: um `show …`, um ping, um SSH ou um teste no browser
  que prove que funciona. Isso é o que vai para o relatório.
- Não inventar requisitos que não estão no enunciado. Se for preciso acrescentar uma regra por causa
  dos equipamentos (ex.: deixar o S3 responder ao SSH na ACL), explicar porquê.

