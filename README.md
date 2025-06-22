# Diagramas iSaúde

### Cadastro
```mermaid
graph TD
    A[Tela Inicial] --> B[Boas-vindas]
    B --> C{Criar conta ou Login?}
    C -->|Login| D[Login]
    C -->|Criar conta| E[Introdução]
    
    E --> F{Seleção de Perfil}
    F -->|Paciente| G[Paciente]
    F -->|Profissional Saúde| H[Fluxo Profissional]
    F -->|Unidade Saúde| I[Fluxo Unidade Saúde]
    F -->|Farmácia| J[Fluxo Farmácia]
    
    %% FLUXO PACIENTE
    G --> G1[Dados Pessoais]
    G1 --> G2[Contato]
    G2 --> G3[Verificação]
    G3 --> G4[Nome Usuário]
    G4 --> G5[Senha]
    G5 --> G6{Foto Perfil?}
    G6 -->|Sim| G7[Upload Foto]
    G6 -->|Não| G8[Finalizado]
    G7 --> G8
    
    %% FLUXO PROFISSIONAL
    H --> H1[Dados Pessoais]
    H1 --> H2[Contato]
    H2 --> H3[Verificação]
    H3 --> H4[Informações Profissionais]
    H4 --> H5[Nome Usuário]
    H5 --> H6[Senha]
    H6 --> H7{Foto Perfil?}
    H7 -->|Sim| H8[Upload Foto]
    H7 -->|Não| H9[Finalizado]
    H8 --> H9
    
    %% FLUXO UNIDADE SAÚDE
    I --> I1[Dados Jurídicos]
    I1 --> I2[Responsável Técnico]
    I2 --> I3[Contato]
    I3 --> I4[Verificação]
    I4 --> I5[Nome Usuário]
    I5 --> I6[Senha]
    I6 --> I7{Foto Perfil?}
    I7 -->|Sim| I8[Upload Foto]
    I7 -->|Não| I9[Finalizado]
    I8 --> I9
    
    %% FLUXO FARMÁCIA
    J --> I1
    
    %% SUBFLUXO LOGIN
    D --> D1[CPF/CNPJ]
    D1 --> D2[Senha]
    D2 --> D3{Esqueci Senha?}
    D3 -->|Sim| D4[Solicitar Redefinição]
    D4 --> D5[Email com Link]
    D5 --> D6[Nova Senha]
    D6 --> D7[Confirmar Senha]
    D7 --> D
    D3 -->|Não| Z[Feed]
    
    G8 --> Z
    H9 --> Z
    I9 --> Z



```mermaid

---
### Pacientes

---
config:
  layout: fixed
---
flowchart TD
    A["Feed Principal"] --> B["Post Individual"] & C["Perfil de Outro Usuário"] & D["Explorar"] & E["Sua Saúde"] & F["Conversas"] & G["Criar Publicação"] & E1["Meu Perfil"]
    B --> B1["Comentários"] & B2["Curtir Post"] & B3["Salvar Post"] & B4["Compartilhar"] & B5["Denunciar Post"]
    B1 --> B1a["Responder Comentário"]
    C --> C1["Publicações do Usuário"] & C2["Seguir/Deixar de Seguir"] & C3["Enviar Mensagem"] & C4["Agendar Consulta"]
    C4 --> C4a["Agendamentos"]
    D --> D1["Buscar Conteúdo"] & D2["Conteúdo Recomendado"]
    D1 --> D1a["Resultados de Busca"]
    G --> G1["Selecionar Tipo"]
    G1 --> G1a["Texto"] & G1b["Imagem"] & G1c["Vídeo"] & G1d["Pulse"]
    G1a --> G2["Compor Texto + Hashtags"]
    G1b --> G3["Selecionar Imagem"]
    G1c --> G4["Gravar/Selecionar Vídeo"]
    G1d --> G5["Gravar Vídeo Curto"]
    E --> E1 & E2["Meus Agendamentos"] & E3["Agendar Nova Consulta"] & E4["Prescrições e Atestados"] & E5["Histórico de Exames"] & E6["Prontuário"]
    E2 --> E2a["Detalhes do Agendamento"]
    E2a --> E2b["Cancelar Consulta"] & E2d["Reagendar"] & E2e["Juntar à Teleconsulta"]
    E2d --> E3
    E2e --> E2f["Sala de Espera Virtual"]
    E3 --> E3a["Buscar Profissional"]
    E3a --> E3b["Perfil Profissional"]
    E3b --> E3c["Selecionar Serviço"]
    E3c --> E3d["Escolher Data/Hora"]
    E3d --> E3e["Preencher Prontuário"]
    E3e --> E3f["Forma de Pagamento"]
    E3f --> E3g["Resumo da Compra"] & E3k["Ajuda com Pagamento"]
    E3g --> E3h["Confirmação"]
    E3h --> E3i["Adicionar à Agenda"]
    E3i --> E3j["Sincronizar Calendário"]
    E4 --> E4a["Visualizar Documento"]
    E4a --> E4b["Compartilhar Exame"] & E4c["Imprimir"]
    E5 --> E4a
    F --> F1["Lista"]
    F1 --> F1a["Nova Conversa"] & F2["Conversa"]
    F1a --> F1b["Selecionar Contato"]
    F2 --> F2a["Enviar Mensagem"]
    F2a --> F2b["Digitar Texto"] & F2c["Anexar Arquivo"]
    F2c --> F2d["Selecionar Tipo"]
    F2d --> F2e["Galeria"] & F2f["Câmera"] & F2g["Documentos"]
    F2g --> F2h["Prontuário iSaúde"] & F2i["Arquivo do Dispositivo"]
    F2i --> F2j["Visualizador de PDF"]
    E1 --> Z["Opções"] & Z1["Editar Perfil"]
    Z --> Z2["Informações Pessoais"] & Z3["Privacidade"] & Z4["Notificações"] & Z5["Acessibilidade"] & Z6["Central de Ajuda"] & Z7["Sair"]
    Z1 --> Z1a["Foto"] & Z1b["Nome"] & Z1c["Bio"]
    Z2 --> Z2a["CPF"] & Z2b["Email"] & Z2c["Telefone"]
    Z6 --> Z6a["FaQ"] & Z6b["Suporte"]
    D2 --> B
    C4a --> E3
 
```mermaid
