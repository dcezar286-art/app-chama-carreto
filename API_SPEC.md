# Especificação de API – Chama Carreto

Este documento descreve como será a API oficial do aplicativo **Chama Carreto**.
Serve para apresentação aos sócios e planejamento do backend.

---

## 🔐 Autenticação

### POST /auth/registrar  
Cria um novo usuário (cliente ou carreteiro).

**Body:**
```json
{
  "nome": "José da Silva",
  "email": "jose@exemplo.com",
  "telefone": "1199999-0000",
  "senha": "minha_senha",
  "tipo": "cliente"
}

{
  "id": 1,
  "nome": "José da Silva",
  "email": "jose@exemplo.com",
  "tipo": "cliente"
}
{ "email": "jose@exemplo.com", "senha": "minha_senha" }
{
  "access_token": "JWT_AQUI",
  "token_type": "bearer"
}
{
  "origem_endereco": "Rua Oriente, 500 - Brás",
  "destino_endereco": "Jaçanã, São Paulo",
  "tipo_carga": "bebidas",
  "peso_estimado": 300
}
{
  "id": 42,
  "origem_endereco": "Rua Oriente, 500 - Brás",
  "destino_endereco": "Jaçanã, São Paulo",
  "tipo_carga": "bebidas",
  "peso_estimado": 300,
  "status": "pendente",
  "preco_estimado": 180.0,
  "criado_em": "2025-01-01T12:00:00Z"
}
{ "id": 42, "status": "aceito" }
{ "id": 42, "status": "concluido" }
