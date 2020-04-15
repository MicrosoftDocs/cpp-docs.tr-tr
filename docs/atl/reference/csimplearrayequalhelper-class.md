---
title: CSimpleArrayEqualHelper Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper::IsEqual
helpviewer_keywords:
- CSimpleArrayEqualHelper class
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
ms.openlocfilehash: 386b005777b3e31dd74916a41bc5af2ab82df210
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330885"
---
# <a name="csimplearrayequalhelper-class"></a>CSimpleArrayEqualHelper Sınıfı

Bu sınıf [CSimpleArray](../../atl/reference/csimplearray-class.md) sınıfı için bir yardımcıdır.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class CSimpleArrayEqualHelper
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Türemiş bir sınıf.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSimpleArrayEqualHelper::IsEqual](#isequal)|(Statik) Eşitlik `CSimpleArray` için iki nesne öğeyi sınar.|

## <a name="remarks"></a>Açıklamalar

Bu özellikler sınıfı `CSimpleArray` sınıfın bir ekidir. Bir nesnede depolanan iki öğeyi `CSimpleArray` karşılaştırmak için bir yöntem sağlar. Varsayılan olarak, öğeler **operator=()** kullanılarak karşılaştırılır, ancak dizi kendi eşitlik işleci olmayan karmaşık veri türleri içeriyorsa, bu sınıfı geçersiz kılmanız gerekir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsimpcoll.h

## <a name="csimplearrayequalhelperisequal"></a><a name="isequal"></a>CSimpleArrayEqualHelper::IsEqual

Eşitlik `CSimpleArray` için iki nesne öğeyi sınar.

```
static bool IsEqual(
    const T& t1,
    const T& t2);
```

### <a name="parameters"></a>Parametreler

*T1*<br/>
T türünde bir nesne.

*t2*<br/>
T türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

Öğeler eşitse doğru döndürür, aksi takdirde yanlış.

## <a name="see-also"></a>Ayrıca bkz.

[CSimpleArray Sınıfı](../../atl/reference/csimplearray-class.md)<br/>
[CSimpleArrayEqualHelperFalse Sınıfı](../../atl/reference/csimplearrayequalhelperfalse-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
