---
title: CSimpleMapEqualHelper sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualValue
helpviewer_keywords:
- CSimpleMapEqualHelper class
ms.assetid: 9bb2968a-d609-405c-8272-ff3b42df6164
ms.openlocfilehash: a530254bbaabce723b97d21313abb81e1b375833
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50527399"
---
# <a name="csimplemapequalhelper-class"></a>CSimpleMapEqualHelper sınıfı

Bu sınıf için Yardımcısı, [CSimpleMap](../../atl/reference/csimplemap-class.md) sınıfı.

## <a name="syntax"></a>Sözdizimi

```
template <class TKey, class TVal>
class CSimpleMapEqualHelper
```

#### <a name="parameters"></a>Parametreler

*TKey*<br/>
Anahtar öğesi.

*TVal*<br/>
Değer öğesi.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleMapEqualHelper::IsEqualKey](#isequalkey)|(Statik) İki anahtar eşitlik için test eder.|
|[CSimpleMapEqualHelper::IsEqualValue](#isequalvalue)|(Statik) Eşitlik için iki değeri test eder.|

## <a name="remarks"></a>Açıklamalar

Bu nitelikler sınıfı için bir ektir `CSimpleMap` sınıfı. İki karşılaştırma yöntemlerini sağlar `CSimpleMap` nesne eşitliği (özellikle, anahtar ve değer bileşenleri) öğeleri. Varsayılan olarak, anahtarları ve değerleri kullanılarak karşılaştırılır **operator==()**, ancak fazladan gerekli işlevselliği sağlamak için eşleme eksik kendi eşitlik işleci karmaşık veri türleri içeriyorsa, bu sınıf kılınabilir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsimpcoll.h

##  <a name="isequalkey"></a>  CSimpleMapEqualHelper::IsEqualKey

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

##  <a name="isequalvalue"></a>  CSimpleMapEqualHelper::IsEqualValue

Eşitlik için iki değeri test eder.

```
static bool IsEqualValue(const TVal& v1, const TVal& v2);
```

### <a name="parameters"></a>Parametreler

*V1*<br/>
İlk değer.

*v2*<br/>
İkinci değer.

### <a name="return-value"></a>Dönüş Değeri

Değerler yanlış Aksi takdirde, eşitse true döndürür.

## <a name="see-also"></a>Ayrıca Bkz.

[CSimpleMapEqualHelperFalse Sınıfı](../../atl/reference/csimplemapequalhelperfalse-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
