-- Carregamento da biblioteca Rayfield atualizada
local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

-- Criação da janela principal do DG Hub
local Window = Rayfield:CreateWindow({
   Name = "DG Hub",
   LoadingTitle = "Carregando DG Hub...",
   LoadingSubtitle = "Interface Oficial",
   Theme = "Ocean", -- Tema azul (você também pode testar "DarkBlue")
   ConfigurationSaving = {
      Enabled = true,
      FolderName = "DGHubConfig",
      FileName = "Configuracoes"
   },
   Discord = {
      Enabled = false
   },
   KeySystem = false -- Sistema de Key desativado
})

-- Notificação de inicialização
Rayfield:Notify({
   Title = "DG Hub",
   Content = "Painel inicializado com sucesso!",
   Duration = 5
})

-- Aba Principal
local MainTab = Window:CreateTab("Início", 4483345998)
local MainSection = MainTab:CreateSection("Controles DG Hub")

-- Botão de Exemplo
MainTab:CreateButton({
   Name = "Executar Ação",
   Callback = function()
       print("Ação do DG Hub executada!")
   end,
})

-- Alternador (Toggle)
MainTab:CreateToggle({
   Name = "Ativar Função",
   CurrentValue = false,
   Flag = "DGHubToggle",
   Callback = function(Value)
       print("Estado da função no DG Hub:", Value)
   end,
})

-- Controle Deslizante (Slider)
MainTab:CreateSlider({
   Name = "Ajuste de Nível",
   Range = {0, 100},
   Increment = 1,
   Suffix = "%",
   CurrentValue = 50,
   Flag = "DGHubSlider",
   Callback = function(Value)
       print("Nível ajustado para:", Value)
   end,
})
