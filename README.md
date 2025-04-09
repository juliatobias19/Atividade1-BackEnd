# Atividade1-BackEnd

👨🏽 *Tabela: usuarios*
*id (PK) – Identificador único do usuário

*nome – Nome completo

*email – Email único do usuário

*senha_hash – Senha criptografada

*telefone – Número de telefone

*data_cadastro – Data de registro na plataforma

*tipo_usuario – Pode ser 'anfitriao', 'hospede' ou 'ambos'

🔗 Relacionamentos:

1 usuário → N lugares (lugares.usuario_id)

1 usuário → N hospedagens (hospedagens.usuario_id)

1 usuário → N avaliações (avaliacoes.usuario_id)

=====================================================================

🏨 *Tabela: lugares*
*id (PK) – Identificador do lugar

*usuario_id (FK) – Referência ao dono do lugar (usuarios.id)

*titulo – Título do anúncio

*descricao – Descrição detalhada

*endereco – Localização do imóvel

*preco_por_noite – Valor da diária

*data_cadastro – Quando o lugar foi cadastrado

*status – 'ativo' ou 'inativo'

🔗 Relacionamentos:

1 lugar → N hospedagens (hospedagens.lugar_id)

=====================================================================

🛎️ *Tabela: hospedagens*
*id (PK) – Identificador da hospedagem

*usuario_id (FK) – Quem fez a reserva (usuarios.id)

*lugar_id (FK) – Lugar reservado (lugares.id)

*data_inicio – Data de entrada

*data_fim – Data de saída

*valor_total – Valor total calculado

*status – 'reservado', 'concluido', 'cancelado'

🔗 Relacionamentos:

1 hospedagem → 1 avaliação (opcional)

1 lugar → N hospedagens

1 usuário → N hospedagens

=====================================================================

⭐ *Tabela: avaliacoes*
*id (PK) – Identificador da avaliação

*hospedagem_id (FK) – Referência à hospedagem avaliada (hospedagens.id)

*usuario_id (FK) – Quem fez a avaliação (usuarios.id)

*nota – Nota de 1 a 5

*comentario – Texto com a opinião do usuário

*data_avaliacao – Quando a avaliação foi feita

🔗 Relacionamentos:

Cada avaliação está ligada a uma única hospedagem

Cada usuário pode fazer várias avaliações

=====================================================================
