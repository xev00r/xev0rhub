# xev0rhub
my own roblox library with lots of scripts

local lib = loadstring(game:HttpGet("TUTAJ_LINK"))()

-- 1. KEY SYSTEM (opcjonalny — usuń jeśli nie potrzebujesz)
lib:KeySystem({
    Title    = "xev0r",
    Subtitle = "Wpisz klucz aby kontynuować",
    Keys     = { "xev0r-free", "xev0r-vip" },
    KeyLink  = "https://linkvertise.com/twoj-link",
    SaveKey  = true,   -- zapamiętaj klucz lokalnie
    Callback = function()

        -- 2. WATERMARK
        local wm = lib:CreateWatermark({
            Text    = "xev0r v3.0",
            ShowFPS = true,
            ShowTime= true,
        })
        -- wm:SetText("nowy tekst")
        -- wm:Toggle()
        -- wm:Destroy()

        -- 3. WINDOW
        local win = lib:CreateWindow({
            Title    = "xev0r",
            Subtitle = "v3.0",
            ConfigId = "moj_skrypt",
        })

        -- 4. TABY
        local combat = win:AddTab("Combat", "⚔")

        combat:AddSection("Aimbot")

        local silentAim = combat:AddToggle("Silent Aim", "Automatyczne celowanie", false, function(v)
            print("Silent Aim:", v)
        end, "silent_aim")

        local fov = combat:AddSlider("FOV", "Pole widzenia", 0, 360, 90, function(v)
            print("FOV:", v)
        end, "aimbot_fov")

        combat:AddDropdown("Metoda", {"Closest", "Highest HP", "Lowest HP"}, "Closest", function(v)
            print("Metoda:", v)
        end, "aimbot_method")

        combat:AddSeparator()
        combat:AddSection("Misc")

        combat:AddKeybind("Toggle Aimbot", "Klawisz do włączania", Enum.KeyCode.E, function(key)
            print("Aimbot toggle! klawisz:", key.Name)
        end, "aimbot_key")

        combat:AddButton("Kill All", "Zabij wszystkich graczy", function()
            lib:Notify({ Title="Combat", Message="Kill All aktywowany!", Type="success" })
        end)

        -- ESP tab
        local esp = win:AddTab("ESP", "👁")
        esp:AddSection("Wizualizacja")

        local espToggle = esp:AddToggle("Player ESP", nil, false, function(v)
            print("ESP:", v)
        end, "esp_enabled")

        local espColor = esp:AddColorPicker("Kolor ESP", Color3.fromRGB(200,200,200), function(c)
            print("ESP color:", c)
        end, "esp_color")

        esp:AddSlider("Max odległość", nil, 10, 1000, 500, function(v)
            print("Max dist:", v)
        end, "esp_dist")

        esp:AddProgressBar("Widocznych graczy", 0)

        -- Settings tab
        local settings = win:AddTab("Settings", "⚙")
        settings:AddSection("Konfiguracja")

        settings:AddInput("Webhook URL", "https://discord.com/api/webhooks/...", function(v)
            print("Webhook:", v)
        end, "webhook_url")

        settings:AddTextarea("Notatki", "Wpisz cokolwiek...", function(v)
            print("Notatka:", v)
        end, "notatki")

        settings:AddButton("Zapisz config", nil, function()
            win:SaveConfig()
            lib:Notify({Title="Config",Message="Zapisano!",Type="success"})
        end)

        settings:AddButton("Wczytaj config", nil, function()
            win:LoadConfig()
            lib:Notify({Title="Config",Message="Wczytano!",Type="info"})
        end)

        settings:AddSeparator()
        settings:AddLabel("xev0r UI Library v3.0 | Grey/Black Theme")

        -- 5. NOTIFIKACJE z każdym typem
        lib:Notify({ Title="xev0r",   Message="Załadowano pomyślnie!", Type="success", Duration=5 })
        lib:Notify({ Title="Uwaga",   Message="Sprawdź ustawienia.",   Type="warning", Duration=4 })
        lib:Notify({ Title="Błąd",    Message="Coś poszło nie tak.",   Type="error",   Duration=4 })
        lib:Notify({ Title="Info",    Message="Nowa wersja dostępna.", Type="info",    Duration=4 })

    end,
})
]]
