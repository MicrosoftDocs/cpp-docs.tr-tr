---
title: CSimpleMapEqualHelperFalse Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualValue
helpviewer_keywords:
- CSimpleMapEqualHelperFalse class
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
ms.openlocfilehash: b6bf1d4e3be849004e13e593fb5f4b5cb87f8123
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330742"
---
# <a name="csimplemapequalhelperfalse-class"></a>CSimpleMapEqualHelperFalse Sınıfı

Bu sınıf [CSimpleMap](../../atl/reference/csimplemap-class.md) sınıfı için bir yardımcıdır.

## <a name="syntax"></a>Sözdizimi

```
template <class TKey, class TVal>
class CSimpleMapEqualHelperFalse
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSimpleMapEqualHelperFalse::IsEqualKey](#isequalkey)|(Statik) Eşitlik için iki anahtar test ediyor.|
|[CSimpleMapEqualHelperFalse::IsEqualValue](#isequalvalue)|(Statik) Yanlış döndürür.|

## <a name="remarks"></a>Açıklamalar

Bu özellikler sınıfı `CSimpleMap` sınıfın bir ekidir. Nesnede bulunan iki öğeyi, özellikle `CSimpleMap` iki değer öğesini veya iki anahtar öğeyi karşılaştırmak için bir yöntem sağlar.

Değer karşılaştırması her zaman yanlış döndürecek `ATLASSERT` ve buna ek olarak, hiç başvurulmuşsa yanlış bir argüman ile çağırır. Eşitlik testinin yeterince tanımlanmamış olduğu durumlarda, bu sınıf anahtar/değer çiftleri içeren bir haritanın çoğu yöntem için doğru çalışmasına izin verir, ancak [CSimpleMap::FindVal](../../atl/reference/csimplemap-class.md#findval)gibi karşılaştırmalara bağlı yöntemler için iyi tanımlanmış bir şekilde başarısız olur.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsimpcoll.h

## <a name="csimplemapequalhelperfalseisequalkey"></a><a name="isequalkey"></a>CSimpleMapEqualHelperFalse::IsEqualKey

Eşitlik için iki anahtar test ediyor.

```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```

### <a name="parameters"></a>Parametreler

*k1*<br/>
İlk anahtar.

*k2*<br/>
İkinci anahtar.

### <a name="return-value"></a>Dönüş Değeri

Anahtarlar eşitse doğru döndürür, aksi takdirde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)çağırır.

## <a name="csimplemapequalhelperfalseisequalvalue"></a><a name="isequalvalue"></a>CSimpleMapEqualHelperFalse::IsEqualValue

Yanlış değerini döndürür.

```
static bool IsEqualValue(const TVal&, const TVal&);
```

### <a name="return-value"></a>Dönüş Değeri

Yanlış değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem her zaman yanlış `ATLASSERT` döndürür ve hiç başvurulmuşsa false bağımsız değişkeni ile çağırır. Bunun `CSimpleMapEqualHelperFalse::IsEqualValue` amacı, eşitlik testleri yeterince tanımlanmamışken karşılaştırmaları kullanarak yöntemleri iyi tanımlanmış bir şekilde başarısız olmaya zorlamaktır.

## <a name="see-also"></a>Ayrıca bkz.

[CSimpleMapEqualHelper Sınıfı](../../atl/reference/csimplemapequalhelper-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
