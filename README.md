# xev0r UI Library v3.1

**Nowoczesna, szybka i estetyczna biblioteka UI do Roblox **

![Version](https://img.shields.io/badge/Version-3.1-blue)
![Roblox](https://img.shields.io/badge/Roblox-Executor-orange)

---

## ✨ Funkcje

- **Piękny ciemny interfejs** (Grey/Black theme)
- **Zaawansowany KeySystem** z zapisem klucza
- **Płynne animacje** (tweeny + spring)
- **Konfigurowalne okna** z zapisywaniem ustawień
- **Tab system**
- **Wszystkie popularne elementy UI**:
  - Toggle, Slider, Dropdown, Button
  - ColorPicker, Keybind, Input, Textarea
  - ProgressBar, Separator, Label
- **Notyfikacje** z animacjami
- **Watermark** z FPS i czasem
- **Auto config save/load**

---

## 📥 Instalacja / Użycie

```lua
local xev0r = loadstring(game:HttpGet("https://raw.githubusercontent.com/xev00r/xev0rhub/main/LibraryAPI"))()
Przykład użycia:
Luaxev0r:KeySystem({
    Title = "xev0r Hub",
    Subtitle = "Enter key to continue",
    Keys = {"xev0r-free", "twoj-klucz-vip"},
    KeyLink = "https://twoj-link-do-klucza.com",
    SaveKey = true,
    Callback = function()
        
        local Window = xev0r:CreateWindow({
            Title = "xev0r Hub",
            Subtitle = "v3.1",
            ConfigId = "moj_hub_config", -- do zapisywania configu
        })

        local Combat = Window:AddTab("Combat", "⚔")
        Combat:AddSection("Aimbot")

        Combat:AddToggle("Silent Aim", "Automatyczne celowanie", false, function(state)
            print("Silent Aim:", state)
        end)

        Combat:AddSlider("FOV", "Pole widzenia", 0, 360, 90, function(value)
            print("FOV:", value)
        end)

        -- ... reszta Twojego skryptu
    end
})

📋 Dostępne Metody
Główne

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
