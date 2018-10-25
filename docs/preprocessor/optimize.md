---
title: en iyi duruma getirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.optimize
- optimize_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, optimize
- optimize pragma
ms.assetid: cb13c1cc-186a-45bc-bee7-95a8de7381cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 98275f6e0a16c6d07b66ce592eb12b9391157653
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50069743"
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