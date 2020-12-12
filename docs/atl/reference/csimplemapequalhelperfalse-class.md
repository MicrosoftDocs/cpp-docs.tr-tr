---
description: 'Daha fazla bilgi edinin: CSimpleMapEqualHelperFalse sınıfı'
title: CSimpleMapEqualHelperFalse sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualValue
helpviewer_keywords:
- CSimpleMapEqualHelperFalse class
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
ms.openlocfilehash: 5bad8232dc1a96fc743a3526acdb86b839601d9a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140588"
---
# <a name="csimplemapequalhelperfalse-class"></a>CSimpleMapEqualHelperFalse sınıfı

Bu sınıf, [CSimpleMap](../../atl/reference/csimplemap-class.md) sınıfı için bir yardımcıdır.

## <a name="syntax"></a>Syntax

```
template <class TKey, class TVal>
class CSimpleMapEqualHelperFalse
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleMapEqualHelperFalse:: IsEqualKey](#isequalkey)|Se Eşitlik için iki anahtarı sınar.|
|[CSimpleMapEqualHelperFalse:: IsEqualValue](#isequalvalue)|Se False döndürür.|

## <a name="remarks"></a>Açıklamalar

Bu nitelikler sınıfı, sınıfına bir ektir `CSimpleMap` . Nesnede bulunan iki öğeyi `CSimpleMap` , özellikle iki değerli öğeleri veya iki anahtar öğesi karşılaştırmak için bir yöntem sağlar.

Değer karşılaştırma her zaman false döndürür ve buna ek olarak, `ATLASSERT` başvuruluyorsa yanlış bir bağımsız değişkenle çağırır. Eşitlik testinin yeterince tanımlanmadığı durumlarda bu sınıf, anahtar/değer çiftlerini içeren bir haritanın çoğu Yöntem için doğru şekilde çalışmasını sağlar, ancak [CSimpleMap:: FindVal](../../atl/reference/csimplemap-class.md#findval)gibi karşılaştırmaları temel alan yöntemler için iyi tanımlanmış bir şekilde başarısız olur.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsimpcoll. h

## <a name="csimplemapequalhelperfalseisequalkey"></a><a name="isequalkey"></a> CSimpleMapEqualHelperFalse:: IsEqualKey

Eşitlik için iki anahtarı sınar.

```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```

### <a name="parameters"></a>Parametreler

*K1*<br/>
İlk anahtar.

*K2*<br/>
İkinci anahtar.

### <a name="return-value"></a>Dönüş Değeri

Anahtarlar eşitse true, değilse false döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)öğesini çağırır.

## <a name="csimplemapequalhelperfalseisequalvalue"></a><a name="isequalvalue"></a> CSimpleMapEqualHelperFalse:: IsEqualValue

Yanlış değerini döndürür.

```
static bool IsEqualValue(const TVal&, const TVal&);
```

### <a name="return-value"></a>Dönüş Değeri

Yanlış değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem her zaman false döndürür ve `ATLASSERT` başvuruluyorsa yanlış bir bağımsız değişkenle çağırır. , ' Nin amacı, `CSimpleMapEqualHelperFalse::IsEqualValue` eşitlik testleri yeterince tanımlanmadığında iyi tanımlanmış bir biçimde başarısız olmak için karşılaştırmaları kullanarak yöntemleri zorlamaktır.

## <a name="see-also"></a>Ayrıca bkz.

[CSimpleMapEqualHelper sınıfı](../../atl/reference/csimplemapequalhelper-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
