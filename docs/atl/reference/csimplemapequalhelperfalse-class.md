---
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
ms.openlocfilehash: 7ccfe59e6741c267aded8f59828947a1d98bfbc3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50572698"
---
# <a name="csimplemapequalhelperfalse-class"></a>CSimpleMapEqualHelperFalse sınıfı

Bu sınıf için Yardımcısı, [CSimpleMap](../../atl/reference/csimplemap-class.md) sınıfı.

## <a name="syntax"></a>Sözdizimi

```
template <class TKey, class TVal>
class CSimpleMapEqualHelperFalse
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleMapEqualHelperFalse::IsEqualKey](#isequalkey)|(Statik) İki anahtar eşitlik için test eder.|
|[CSimpleMapEqualHelperFalse::IsEqualValue](#isequalvalue)|(Statik) Yanlış değerini döndürür.|

## <a name="remarks"></a>Açıklamalar

Bu nitelikler sınıfı için bir ektir `CSimpleMap` sınıfı. İçindeki iki öğe karşılaştırmak için bir yöntem sağlar `CSimpleMap` nesne, özellikle iki değer öğe veya iki temel öğeleri.

Değer karşılaştırma her zaman false döndürür ve ayrıca, çağıran `ATLASSERT` bağımsız hiç olmadığı kadar başvurulan yoksa false. Burada eşitlik testi yeterince tanımlı değil durumlarda, bu sınıf için çoğu yöntemleri doğru şekilde çalışmaz, ancak üzerinde karşılaştırmalar gibi bağlı yöntemler için iyi tanımlanmış bir şekilde başarısız için anahtar/değer çiftleri içeren bir eşleme sağlar. [CSimpleMap:: FindVal](../../atl/reference/csimplemap-class.md#findval).

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsimpcoll.h

##  <a name="isequalkey"></a>  CSimpleMapEqualHelperFalse::IsEqualKey

İki anahtar eşitlik için test eder.

```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```

### <a name="parameters"></a>Parametreler

*K1*<br/>
İlk anahtar.

*K2*<br/>
İkinci anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Anahtarları false, eşitse true döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin çağırdığı [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md).

##  <a name="isequalvalue"></a>  CSimpleMapEqualHelperFalse::IsEqualValue

Yanlış değerini döndürür.

```
static bool IsEqualValue(const TVal&, const TVal&);
```

### <a name="return-value"></a>Dönüş Değeri

Yanlış değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem her zaman false değerini döndürür ve çağıracak `ATLASSERT` bağımsız hiç olmadığı kadar başvurulan yoksa false. Amacı `CSimpleMapEqualHelperFalse::IsEqualValue` yöntemleri karşılaştırmalar eşitliği testleri yeterince tanımlanmamış iyi tanımlanmış bir şekilde başarısız kullanmayı zorlamak için.

## <a name="see-also"></a>Ayrıca Bkz.

[CSimpleMapEqualHelper Sınıfı](../../atl/reference/csimplemapequalhelper-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
