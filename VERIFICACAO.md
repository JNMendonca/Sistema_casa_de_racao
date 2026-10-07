# Verificação

O script scripts/verify-business.mjs verifica as regras de estoque no SQLite: entrada, baixa de venda, rejeição de saldo negativo e reversão da venda inteira se um item falhar, código único e preço histórico.

O leitor USB físico deve ser configurado como teclado com Enter e testado com os códigos da loja. Este ambiente não disponibiliza navegador de inspeção nem contexto WebMCP, por isso a inspeção visual e o teste WebMCP no navegador não foram realizados.

Verificações concluídas: TypeScript sem erros e testes das regras de negócio aprovados (node scripts/verify-business.mjs).

Compilação concluída. Testes da API com banco D1 local aprovados: cadastro, validação, entrada, venda, saldo insuficiente, código duplicado, compra MEI e pagamento. Página inicial respondeu HTTP 200. Registros de teste foram removidos do banco local.

Autenticação própria verificada no D1 local: consultas e alterações anônimas bloqueadas; origem externa rejeitada; senha temporária exige troca; funcionário não gerencia usuários; bloqueio, redefinição, troca de senha e saída revogam sessões; limite de tentativas testado. As operações de estoque, vendas e pagamentos passaram usando a sessão de um funcionário.
