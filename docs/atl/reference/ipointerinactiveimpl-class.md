---
title: Ipoıb ınterınactiveımpl sınıfı
ms.date: 11/04/2016
f1_keywords:
- IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl::GetActivationPolicy
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveMouseMove
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveSetCursor
helpviewer_keywords:
- IPointerInactive ATL implementation
- inactive objects
- IPointerInactiveImpl class
ms.assetid: e1fe9ea6-d38a-4527-9112-eb344771e0b7
ms.openlocfilehash: 6fb5d9f2bcbdeda61f32947bf339d134c4924b72
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495663"
---
# <a name="ipointerinactiveimpl-class"></a>Ipoıb ınterınactiveımpl sınıfı

Bu sınıf ve `IUnknown` , [ıpoıb etkin olmayan](/windows/win32/api/ocidl/nn-ocidl-ipointerinactive) arabirim yöntemlerini uygular.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class IPointerInactiveImpl
```

#### <a name="parameters"></a>Parametreler

*ŞI*<br/>
Sınıfınız, öğesinden `IPointerInactiveImpl`türetilir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Ipoıb ınterınactiveımpl:: GetActivationPolicy](#getactivationpolicy)|Nesne için geçerli etkinleştirme ilkesini alır. ATL uygulama E_NOTIMPL döndürür.|
|[Ipoıb ınterınactiveımpl:: OnInactiveMouseMove](#oninactivemousemove)|Nesnenin fare olaylarını tetiktabileceğini belirten nesne, fare işaretçisinin üzerine taşındığını bildirir. ATL uygulama E_NOTIMPL döndürür.|
|[Ipoıb ınterınactiveımpl:: OnInactiveSetCursor](#oninactivesetcursor)|Etkin olmayan nesne için fare işaretçisini ayarlar. ATL uygulama E_NOTIMPL döndürür.|

## <a name="remarks"></a>Açıklamalar

Etkin olmayan bir nesne, yalnızca yüklenen veya çalışan bir nesnedir. Etkin bir nesneden farklı olarak, etkin olmayan bir nesne Windows fare ve klavye iletilerini alamaz. Bu nedenle, etkin olmayan nesneler daha az kaynak kullanır ve genellikle daha etkilidir.

[Ipoıb devre dışı](/windows/win32/api/ocidl/nn-ocidl-ipointerinactive) arabirimi, bir nesnenin, etkin olmadığında en düşük düzeyde fare etkileşimini desteklemesini sağlar. Bu işlevsellik özellikle denetimler için yararlıdır.

Sınıfı `IPointerInactiveImpl` ,`IPointerInactive` yöntemleri yalnızca E_NOTIMPL döndürerek uygular. Ancak, hata ayıklama `IUnknown` yapılarında döküm cihazına bilgi göndererek uygular.

**Ilgili makaleler** ATL [öğreticisi](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IPointerInactive`

`IPointerInactiveImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl. h

##  <a name="getactivationpolicy"></a>Ipoıb ınterınactiveımpl:: GetActivationPolicy

Nesne için geçerli etkinleştirme ilkesini alır.

```
HRESULT GetActivationPolicy(DWORD* pdwPolicy);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. [ıpoıb INTERACTIVE:: GetActivationPolicy](/windows/win32/api/ocidl/nf-ocidl-ipointerinactive-getactivationpolicy) .

##  <a name="oninactivemousemove"></a>Ipoıb ınterınactiveımpl:: OnInactiveMouseMove

Nesnenin fare olaylarını tetiktabileceğini belirten nesne, fare işaretçisinin üzerine taşındığını bildirir.

```
HRESULT OnInactiveMouseMove(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK için bkz. [ıpoıb INTERACTIVE:: OnInactiveMouseMove](/windows/win32/api/ocidl/nf-ocidl-ipointerinactive-oninactivemousemove) .

##  <a name="oninactivesetcursor"></a>Ipoıb ınterınactiveımpl:: OnInactiveSetCursor

Etkin olmayan nesne için fare işaretçisini ayarlar.

```
HRESULT OnInactiveSetCursor(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg,
    BOOL fSetAlways);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. ' de [ıpoıb INTERACTIVE:: OnInactiveSetCursor](/windows/win32/api/ocidl/nf-ocidl-ipointerinactive-oninactivesetcursor) .

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
