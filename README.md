<div align="center">
  <h1>xev0r UI Library</h1>
  <p><strong>Nowoczesna • Szybka • Estetyczna</strong> biblioteka interfejsu dla Roblox</p>

  ![Version](https://img.shields.io/badge/Version-3.1-blue?style=for-the-badge)
  ![Roblox](https://img.shields.io/badge/Roblox-Executor-orange?style=for-the-badge)
  ![Lua](https://img.shields.io/badge/Lua-5.1-yellow?style=for-the-badge)
</div>

---

## ✨ Główne Funkcje

- Zaawansowany **KeySystem** z zapisywaniem klucza
- Płynne animacje (tweeny + spring effect)
- System **Tabów** i sekcji
- Konfigurowalne okna z auto save/load
- Watermark z FPS i czasem
- System notyfikacji (success, error, warning, info)
- Elegancki ciemny design (Grey/Black Theme)

---

## 📥 Szybka Instalacja

```lua
local xev0r = loadstring(game:HttpGet("https://raw.githubusercontent.com/xev00r/xev0rhub/main/LibraryAPI"))()

```

## 📋 Dostępne Metody Główne

xev0r:KeySystem(options)
xev0r:CreateWindow(options)
xev0r:CreateWatermark(options)
xev0r:Notify(options)

Elementy okna

Tab:AddToggle()
Tab:AddSlider()
Tab:AddDropdown()
Tab:AddButton()
Tab:AddColorPicker()
Tab:AddKeybind()
Tab:AddInput()
Tab:AddTextarea()
Tab:AddProgressBar()
Tab:AddSection()
Tab:AddSeparator()
Tab:AddLabel()

## 📖 Pełny Przykład Użycia

xev0r:KeySystem({
    Title = "xev0r Hub",
    Subtitle = "Enter key to continue",
    Keys = {"xev0r-free", "xev0r-vip"},
    KeyLink = "https://twoj-link-do-klucza.com",
    SaveKey = true,

    Callback = function()
        local Window = xev0r:CreateWindow({
            Title = "xev0r Hub",
            Subtitle = "v3.1",
            ConfigId = "xev0r_main_config", -- potrzebne do zapisywania ustawień
        })

        -- TABY
        local Combat = Window:AddTab("Combat", "⚔️")
        Combat:AddSection("Aimbot")

        Combat:AddToggle("Silent Aim", "Automatyczne celowanie", false, function(state)
            print("Silent Aim:", state)
        end)

        Combat:AddSlider("FOV", "Pole widzenia aimbota", 40, 360, 120, function(value)
            print("FOV:", value)
        end)

        Combat:AddDropdown("Cel", {"Head", "Torso", "Closest"}, "Head", function(selected)
            print("Cel:", selected)
        end)

        local Visuals = Window:AddTab("Visuals", "👁️")
        local Settings = Window:AddTab("Settings", "⚙️")

        xev0r:Notify({
            Title = "xev0r Hub",
            Message = "Skrypt załadowany pomyślnie!",
            Type = "success"
        })
    end
})


🎨 Theme
Aktualnie tylko Grey/Black (ciemny, elegancki).

📌 Wersja 3.1 — Co nowego?

Poprawiony i dopracowany KeySystem
Lepsze animacje otwarcia/zamknięcia
Naprawione dragi (Slider + ColorPicker)
Lepsze zarządzanie configiem
Wyczyszczony i zoptymalizowany kod

```

📞 Kontakt / Discord

## Made with ❤️ by xev00r

## Gwiazdkuj repo jeśli Ci się podoba ⭐
