---
title: CSimpleArrayEqualHelper sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper::IsEqual
helpviewer_keywords:
- CSimpleArrayEqualHelper class
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
ms.openlocfilehash: e677a5d12918649597db9614b965118f8d6b7da6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50656229"
---
# <a name="csimplearrayequalhelper-class"></a>CSimpleArrayEqualHelper sınıfı

Bu sınıf için Yardımcısı, [CSimpleArray](../../atl/reference/csimplearray-class.md) sınıfı.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class CSimpleArrayEqualHelper
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Türetilmiş bir sınıf.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleArrayEqualHelper::IsEqual](#isequal)|(Statik) İki `CSimpleArray` nesne eşitliği öğeleri.|

## <a name="remarks"></a>Açıklamalar

Bu nitelikler sınıfı için bir ektir `CSimpleArray` sınıfı. Depolanan karşılaştırma iki öğe için bir yöntem sağlar. bir `CSimpleArray` nesne. Varsayılan olarak, öğeleri kullanılarak karşılaştırılır **operator=()**, ancak dizi kendi eşitlik işleci eksik karmaşık veri türleri içeriyorsa, bu sınıf geçersiz kılmak gerekir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsimpcoll.h

##  <a name="isequal"></a>  CSimpleArrayEqualHelper::IsEqual

İki `CSimpleArray` nesne eşitliği öğeleri.

```
static bool IsEqual(
    const T& t1,
    const T& t2);
```

### <a name="parameters"></a>Parametreler

*T1*<br/>
T türünde bir nesne

*T2*<br/>
T türünde bir nesne

### <a name="return-value"></a>Dönüş Değeri

Öğe yanlış Aksi takdirde, eşitse true döndürür.

## <a name="see-also"></a>Ayrıca Bkz.

[CSimpleArray Sınıfı](../../atl/reference/csimplearray-class.md)<br/>
[CSimpleArrayEqualHelperFalse Sınıfı](../../atl/reference/csimplearrayequalhelperfalse-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
