---
description: pragmaMicrosoft C/C++ ' da runtime_checks yönergesi hakkında daha fazla bilgi edinin
title: runtime_checks pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.runtime_checks
- runtime_checks_CPP
helpviewer_keywords:
- runtime_checks pragma
- pragma, runtime_checks
no-loc:
- pragma
ms.openlocfilehash: 4932126ffe33d2f8a99f6d94e3c58d2c0322df92
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98712823"
---
# <a name="runtime_checks-no-locpragma"></a>`runtime_checks` pragma

Derleyici seçenek ayarlarını devre dışı bırakır veya geri yükler [`/RTC`](../build/reference/rtc-run-time-error-checks.md) .

## <a name="syntax"></a>Syntax

> **`#pragma runtime_checks( "`** [ *çalışma zamanı-Check-Options* ] **`",`** { **`restore`** | **`off`** } **`)`**

## <a name="remarks"></a>Açıklamalar

Derleyici seçeneği tarafından etkinleştirilmeyen bir çalışma zamanı denetimini etkinleştiremezsiniz. Örneğin, **`/RTCs`** komut satırında belirtmezseniz, öğesini belirtmek `#pragma runtime_checks( "s", restore)` yığın çerçeve doğrulamasını etkinleştirmez.

, **`runtime_checks`** pragma Bir işlevin dışında görünmelidir ve görülendikten sonra tanımlanan ilk işlevde etkili olur pragma . **`restore`** Ve **`off`** bağımsız değişkenleri, açma veya kapatma içinde belirtilen seçenekleri **`runtime_checks`** pragma devre dışı bırakır.

*Çalışma zamanı-onay seçenekleri* aşağıdaki tabloda gösterilen parametrelerden veya daha fazla olabilir.

### <a name="parameters-of-the-runtime_checks-pragma"></a>Runtime_checks pragma parametreleri

| Parametre (ler) | Çalışma zamanı denetimi türü |
|--------------------|-----------------------------|
| **`s`** | Yığın (çerçeve) doğrulamasını mümkün. |
| **`c`** | Bir değer, veri kaybına neden olan daha küçük bir veri türüne atandığında bildirir. |
| **`u`** | Bir değişken tanımlanmadan önce kullanıldığında raporlar. |

Bu parametreler, derleyici seçeneği ile aynı olanlardır **`/RTC`** . Örneğin:

```cpp
#pragma runtime_checks( "sc", restore )
```

Öğesini **`runtime_checks`** pragma boş dize () ile kullanmak, **`""`** yönergesinin özel bir biçimidir:

- Parametresini kullandığınızda, **`off`** Yukarıdaki tabloda listelenen çalışma zamanı hata denetimleri devre dışı bırakır.

- **`restore`** Parametresini kullandığınızda, çalışma zamanı hata denetimini, derleyici seçeneğini kullanarak belirttikleriniz için sıfırlar **`/RTC`** .

```cpp
#pragma runtime_checks( "", off )
/* runtime checks are off in this region */
#pragma runtime_checks( "", restore )
```

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
