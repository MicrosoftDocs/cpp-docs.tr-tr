---
description: 'Daha fazla bilgi edinin: CSimpleMapEqualHelper sınıfı'
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
ms.openlocfilehash: 2b8ff742bf24b6c6c4354cef652e3fc697ffb1d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140614"
---
# <a name="csimplemapequalhelper-class"></a>CSimpleMapEqualHelper sınıfı

Bu sınıf, [CSimpleMap](../../atl/reference/csimplemap-class.md) sınıfı için bir yardımcıdır.

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
|[CSimpleMapEqualHelper:: IsEqualKey](#isequalkey)|Se Eşitlik için iki anahtarı sınar.|
|[CSimpleMapEqualHelper:: IsEqualValue](#isequalvalue)|Se Eşitlik için iki değeri sınar.|

## <a name="remarks"></a>Açıklamalar

Bu nitelikler sınıfı, sınıfına bir ektir `CSimpleMap` . İki `CSimpleMap` nesne öğesini (özellikle, anahtar ve değer bileşenlerini) eşitlik için karşılaştırmak için yöntemler sağlar. Varsayılan olarak, anahtarlar ve değerler **operator = = ()** kullanılarak karşılaştırılır, ancak haritada kendi eşitlik operatörü olmayan karmaşık veri türleri varsa, bu sınıf ek gerekli işlevselliği sağlamak için geçersiz kılınabilir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsimpcoll. h

## <a name="csimplemapequalhelperisequalkey"></a><a name="isequalkey"></a> CSimpleMapEqualHelper:: IsEqualKey

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

## <a name="csimplemapequalhelperisequalvalue"></a><a name="isequalvalue"></a> CSimpleMapEqualHelper:: IsEqualValue

Eşitlik için iki değeri sınar.

```
static bool IsEqualValue(const TVal& v1, const TVal& v2);
```

### <a name="parameters"></a>Parametreler

*v1*<br/>
İlk değer.

*v2*<br/>
İkinci değer.

### <a name="return-value"></a>Dönüş Değeri

Değerler eşitse true, değilse false döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CSimpleMapEqualHelperFalse sınıfı](../../atl/reference/csimplemapequalhelperfalse-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
