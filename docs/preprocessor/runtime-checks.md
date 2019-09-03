---
title: runtime_checks pragması
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.runtime_checks
- runtime_checks_CPP
helpviewer_keywords:
- runtime_checks pragma
- pragmas, runtime_checks
ms.assetid: ae50b43f-f88d-47ad-a2db-3389e9e7df5b
ms.openlocfilehash: a1c8e6cca27e157818e6ec80182f8fefa112daf1
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216611"
---
# <a name="runtime_checks-pragma"></a>runtime_checks pragması

[/RTC](../build/reference/rtc-run-time-error-checks.md) ayarlarını devre dışı bırakır veya geri yükler.

## <a name="syntax"></a>Sözdizimi

> **#pragma runtime_checks ("** [ *runtime_checks* ] **",** { **restore** | **off** } **)**

## <a name="remarks"></a>Açıklamalar

Derleyici seçeneği tarafından etkinleştirilmeyen bir çalışma zamanı denetimini etkinleştiremezsiniz. Örneğin, komut satırında belirtmezseniz `/RTCs` `#pragma runtime_checks( "s", restore)` , öğesini belirtmek yığın çerçeve doğrulamasını etkinleştirmez.

**Runtime_checks** pragma bir işlevin dışında görünmelidir ve pragma görüntülendikten sonra tanımlanan ilk işlevde etkili olur. **Geri yükleme** ve **kapatma** bağımsız değişkenleri, **runtime_checks** açık veya kapalı olarak belirtilen seçenekleri devre dışı bırakır.

**Runtime_checks** , aşağıdaki tabloda gösterilen parametrelerden biri sıfır veya daha fazla olabilir.

### <a name="parameters-of-the-runtime_checks-pragma"></a>Runtime_checks pragma parametreleri

| Parametre (ler) | Çalışma zamanı denetimi türü |
|--------------------|-----------------------------|
| **s** | Yığın (çerçeve) doğrulamasını mümkün. |
| **c** | Bir değer, veri kaybına neden olan daha küçük bir veri türüne atandığında bildirir. |
| **u** | Bir değişken tanımlanmadan önce kullanıldığında raporlar. |

Bu parametreler, `/RTC` derleyici seçeneği ile aynı olanlardır. Örneğin:

```cpp
#pragma runtime_checks( "sc", restore )
```

**Runtime_checks** pragma 'ı boş dize ( **""** ) ile kullanmak, yönergenin özel bir biçimidir:

- **Kapalı** parametresini kullandığınızda, yukarıdaki tabloda listelenen çalışma zamanı hata denetimlerini devre dışı bırakır.

- **Restore** parametresini kullandığınızda, çalışma zamanı hata denetimini, `/RTC` derleyici seçeneğini kullanarak belirttikleriniz için sıfırlar.

```cpp
#pragma runtime_checks( "", off )
/* runtime checks are off in this region */
#pragma runtime_checks( "", restore )
```

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
