---
description: 'Daha fazla bilgi edinin: optimize pragma'
title: getirileceğini pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.optimize
- optimize_CPP
helpviewer_keywords:
- pragma, optimize
- optimize pragma
no-loc:
- pragma
ms.openlocfilehash: d9044788d0eea394867622d0f7aea1e365ad3399
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713460"
---
# <a name="optimize-no-locpragma"></a>`optimize` pragma

İşlev işlevi temelinde iyileştirmeleri belirtir.

## <a name="syntax"></a>Syntax

> **`#pragma optimize( "`** [ *iyileştirme-liste* ] **`",`** { **`on`** | **`off`** } **`)`**

## <a name="remarks"></a>Açıklamalar

**`optimize`** pragma Bir işlevin dışında görünmelidir. Görünmeden sonra tanımlanan ilk işlevde etkili olur pragma . **`on`** Ve **`off`** bağımsız değişkenleri *iyileştirme listesinde* belirtilen seçenekleri açıp kapatır.

*En iyi duruma getirme listesi* , aşağıdaki tabloda gösterilen parametrelerden sıfır veya daha fazla olabilir.

### <a name="parameters-of-the-optimize-pragma"></a>Optimize pragma parametreleri

| Parametre (ler) | İyileştirme türü |
|--------------------|--------------------------|
| **`g`** | Genel iyileştirmeleri etkinleştirin. |
| **`s`** veya **`t`** | Makine kodunun kısa veya hızlı dizilerini belirtin. |
| **`y`** | Program yığınında çerçeve işaretçileri oluşturun. |

Bu parametreler, derleyici seçenekleriyle kullanılan harflerdir [`/O`](../build/reference/o-options-optimize-code.md) . Örneğin, aşağıdaki pragma **`/Os`** derleyici seçeneğine eşdeğerdir:

```cpp
#pragma optimize( "s", on )
```

Öğesini **`optimize`** pragma boş dize () ile kullanmak, **`""`** yönergesinin özel bir biçimidir:

Parametresini kullandığınızda, **`off`** Tüm iyileştirmeleri,,,, **`g`** **`s`** **`t`** ve **`y`** ' ı kapatır.

**`on`** Parametresini kullandığınızda, iyileştirmeleri derleyici seçeneğini kullanarak belirttikleriniz için sıfırlar [`/O`](../build/reference/o-options-optimize-code.md) .

```cpp
#pragma optimize( "", off )
/* unoptimized code section */
#pragma optimize( "", on )
```

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
