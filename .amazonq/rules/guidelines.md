# Regras de Enums e Padrões Específicos

## Contexto de Aplicação
Estas regras se aplicam ao uso de enums, padrões específicos de desenvolvimento e boas práticas para estruturas de dados em projetos Grails.

## Regras

### R077 - Criação de Enums
**Contexto**: Criação e organização de enums
- **R077.1**: Definir enums em package chamado `enums`
- **R077.2**: Considerar retrocompatibilidade ao adicionar novos valores
- **R077.3**: Publicar definição do enum antes de usá-lo efetivamente
- **R077.4**: Evitar quebra de releases ao adicionar novos valores

### R078 - Ordenação de Enums
**Contexto**: Organização de valores em enums
- **R078.1**: Ordenar por ciclo de vida quando existir
- **R078.2**: Usar ordenação alfabética quando não houver ciclo de vida
- **R078.3**: Manter estados de erro no final do enum
- **R078.4**: Documentar lógica de ordenação

### R079 - Conversão de Enums
**Contexto**: Conversão entre diferentes enums
- **R079.1**: Criar método de conversão no enum que será convertido
- **R079.2**: Usar prefixo `convertTo` seguido do nome do enum resultante
- **R079.3**: Implementar todos os casos de conversão
- **R079.4**: Documentar mapeamentos de conversão

### R080 - Validação de Enums
**Contexto**: Validação de valores de enum
- **R080.1**: Criar métodos de validação dentro da classe do enum
- **R080.2**: Usar retorno Boolean para métodos de validação
- **R080.3**: Usar nomenclatura `is[Estado]()` para validações
- **R080.4**: Evitar imports desnecessários em outros lugares

### R081 - Descontinuação de Enums
**Contexto**: Marcação de enums obsoletos
- **R081.1**: Usar anotação `@Deprecated` para enums descontinuados
- **R081.2**: Mover enums descontinuados para o final da classe
- **R081.3**: Documentar motivo da descontinuação
- **R081.4**: Considerar migração de dados existentes

### R082 - Tratamento Resiliente de Enum em TagLib
**Contexto**: Tratamento de enums não mapeados em TagLibs
- **R082.1**: Implementar método de fallback para enums não mapeados
- **R082.2**: Aplicar estilo visual padrão (neutro) como fallback
- **R082.3**: Logar alerta para enums não mapeados

### R083 - Não Usar FindOrCreateWhere
**Contexto**: Evitar uso de FindOrCreateWhere
- **R083.1**: Não utilizar `findOrCreate` em produção
- **R083.2**: Fazer busca e criação manualmente
- **R083.3**: Usar o padrão Repository para busca
- **R083.4**: Verificar softDelete adequadamente

### R084 - Não Usar Tokenize
**Contexto**: Evitar uso de tokenize
- **R084.1**: Não usar `tokenize` em código de produção
- **R084.2**: Usar `split` por ser mais previsível
- **R084.3**: Considerar comportamento com valores nulos
- **R084.4**: Testar comportamento com delimitadores múltiplos

### R085 - Não Usar First e Last
**Contexto**: Evitar uso de first e last
- **R085.1**: Usar `[0]` em vez de `first()`
- **R085.2**: Usar `[-1]` em vez de `last()`
- **R085.3**: Sempre verificar se lista não está vazia antes de usar `[-1]`
- **R085.4**: Usar `getAt(0)` e `getAt(-1)` quando necessário safe operator

### R086 - Interrupção de Jobs
**Contexto**: Interrupção da execução de Jobs
- **R086.1**: Implementar mecanismo de interrupção adequado
- **R086.2**: Usar flags de controle para interrupção
- **R086.3**: Logar interrupções para auditoria
- **R086.4**: Garantir limpeza de recursos ao interromper

### R087 - Uso de If Else em Validações
**Contexto**: Utilização de If Else em validações
- **R087.1**: Usar if/else apenas quando necessário
- **R087.2**: Prefira o uso de `early returns` para simplificar fluxos complexos e reduzir cadeias extensas de `if`/`else if`/`else`
- **R087.3**: Manter validações simples e claras
- **R087.4**: Documentar lógica complexa

### R088 - Padrão de Listagem com Filtros
**Contexto**: Padrão de utilização de filtros nas telas de listagem
- **R088.1**: Implementar filtros de forma consistente
- **R088.2**: Usar padrão estabelecido para filtros
- **R088.3**: Validar filtros antes de aplicar
- **R088.4**: Documentar filtros disponíveis

### R089 - Exportação em Excel
**Contexto**: Criação e uso de formatters na exportação de Excel
- **R089.1**: Usar formatters padronizados para exportação
- **R089.2**: Manter consistência no formato de dados
- **R089.3**: Documentar formatters criados
- **R089.4**: Testar exportação com diferentes tipos de dados

### R090 - Padrão de Variáveis
**Contexto**: Padrão de nomenclatura e uso de variáveis
- **R090.1**: Usar nomes descritivos para variáveis
- **R090.2**: Seguir convenções de nomenclatura
- **R090.3**: Evitar variáveis com nomes muito curtos
- **R090.4**: Documentar variáveis complexas

### R091 - Constantes
**Contexto**: Uso e organização de constantes
- **R091.1**: As constantes devem ser nomeadas em SCREAMING_SNAKE_CASE
- **R091.2**: As constantes devem ser definidas no início da classe ou do método
- **R091.3**: Sempre deve ser utilizada a palavra chave `final` para indicar imutabilidade
- **R091.4**: Para constantes definidas dentro de classes, utilize o modificador `private`. Para constantes definidas em método não é necessário
- **R091.5**: Usar nomes descritivos para constantes
- **R091.6**: Agrupar constantes relacionadas
- **R091.7**: Documentar propósito das constantes

### R092 - Padrão de TagLibs
**Contexto**: Padrões para criação de TagLibs
- **R092.1**: Seguir padrão estabelecido para TagLibs
- **R092.2**: Implementar tratamento de erro adequado
- **R092.3**: Documentar parâmetros e comportamento

### R093 - Mensagens de Retorno em Alertas
**Contexto**: Como apresentar mensagens de retorno em alertas
- **R093.1**: Usar mensagens claras e objetivas
- **R093.2**: Manter consistência no formato das mensagens
- **R093.3**: Evitar mensagens técnicas para usuários finais
