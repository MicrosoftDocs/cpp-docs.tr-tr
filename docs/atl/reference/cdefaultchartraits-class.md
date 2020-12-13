---
description: 'Daha fazla bilgi edinin: Cdefaultcharnitelikler sınıfı'
title: Cdefaultcharnitelikler sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits::CharToLower
- ATLCOLL/ATL::CDefaultCharTraits::CharToUpper
helpviewer_keywords:
- CDefaultCharTraits class
ms.assetid: f94a3934-597f-401d-8513-ed6924ae069a
ms.openlocfilehash: 6d98c6b6ffb527fef1e5b2320b46eda61ec3f670
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141966"
---
# <a name="cdefaultchartraits-class"></a>Cdefaultcharnitelikler sınıfı

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

|Ad|Açıklama|
|----------|-----------------|
|[Cdefaultcharnitelikler:: CharToLower](#chartolower)|Se Bir karakteri büyük harfe dönüştürmek için bu işlevi çağırın.|
|[Cdefaultcharnitelikler:: CharToUpper](#chartoupper)|Se Bir karakteri küçük harfe dönüştürmek için bu işlevi çağırın.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, [Cstrıngelementtraitsı](../../atl/reference/cstringelementtraitsi-class.md)sınıfı tarafından kullanılan işlevleri sağlar.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll. h

## <a name="cdefaultchartraitschartolower"></a><a name="chartolower"></a> Cdefaultcharnitelikler:: CharToLower

Bir karakteri küçük harfe dönüştürmek için bu işlevi çağırın.

```
static wchar_t CharToLower(wchar_t x);
static char CharToLower(char x);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Küçük harfe Dönüştürülecek karakter.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#132](../../atl/codesnippet/cpp/cdefaultchartraits-class_1.cpp)]

## <a name="cdefaultchartraitschartoupper"></a><a name="chartoupper"></a> Cdefaultcharnitelikler:: CharToUpper

Bir karakteri büyük harfe dönüştürmek için bu işlevi çağırın.

```
static wchar_t CharToUpper(wchar_t x);
static char CharToUpper(char x);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Büyük harfe Dönüştürülecek karakter.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
