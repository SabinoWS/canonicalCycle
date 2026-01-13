Conversa

[07:46, 13/01/2026] ~: A ideia é gerar rules e agentes para cada parte do fluxo
[07:47, 13/01/2026] ~: Por exemplo

Analista
Raw - > filtered - > canonical - > artefatos
[07:47, 13/01/2026] ~: Raw do analista é uma conversa com o cliente, anotações, fotos, documentos etc
[07:48, 13/01/2026] ~: Filtered é ele é a IA organizando isso
[07:48, 13/01/2026] ~: Canonical é o que ele como responsável aprovou e que a IA pode gerar um artefato a qualquer momento a partir disso
[07:49, 13/01/2026] ~: Artefato depende da role. Analista seria a análise de negócio, requisitos, épico e história
[07:49, 13/01/2026] ~: Aí depois disso passa para a próxima role
[07:50, 13/01/2026] ~: Arquiteto, a partir do artefato de análise de negócio ele faz todo o fluxo dele do raw (que é o artefato anterior + coisas raw de levantamentos dele) até o artefato dele
[07:51, 13/01/2026] ~: Depois vai para engenharia e desenvolvimento
[07:51, 13/01/2026] ~: E todos estes agentes claro
[07:52, 13/01/2026] ~: A ideia é

1 memória por aquivo
2 sempre poder gerar artefatos a partir das verdades, artefatos descartáveis
3 autonomia agentica porém com responsabilidade técnica das personas aprovando os canonicals (uma mesma pessoa pode tocar mais de uma persona)
[07:55, 13/01/2026] ~: Aí claro que cada role/persona quem for usar o ciclo pode especificar pro seu uso
[07:56, 13/01/2026] ~: Como o agente deve escrever os tickets, boas práticas pro arquiteto e engenheiro, como o desenvolvedor deve escrever código e trabalhar de forma específica em X projeto etc
[08:05, 13/01/2026] ~: Um exemplo pequeno

O suporte mandou uma mensagem de algumas coisas quebrando no mapa. O relato, e prints

Analista 
.. 1 botei isso na pasta relatoMapa/raw
.. 2 no prompt dei meu pensamento e acesso ao raw
3 o agente analista criou o filtered com os cenários de ajustes
.. 4 fiz alguns refinamentos pequenos no filtered e aprovei 
5 agente gerou o canonical
.. 6 aprovei
7 ele gerou os tickets no jira

Arquiteto
Neste cenário, não tão necessário.

Engenheiro
.. 1 inicío o prompt enviando os tickets
2 o agente lê os tickets, lê o código (contexto de workspace), cria um levantamento filtrado sobre ajustes, impactos esforço e onde mexer exatamente.
.. 3 ajusto, se necessário. Aprovo o filtered
4 agente cria as tasks detalhadas da história
.. 5 aprovo
6 agente cria os tickets no jira

Desenvolvedor
Raw = tasks
Filtered = alterações no workspace (código) feitas pelo agente
Canonical = stage do git
Artefato = commit