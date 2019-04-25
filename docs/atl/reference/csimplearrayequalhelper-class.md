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
ms.openlocfilehash: 8b7e32ddab5b2f0667b17b0f127ac2e7e5d9a426
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62278000"
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

## <a name="see-also"></a>Ayrıca bkz.

[CSimpleArray Sınıfı](../../atl/reference/csimplearray-class.md)<br/>
[CSimpleArrayEqualHelperFalse Sınıfı](../../atl/reference/csimplearrayequalhelperfalse-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
