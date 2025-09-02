# CraftRecipeConfig — описание конфигурации рецепта крафта

Конфигурация задаётся в формате **JSON**. Каждый объект описывает отдельный рецепт.

## Основные поля

| Поле | Тип | Описание |
|------|-----|-----------|
| `craftRecipeID` | `int` | Уникальный ID рецепта |
| `categoryID` | `string` | Категория рецепта (например, `"Craft"`) |
| `craftTitle` | `string` | Название рецепта |
| `craftDescription` | `string` | Описание рецепта (опционально) |
| `resultPreview` | `string` | Класс или превью-объект результата |
| `buttonCraftTitle` | `string` | Название кнопки (по умолчанию `#STR_RLF_WS_CRAFT`) |
| `progressTitle` | `string` | Заголовок прогресса (по умолчанию `#STR_RLF_WS_DIRECT_CRAFT_TIME`) |
| `craftMode` | `int` | Режим крафта (0 – обычный, др. значения зависят от логики) |
| `craftTimeSec` | `int` | Время крафта в секундах |
| `showResultAttachmentsInfo` | `int` (0/1) | Показывать ли инфо об аттачментах результата |
| `spawnOutsideWorkbench` | `int` (0/1) | Спавнить ли результат вне верстака |
| `resultSpawnPosition` | `array[3]` | Позиция спавна результата (XYZ) |
| `resultSpawnOrientation` | `array[3]` | Ориентация результата (XYZ) |
| `resultSpawnPosOffset` | `array[3]` | Смещение позиции спавна |
| `addPerkPointsSkillTypes` | `array[string]` | Типы навыков, за которые начисляются очки |
| `addPerkPointsValue` | `array[int]` | Количество очков навыков |
| `needPerkToCraft` | `array[int]` | ID перков, необходимых для крафта |
| `hideRecipeWithoutPerk` | `int` (0/1) | Скрывать рецепт без нужных перков |
| `requireAllPerksInList` | `int` (0/1) | Требуются ли все перки из списка |

---

## Блок `results` — результаты крафта

Каждый объект внутри `results` описывает один предмет, создаваемый рецептом.

| Поле | Тип | Описание |
|------|-----|-----------|
| `classname` | `string` | Класс предмета |
| `resultTitle` | `string` | Заголовок результата (опционально) |
| `resultPreview` | `string` | Картинка/превью |
| `showResultAttachmentsInfo` | `bool` | Показывать ли инфо о вложениях |
| `count` | `array[int]` | Количество (min, max, step) |
| `health` | `array[int]` | Прочность результата |
| `quantity` | `array[int]` | Количество ресурса в предмете |
| `energy` | `array[int]` | Заряд энергии |
| `liquid` | `int` | Тип жидкости |
| `foodStage` | `int` | Стадия еды |
| `chance` | `float` | Шанс получения (0.0–1.0) |
| `cleanness` | `int` | Чистота предмета |

---

## Блок `needIngredients` — необходимые ингредиенты

Каждый объект описывает один обязательный ингредиент.

| Поле | Тип | Описание |
|------|-----|-----------|
| `isKindOf` | `bool` | Использовать `IsKindOf` для проверки |
| `itemTitle` | `string` | Название предмета |
| `itemClassname` | `array[string]` | Список допустимых классов |
| `itemPreview` | `string` | Превью предмета |
| `itemCount` | `int` | Количество |
| `itemHealth` | `int` | Минимальное состояние |
| `itemQuantity` | `array[int]` | Кол-во ресурса (min, max) |
| `itemEnergy` | `array[int]` | Энергия (min, max) |
| `itemFoodStage` | `array[int]` | Допустимые стадии еды |
| `itemCleanness` | `int` | Чистота |
| `itemLiquidType` | `int` | Тип жидкости |
| `destroyItem` | `bool` | Уничтожать предмет после крафта |
| `itemHaveEnergy` | `bool` | Требуется ли заряд |
| `itemDamageAfterCraft` | `array[int]` | Повреждение после крафта |
| `itemQuantityAfterCraft` | `array[int]` | Изменение количества после крафта |

---

## Блок `needAttachment` — требуемые аттачменты

Описание оборудования/инструментов, которые должны быть прикреплены.

| Поле | Тип | Описание |
|------|-----|-----------|
| `isKindOf` | `bool` | Использовать `IsKindOf` для проверки |
| `attachType` | `string` | Класс аттачмента |
| `attachSlot` | `string` | Слот аттачмента |
| `needElectricityOn` | `int` (0/1) | Требуется ли питание |
| `hideRecipeIfMissing` | `int` (0/1) | Скрывать рецепт, если отсутствует |
| `damageAfterCraft` | `int` | Наносимый урон инструменту |
| `decreaseAttachQuantity` | `dict` | Уменьшение количества (например, диска) |
| `decreaseAttachHealth` | `dict` | Уменьшение прочности |

---
