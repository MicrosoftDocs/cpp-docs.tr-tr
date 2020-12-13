---
description: 'Daha fazla bilgi edinin: runtime_checks pragma'
title: runtime_checks pragması
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.runtime_checks
- runtime_checks_CPP
helpviewer_keywords:
- runtime_checks pragma
- pragmas, runtime_checks
ms.assetid: ae50b43f-f88d-47ad-a2db-3389e9e7df5b
ms.openlocfilehash: 2ee04751e9cc978487670314675d3fa4ae52bd3d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342302"
---
# <a name="runtime_checks-pragma"></a>runtime_checks pragması

[/RTC](../build/reference/rtc-run-time-error-checks.md) ayarlarını devre dışı bırakır veya geri yükler.

## <a name="syntax"></a>Syntax

> **#pragma runtime_checks ("** [ *runtime_checks* ] **",** { **restore**  |  **off** } **)**

## <a name="remarks"></a>Açıklamalar

Derleyici seçeneği tarafından etkinleştirilmeyen bir çalışma zamanı denetimini etkinleştiremezsiniz. Örneğin, `/RTCs` komut satırında belirtmezseniz, öğesini belirtmek `#pragma runtime_checks( "s", restore)` yığın çerçeve doğrulamasını etkinleştirmez.

**Runtime_checks** pragma bir işlevin dışında görünmelidir ve pragma görüntülendikten sonra tanımlanan ilk işlevde devreye girer. **Geri yükleme** ve **kapatma** bağımsız değişkenleri **runtime_checks** açık veya kapalı olarak belirtilen seçenekleri devre dışı bırakır.

**Runtime_checks** , aşağıdaki tabloda gösterilen parametrelerden biri sıfır veya daha fazla olabilir.

### <a name="parameters-of-the-runtime_checks-pragma"></a>Runtime_checks pragma parametreleri

| Parametre (ler) | Çalışma zamanı denetimi türü |
|--------------------|-----------------------------|
| **s** | Yığın (çerçeve) doğrulamasını mümkün. |
| **,** | Bir değer, veri kaybına neden olan daha küçük bir veri türüne atandığında bildirir. |
| **larınız** | Bir değişken tanımlanmadan önce kullanıldığında raporlar. |

Bu parametreler, derleyici seçeneği ile aynı olanlardır `/RTC` . Örneğin:

```cpp
#pragma runtime_checks( "sc", restore )
```

**Runtime_checks** pragma 'ı boş dize (**""**) ile kullanmak, yönergenin özel bir biçimidir:

- **Kapalı** parametresini kullandığınızda, yukarıdaki tabloda listelenen çalışma zamanı hata denetimlerini devre dışı bırakır.

- **Restore** parametresini kullandığınızda, çalışma zamanı hata denetimini, derleyici seçeneğini kullanarak belirttikleriniz için sıfırlar `/RTC` .

```cpp
#pragma runtime_checks( "", off )
/* runtime checks are off in this region */
#pragma runtime_checks( "", restore )
```

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
