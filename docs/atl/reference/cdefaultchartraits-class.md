---
title: CDefaultCharTraits sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits::CharToLower
- ATLCOLL/ATL::CDefaultCharTraits::CharToUpper
helpviewer_keywords:
- CDefaultCharTraits class
ms.assetid: f94a3934-597f-401d-8513-ed6924ae069a
ms.openlocfilehash: fe599ee0e84c393bed656b7304fd13d55ce95a50
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57296117"
---
# <a name="cdefaultchartraits-class"></a>CDefaultCharTraits sınıfı

Bu sınıf, büyük ve küçük arasındaki karakter dönüştürme için iki statik işlevler sağlar.

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
|[CDefaultCharTraits::CharToLower](#chartolower)|(Statik) Bir karakteri büyük harfe dönüştürmek için bu işlevi çağırın.|
|[CDefaultCharTraits::CharToUpper](#chartoupper)|(Statik) Bir karakteri küçük harfe dönüştürmek için bu işlevi çağırın.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf sınıf tarafından kullanılan işlevler sağlar [Cstringelementtraitsı](../../atl/reference/cstringelementtraitsi-class.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcoll.h

##  <a name="chartolower"></a>  CDefaultCharTraits::CharToLower

Bir karakteri küçük harfe dönüştürmek için bu işlevi çağırın.

```
static wchar_t CharToLower(wchar_t x);
static char CharToLower(char x);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Küçük harfe dönüştürülecek karakter.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#132](../../atl/codesnippet/cpp/cdefaultchartraits-class_1.cpp)]

##  <a name="chartoupper"></a>  CDefaultCharTraits::CharToUpper

Bir karakteri büyük harfe dönüştürmek için bu işlevi çağırın.

```
static wchar_t CharToUpper(wchar_t x);
static char CharToUpper(char x);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Büyük harfe dönüştürülecek karakter.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
