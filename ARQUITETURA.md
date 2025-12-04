### **📄 Conteúdo completo do arquivo `ARQUITETURA.md`:**

```md
# Arquitetura do Sistema – Chama Carreto

Este documento descreve a arquitetura técnica planejada do app **Chama Carreto**.

---

# 🏗️ 1. Componentes principais

## 📱 Aplicativos móveis
- App Cliente  
- App Carreteiro  
- Desenvolvidos em **React Native (Expo)** ou **Flutter**  
- Funções:
  - Login
  - Chamar carreto (cliente)
  - Receber chamadas (carreteiro)
  - Acompanhamento do serviço
  - Avaliação

---

## 🌐 Backend (API)

### Linguagens e serviços
- Linguagem: **Python**
- Framework: **FastAPI**
- Banco de dados: **PostgreSQL**
- Autenticação: **JWT**
- Pagamentos: Pix/Cartão (futuro)
- Mapas: Google Maps ou Mapbox

### Responsabilidades
- Criar e autenticar usuários
- Registrar pedidos de carreto
- Parear cliente ↔ carreteiro
- Calcular preço estimado
- Registrar aceites e conclusões
- Notificações (push)
- Painel administrativo

---

## 💾 Banco de Dados – Modelo inicial

### Tabela: `usuarios`
- id
- nome
- email
- senha_hash
- telefone
- tipo (cliente, carreteiro, admin)

### Tabela: `carreteiros`
- id (FK → usuarios)
- placa
- tipo_veiculo
- capacidade_kg
- online

### Tabela: `chamados`
- id
- cliente_id
- carreteiro_id (pode ser null até alguém aceitar)
- origem_endereco
- destino_endereco
- tipo_carga
- peso_estimado
- preco_estimado
- preco_final
- status (pendente, aceito, concluido, cancelado)
- criado_em

---

# 🧭 2. Fluxo do sistema

## Cliente
1. Faz login
2. Informa origem, destino, carga
3. API cria o chamado
4. Carreteiros próximos recebem notificação

## Carreteiro
1. Abre o app e fica ONLINE
2. Recebe lista de chamados pendentes
3. Aceita um deles
4. Finaliza ao entregar carga

---

# 🚀 3. Evolução do projeto

### Fase 1 – **MVP**
- Protótipo web (já pronto)
- Documentação API (este arquivo)

### Fase 2 – **Desenvolvimento**
- FastAPI + PostgreSQL
- Apps em React Native

### Fase 3 – **Publicação**
- Hospedagem backend (Render / AWS / PythonAnywhere)
- Publicar app:
  - Google Play Store
  - Apple App Store

---

# 📌 Conclusão
Esses arquivos formam a base profissional do projeto para apresentação aos sócios
antes de iniciar a fase de desenvolvimento.
