# Pink-Progress
Seu espaço pessoal de evolução para organizar estudos de inglês, programação e carreira de forma leve e flexível, sem transformar a rotina em obrigação. Os dados ficam salvos localmente no navegador, sem conta, sincronização ou Supabase.

O que está implementado
- Dashboard com horas de estudo registradas, tarefas abertas e concluídas, metas e revisões pendentes.
- **English Lab:** vocabulário com tradução, exemplo, nível e revisão espaçada (de novo, difícil, bom ou fácil).
- **Code Lab:** trilhas com progresso, exercícios, projetos e tarefas com prazo.
- **Career Lab:** competências, nível profissional, cursos, certificados, conquistas, metas e tarefas.
- **Analytics:** filtros por período e área; gráficos calculados a partir das sessões e conclusões registradas.
- Cadastro, consulta, edição, exclusão confirmada, busca de vocabulário, filtros, validação, estados vazios e avisos.
- Persistência local versionada. A interface não preenche registros nem estatísticas demonstrativos.
- Interface responsiva, acessível por teclado e compatível com preferência por movimento reduzido.

Os registros são armazenados somente no armazenamento local deste navegador/dispositivo. Limpar os dados do navegador apaga os registros; não há sincronização, conta, autenticação nem integração Supabase implementadas.

Requisitos

- Node.js 22.12+ ou 24.0+
- npm

## Instalação e execução

```bash
npm install
npm run dev
```

Abra o endereço local indicado pelo Vite. Os comandos adicionais são:

```bash
npm test       # testes da persistência, cálculos e fluxos de tarefas/sessões
npm run build  # verificação TypeScript e build de produção
npm run preview
```

## Dados e futura sincronização
O contrato da aplicação está em `src/types.ts`. O ponto único de leitura e gravação local está em `src/services/storage.ts`; os componentes consomem operações tipadas pelo `DataProvider`. Para integrar Supabase no futuro, substitua esse adaptador de persistência por um repositório assíncrono, mantendo os tipos e cálculos de `src/services/analytics.ts`. Hoje não existe sincronização em nuvem nem autenticação.
