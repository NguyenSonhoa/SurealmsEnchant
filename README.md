# SurealmsEnchant Plugin - Advanced Enchanting System

Plugin Minecraft với hệ thống enchant hoàn toàn mới, sử dụng Specialized Books và economy integration.

## 🌟 Tính năng chính

- **🔮 Advanced Enchanting Table**: GUI 6x9 với 3 tiers enchantments
- **📚 Specialized Books**: 12 loại book chuyên biệt cho từng item type
- **💰 Economy Integration**: Sử dụng VaultAPI - trả tiền thay vì Lapis Lazuli
- **⚔️ Anvil-Only Enchanting**: Chỉ apply enchantments qua anvil
- **🔍 Enchant Index**: GUI xem tất cả enchantments có sẵn
- **♻️ Grindstone Disenchanting**: Disenchant books để tái sử dụng
- **🎯 Tier System**: 3 cấp độ dựa trên XP level của player
- **🔮 Rune System**: Power & Protection Runes với special effects
- **⚡ Vanilla-Style Custom Enchantments**: Real Bukkit enchantments

## 🚀 Cách sử dụng

### Commands

```bash
/enchant                    # Mở enchanting table
/enchant index             # Xem tất cả enchantments
/enchant book <type>       # Lấy specialized book
/enchant book list         # Liệt kê tất cả book types
/enchant rune <type>       # Lấy runes
/enchant rune list         # Liệt kê tất cả rune types
/enchant help              # Hiển thị hướng dẫn
/enchant reload            # Reload config (admin)
```

### Permissions

```yaml
surealms.enchant.*: op          # Tất cả permissions
surealms.enchant.use: true      # Sử dụng enchanting table
surealms.enchant.index: true    # Xem enchant index
surealms.enchant.book: op       # Lấy specialized books
surealms.enchant.rune: op       # Lấy runes
surealms.enchant.admin: op      # Admin commands
```

### 📖 Hướng dẫn chi tiết

#### 1. **Lấy Specialized Books**:
```bash
/enchant book sword_book      # Book cho swords
/enchant book pickaxe_book    # Book cho pickaxes
/enchant book helmet_book     # Book cho helmets
# ... và nhiều loại khác
```

#### 2. **Tạo Enchanted Books**:
- Mở enchanting table: `/enchant`
- Đặt book vào slot giữa
- Chọn tier dựa trên level của bạn:
  - **Tier I** (Level 5+): Basic enchantments - $100+
  - **Tier II** (Level 15+): Improved enchantments - $250+
  - **Tier III** (Level 30+): Powerful enchantments - $500+
- Trả tiền để tạo enchanted book

#### 3. **Apply Enchantments**:
- Sử dụng **Anvil** để apply enchanted book lên item
- Đặt item ở slot đầu, enchanted book ở slot thứ 2
- Lấy kết quả từ slot thứ 3

#### 4. **Use Runes**:
- Lấy runes: `/enchant rune power_rune` hoặc `/enchant rune protection_rune`
- **Power Rune**: Nâng cấp tất cả enchantments lên 1 level
- **Protection Rune**: Ngăn item bị phá hủy khi durability = 0
- Apply tại **Anvil** như enchanted books

#### 5. **Disenchant Books**:
- Sử dụng **Grindstone** để disenchant
- Specialized books sẽ trở về dạng gốc
- Regular books sẽ thành book thường
- Nhận lại một phần XP

## ⚡ **Vanilla-Style Custom Enchantments**

### **Auto Smelting** (Legendary) - `surealms:auto_smelting`
- **Pickaxe Only** - Level I
- **Effect**: Tự động nung banh cục quặng khi đào
- **Vanilla Integration**: Works với /enchant command
- **Conflicts**: Silk Touch (Sài là bay acc crash game) :)

### **Backstab** (Epic) - `surealms:backstab`
- **Sword & Axe** - Level I-III
- **Effect**: +30-50% damage khi tấn công từ phía sau
- **Mechanics**: 120° detection angle
- **Vanilla Integration**: Real enchantment tooltips

### **Lucky Orb** (Rare) - `surealms:lucky_orb`
- **All Armor** - Level I-III
- **Effect**: +75-125% EXP từ orbs per piece
- **Stacking**: Across multiple armor pieces
- **Vanilla Integration**: Works in anvils như vanilla enchants

## Layout GUI

```
[ ] [ ] [ ] [ ] [B] [ ] [ ] [ ] [ ]   <- Hàng 1 (B = Book slot)
[ ] [1] [1] [1] [I] [1] [ ] [ ] [ ]   <- Hàng 2 (I = Item slot, 1 = Level I)
[ ] [ ] [2] [2] [2] [ ] [ ] [ ] [ ]   <- Hàng 3 (2 = Level II)
[ ] [ ] [3] [3] [3] [3] [ ] [ ] [ ]   <- Hàng 4 (3 = Level III)
```

## Enchantments Available

### Level I (Cost: 10 XP each)
- **Slot 5**: Sharpness I
- **Slot 6**: Smite I  
- **Slot 7**: Bane of Arthropods I
- **Slot 8**: Knockback I

### Level II (Cost: 20 XP each)
- **Slot 14**: Sharpness II
- **Slot 15**: Smite II
- **Slot 16**: Bane of Arthropods II

### Level III (Cost: 30 XP each)
- **Slot 23**: Sharpness III
- **Slot 24**: Smite III
- **Slot 25**: Bane of Arthropods III
- **Slot 26**: Fire Aspect I

## Cấu hình

File `config.yml` cho phép tùy chỉnh:

- XP cost multiplier
- Sound effects
- GUI title và layout
- Enchantment mappings
- Messages

## Yêu cầu

- **Minecraft**: 1.21+
- **Server**: Paper/Spigot
- **Java**: 21+

## Installation

1. Download file `.jar` từ thư mục `build/libs/`
2. Đặt vào thư mục `plugins/` của server
3. Restart server
4. Cấu hình permissions nếu cần

## Development

### Build từ source

```bash
./gradlew build
```

### Structure

```
src/main/kotlin/me/sanenuyan/surealmsEnchant/
├── SurealmsEnchant.kt          # Main plugin class
├── commands/
│   └── EnchantCommand.kt       # Command handler
├── gui/
│   └── EnchantGUI.kt          # GUI management
├── listeners/
│   └── EnchantListener.kt     # Event handling
└── managers/
    └── EnchantManager.kt      # Enchant logic
```

## License

MIT License - Xem file LICENSE để biết thêm chi tiết.

## Support

Nếu gặp vấn đề, vui lòng tạo issue trên GitHub repository.
