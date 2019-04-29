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
ms.openlocfilehash: 9f5240fc59f59a71ddb3d18b67fadf3463a0d1ea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328178"
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

## <a name="see-also"></a>Ayrıca bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)