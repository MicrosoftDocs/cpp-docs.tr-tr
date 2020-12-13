---
description: 'Daha fazla bilgi edinin: optimize pragma'
title: optimize pragması
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.optimize
- optimize_CPP
helpviewer_keywords:
- pragmas, optimize
- optimize pragma
ms.assetid: cb13c1cc-186a-45bc-bee7-95a8de7381cc
ms.openlocfilehash: 9c7f07e44a31144c469bb13c936bc16d5fda39df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333206"
---
# <a name="optimize-pragma"></a>optimize pragması

İşlev işlevi temelinde iyileştirmeleri belirtir.

## <a name="syntax"></a>Syntax

> **#pragma optimize et ("** [ *optimizasyon-List* ] **",** { **on**  |  **off** } **)**

## <a name="remarks"></a>Açıklamalar

**Optimize** pragma bir işlevin dışında görünmelidir. Pragma görüntülendikten sonra tanımlanan ilk işlevde devreye girer. **Açık** ve **kapalı** bağımsız değişkenler, *iyileştirme listesinde* belirtilen seçenekleri açıp kapatır.

*En iyi duruma getirme listesi* , aşağıdaki tabloda gösterilen parametrelerden sıfır veya daha fazla olabilir.

### <a name="parameters-of-the-optimize-pragma"></a>Optimize pragma parametreleri

| Parametre (ler) | İyileştirme türü |
|--------------------|--------------------------|
| **Acil** | Genel iyileştirmeleri etkinleştirin. |
| **s** veya **t** | Makine kodunun kısa veya hızlı dizilerini belirtin. |
| **Iz** | Program yığınında çerçeve işaretçileri oluşturun. |

Bu parametreler, [/o](../build/reference/o-options-optimize-code.md) derleyici seçenekleriyle kullanılan harflerdir. Örneğin, aşağıdaki pragma `/Os` derleyici seçeneğine eşdeğerdir:

```cpp
#pragma optimize( "s", on )
```

**OPTIMIZE** pragma 'ı boş dize (**""**) ile kullanmak, yönergenin özel bir biçimidir:

**Kapalı** parametresini kullandığınızda, tüm iyileştirmeleri, **g**, **s**, **t** ve **y** işlemlerini kapatır.

**On** parametresini kullandığınızda, en iyileştirmeleri [/o](../build/reference/o-options-optimize-code.md) derleyici seçeneğini kullanarak belirttikleriniz için sıfırlar.

```cpp
#pragma optimize( "", off )
/* unoptimized code section */
#pragma optimize( "", on )
```

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
