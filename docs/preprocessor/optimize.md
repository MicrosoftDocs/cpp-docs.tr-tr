---
title: optimize
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.optimize
- optimize_CPP
helpviewer_keywords:
- pragmas, optimize
- optimize pragma
ms.assetid: cb13c1cc-186a-45bc-bee7-95a8de7381cc
ms.openlocfilehash: 65948f2b466bdd40bd753dbba99e2e235c57b0f6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615871"
---
# <a name="optimize"></a>optimize

İşlev tarafından işlevi olarak gerçekleştirilecek iyileştirmeleri belirtir.

## <a name="syntax"></a>Sözdizimi

```
#pragma optimize( "[optimization-list]", {on | off} )
```

## <a name="remarks"></a>Açıklamalar

**En iyi duruma getirme** pragma işlevin dışında görünmelidir ve pragma görüldüğünde sonra tanımlanmış konumundaki ilk işlev etkinleşir. *Üzerinde* ve *kapalı* bağımsız değişkenleri kapatma seçenekleri belirtilen *iyileştirme listesi* açıp kapatabilir.

*İyileştirme listesi* sıfır veya daha fazla parametre aşağıdaki tabloda gösterilen olabilir.

### <a name="parameters-of-the-optimize-pragma"></a>Optimize Pragması parametreleri

|Parametre|İyileştirme türü|
|--------------------|--------------------------|
|*g*|Genel iyileştirmeler sağlar.|
|*s* veya *t*|Makine kodu kısa veya hızlı dizisi belirtin.|
|*Y*|Programın yığınında çerçeve işaretçileri oluşturur.|

İle kullanılan aynı harflerini bunlar [/O](../build/reference/o-options-optimize-code.md) derleyici seçenekleri. Örneğin, aşağıdaki pragma değerine eşdeğer olan `/Os` derleyici seçeneği:

```
#pragma optimize( "ts", on )
```

Kullanarak **en iyi duruma getirme** pragma ile boş bir dize (**""**) özel bir formu yönergesi:

Kullanırken *kapalı* parametresi iyileştirmeleri etkinleştirir *g*, *s*, *t*, ve *y*, kapalı.

Kullanırken *üzerinde* parametresi ile belirtilen bu iyileştirmeler sıfırlar, [/O](../build/reference/o-options-optimize-code.md) derleyici seçeneği.

```
#pragma optimize( "", off )
.
.
.
#pragma optimize( "", on )
```

## <a name="see-also"></a>Ayrıca Bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)