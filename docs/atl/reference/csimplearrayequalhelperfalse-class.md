---
title: CSimpleArrayEqualHelperFalse Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse::IsEqual
helpviewer_keywords:
- CSimpleArrayEqualHelperFalse class
ms.assetid: 6918af6f-d23d-49eb-8482-c44272f5ffeb
ms.openlocfilehash: 5eca3145d64895e34b599fbf83834af142b65973
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330898"
---
# <a name="csimplearrayequalhelperfalse-class"></a>CSimpleArrayEqualHelperFalse Sınıfı

Bu sınıf [CSimpleArray](../../atl/reference/csimplearray-class.md) sınıfı için bir yardımcıdır.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class CSimpleArrayEqualHelperFalse
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Türemiş bir sınıf.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSimpleArrayEqualHelperFalse::IsEqual](#isequal)|(Statik) Yanlış döndürür.|

## <a name="remarks"></a>Açıklamalar

Bu özellikler sınıfı sınıfın `CSimpleArray` tamamlayıcısıdır. Her zaman yanlış döndürür ve `ATLASSERT` buna ek olarak, hiç başvurulmuş sayılsa yanlış bir argüman ile arayacaktır. Eşitlik testinin yeterince tanımlanmamış olduğu durumlarda, bu sınıf, öğeleriçeren bir dizinin çoğu yöntem için doğru çalışmasına izin verir, ancak CSimpleArray gibi karşılaştırmalara bağlı yöntemler için iyi tanımlanmış bir şekilde başarısız [olur::Bul](../../atl/reference/csimplearray-class.md#find).

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsimpcoll.h

## <a name="csimplearrayequalhelperfalseisequal"></a><a name="isequal"></a>CSimpleArrayEqualHelperFalse::IsEqual

Yanlış değerini döndürür.

```
static bool IsEqual(const T&, const T&);
```

### <a name="return-value"></a>Dönüş Değeri

Yanlış değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem her zaman yanlış `ATLASSERT` döndürür ve başvurulmuşsa false bağımsız değişkeni ile çağırır. Bunun `CSimpleArrayEqualHelperFalse::IsEqual` amacı, eşitlik testleri yeterince tanımlanmamışken karşılaştırmaları kullanarak yöntemleri iyi tanımlanmış bir şekilde başarısız olmaya zorlamaktır.

## <a name="see-also"></a>Ayrıca bkz.

[CSimpleArrayEqualHelper Sınıfı](../../atl/reference/csimplearrayequalhelper-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
