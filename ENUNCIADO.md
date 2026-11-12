# Enunciado do projeto – Segurança de Redes (Cisco Packet Tracer)

![Topologia da rede](docs/topologia.png)

**x = 10** → as redes `192.X.n.0/24` do diagrama ficam `192.10.n.0/24`.

## Tarefas

**Etapa 1:** Atribua o nome aos equipamentos.

**Etapa 2:** Configure um banner.

**Etapa 3:** Configure os IPs nos equipamentos.

**Etapa 4:** Configure as rotas estáticas para colocar todos os equipamentos a comunicar.

**Etapa 5:** Configure a password com um tamanho mínimo de 10 caracteres.

**Etapa 6:** Configure a password de enable com "cisco12345".

**Etapa 7:** Configure um utilizador com privilégios 15 em todos os routers e switches e configure a line vty com este user/pass e com o método de transporte SSH.

**Etapa 8:** Configure em todos os routers o acesso remoto apenas através do PC-A.

**Etapa 9:** Configure um servidor RADIUS no PC-A e crie o utilizador com username "RadAdmin" e a password "RadAdminpa55".

**Etapa 10:** Crie um modelo AAA no R1 e R3, em que o primeiro método é o servidor RADIUS e o segundo método de autenticação é a base de dados local do router.

**Etapa 11:** Configurar ACLs estendidas de acordo com as seguintes premissas:

- A rede local do R3 é utilizada em laboratórios de computador de alunos. O administrador de rede notou que os alunos nesses laboratórios estão a tentar hackear o servidor. Crie uma ACL que negue todo o tráfego entre as LANs do R1 e do R3.
- Todo o tráfego da rede local do R3 com destino à porta TCP 80, 443 e DNS deve ser permitido.
- Igualmente a rede do R3 deverá poder comunicar em FTP para as LAN dos R4 e R6.
- Qualquer tráfego não especificado acima deve ser negado (se alguma comunicação/serviço for necessária entre as redes devido aos equipamentos, adicione a regra antes desta última).

**Etapa 12:** Crie uma Zone Based Firewall no R7 com 3 zonas: Outside, DMZ e Inside, e as seguintes premissas:

- Nenhum tráfego iniciado na zona Outside deve ser permitido para a rede interna.
- O tráfego de retorno da zona Outside (pacotes de retorno vindos da Internet para o site R7, em resposta a solicitações originadas de qualquer uma das redes R7) deve ser permitido.
- Os computadores na rede interna R7 são considerados confiáveis e podem iniciar qualquer tipo de tráfego (tráfego baseado em TCP, UDP ou ICMP).
- Os servidores na DMZ são considerados não confiáveis e têm permissão para iniciar apenas o tráfego da Web (HTTP ou HTTPS) para a zona Outside, assim como só podem receber este tipo de tráfego.
- Nenhum tráfego é permitido entre a rede interna e a DMZ.

**Etapa 13:** No router R2 ative uma IPS com as assinaturas básicas entre a Internet e a rede 10.3.3.0/30. O PC-A deverá receber os logs da IPS.

**Etapa 14:** Crie um túnel IPsec entre o R4 e o R6 de forma que as LAN do R4 e R6 comuniquem em segurança.

**Etapa 15:** Ative os serviços de segurança do IOS e da configuração.

## Redes do diagrama (com x = 10)

| Rede | Onde |
|---|---|
| 192.10.1.0/24 | LAN do R1 (S1, PC-A) |
| 192.10.2.0/24 | LAN do R3 (S3, PC-C) |
| 192.10.3.0/24 | LAN do R4 (S4, PC-D) |
| 192.10.4.0/24 | LAN do R6 (S5, PC-E) |
| 192.10.5.0/24 | INSIDE do R7 (PC-F) |
| 172.16.1.0/24 | DMZ do R7 (PC-B) |
| 10.1.1.0/30 | R1 ↔ R2 (série) |
| 10.2.2.0/30 | R2 ↔ R3 (série) |
| 10.3.3.0/30 | R2 ↔ R5 (Ethernet) |
| 10.4.4.0/30 | R4 ↔ R5 (série) |
| 10.5.5.0/30 | R5 ↔ R6 (série) |
| 10.6.6.0/30 | R2 ↔ R7 (OUTSIDE) |
| 62.48.16.12/24 | Loopback 0 do R2 ("Internet") |
