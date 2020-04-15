---
title: CDefaultCharTraits Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits::CharToLower
- ATLCOLL/ATL::CDefaultCharTraits::CharToUpper
helpviewer_keywords:
- CDefaultCharTraits class
ms.assetid: f94a3934-597f-401d-8513-ed6924ae069a
ms.openlocfilehash: 40c4d107d05e6d7b610e7c46be920d91d8fe6086
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327102"
---
# <a name="cdefaultchartraits-class"></a>CDefaultCharTraits Sınıfı

Bu sınıf, büyük harf ve küçük harf arasında karakterleri dönüştürmek için iki statik işlev sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <typename T>
class CDefaultCharTraits
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Koleksiyonda depolanacak veri türü.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CdefaultChartraits::Chartolower](#chartolower)|(Statik) Bir karakteri büyük harfe dönüştürmek için bu işlevi arayın.|
|[CdefaultChartraits::Chartoupper](#chartoupper)|(Statik) Bir karakteri küçük harfe dönüştürmek için bu işlevi arayın.|

## <a name="remarks"></a>Açıklamalar

Bu [sınıf, CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)sınıfı tarafından kullanılan işlevleri sağlar.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll.h

## <a name="cdefaultchartraitschartolower"></a><a name="chartolower"></a>CdefaultChartraits::Chartolower

Bir karakteri küçük harfe dönüştürmek için bu işlevi arayın.

```
static wchar_t CharToLower(wchar_t x);
static char CharToLower(char x);
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Küçük harfe dönüştürülecek karakter.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#132](../../atl/codesnippet/cpp/cdefaultchartraits-class_1.cpp)]

## <a name="cdefaultchartraitschartoupper"></a><a name="chartoupper"></a>CdefaultChartraits::Chartoupper

Bir karakteri büyük harfe dönüştürmek için bu işlevi arayın.

```
static wchar_t CharToUpper(wchar_t x);
static char CharToUpper(char x);
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Büyük harfe dönüştürülecek karakter.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
