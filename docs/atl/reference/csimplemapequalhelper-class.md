---
title: CSimpleMapEqualHelper Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualValue
helpviewer_keywords:
- CSimpleMapEqualHelper class
ms.assetid: 9bb2968a-d609-405c-8272-ff3b42df6164
ms.openlocfilehash: d137a35a517ea93139f036f6e9a7a8de06d518a7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330755"
---
# <a name="csimplemapequalhelper-class"></a>CSimpleMapEqualHelper Sınıfı

Bu sınıf [CSimpleMap](../../atl/reference/csimplemap-class.md) sınıfı için bir yardımcıdır.

## <a name="syntax"></a>Sözdizimi

```
template <class TKey, class TVal>
class CSimpleMapEqualHelper
```

#### <a name="parameters"></a>Parametreler

*Tkey*<br/>
Anahtar unsur.

*TVal*<br/>
Değer öğesi.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSimpleMapEqualHelper::IsEqualKey](#isequalkey)|(Statik) Eşitlik için iki anahtar test ediyor.|
|[CSimpleMapEqualHelper::IsEqualValue](#isequalvalue)|(Statik) Eşitlik için iki değeri sınar.|

## <a name="remarks"></a>Açıklamalar

Bu özellikler sınıfı `CSimpleMap` sınıfın bir ekidir. Eşitlik için iki `CSimpleMap` nesne öğesini (özellikle anahtar ve değer bileşenleri) karşılaştırma yöntemleri sağlar. Varsayılan olarak, anahtarlar ve değerler **işleç==()** kullanılarak karşılaştırılır, ancak harita kendi eşitlik işleci olmayan karmaşık veri türleri içeriyorsa, bu sınıf gerekli ekstra işlevselliği sağlamak için geçersiz kılınabilir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsimpcoll.h

## <a name="csimplemapequalhelperisequalkey"></a><a name="isequalkey"></a>CSimpleMapEqualHelper::IsEqualKey

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

## <a name="csimplemapequalhelperisequalvalue"></a><a name="isequalvalue"></a>CSimpleMapEqualHelper::IsEqualValue

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

Değerler eşitse doğru döndürür, aksi takdirde yanlış.

## <a name="see-also"></a>Ayrıca bkz.

[CSimpleMapEqualHelperFalse Sınıfı](../../atl/reference/csimplemapequalhelperfalse-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
