# Outras Disciplinas

> **📝 Espaço reservado** para outros componentes curriculares.

Conforme novas disciplinas forem ministradas, suas áreas de material serão
adicionadas aqui.

## Como adicionar uma nova disciplina

Para criar a área de uma nova disciplina, basta:

1. Criar uma pasta dentro de `docs/disciplinas/` com o nome da disciplina (ex.: `eletronica-digital/`)
2. Adicionar um arquivo `index.md` na pasta
3. Adicionar a navegação no arquivo `mkdocs.yml`, dentro da seção `Disciplinas`

Exemplo de entrada no `mkdocs.yml`:

```yaml
nav:
  - Disciplinas:
      - Automação Industrial:
          - disciplinas/automacao-industrial/index.md
      - Eletrônica Digital:
          - disciplinas/eletronica-digital/index.md
```

A estrutura sugerida para cada nova disciplina segue o mesmo padrão de
**Automação Industrial**: plano de ensino, apostila, aulas, atividades,
avaliações e referências.
