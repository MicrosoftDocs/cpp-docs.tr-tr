---
title: Iolecontrolımpl sınıfı
ms.date: 11/04/2016
f1_keywords:
- IOleControlImpl
- ATLCTL/ATL::IOleControlImpl
- ATLCTL/ATL::IOleControlImpl::FreezeEvents
- ATLCTL/ATL::IOleControlImpl::GetControlInfo
- ATLCTL/ATL::IOleControlImpl::OnAmbientPropertyChange
- ATLCTL/ATL::IOleControlImpl::OnMnemonic
helpviewer_keywords:
- IOleControlImpl class
ms.assetid: 5a4255ad-ede4-49ca-ba9a-07c2e919fa85
ms.openlocfilehash: 50119d21b041f37f03ca416a9a56ca9e29ae3344
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62276802"
---
# <a name="iolecontrolimpl-class"></a>Iolecontrolımpl sınıfı

Bu sınıfın bir varsayılan uygulamayı sağlar `IOleControl` uygular ve arabirimi `IUnknown`.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class IOleControlImpl
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, türetilen `IOleControlImpl`.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IOleControlImpl::FreezeEvents](#freezeevents)|Kapsayıcı yoksayar veya denetim olayları kabul olup olmadığını gösterir.|
|[IOleControlImpl::GetControlInfo](#getcontrolinfo)|Denetimin klavye davranışı hakkında bilgi doldurur. ATL uygulamasını E_NOTIMPL döndürür.|
|[IOleControlImpl::OnAmbientPropertyChange](#onambientpropertychange)|Bir denetimi bir veya daha fazla kapsayıcının ortam özellikleri değiştiğini bildirir. ATL uygulamasını S_OK döndürür.|
|[IOleControlImpl::OnMnemonic](#onmnemonic)|Denetim, bir kullanıcının belirtilen bir tuş vuruşu bastığına bildirir. ATL uygulamasını E_NOTIMPL döndürür.|

## <a name="remarks"></a>Açıklamalar

Sınıf `IOleControlImpl` bir varsayılan uygulamayı sağlar [IOleControl](/windows/desktop/api/ocidl/nn-ocidl-iolecontrol) arabirimi ve uygular `IUnknown` dökümünü almak için bilgi göndererek hata ayıklama cihazı oluşturur.

**İle ilgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IOleControl`

`IOleControlImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlctl.h

##  <a name="freezeevents"></a>  IOleControlImpl::FreezeEvents

ATL'nin uygulamasında `FreezeEvents` denetim sınıfın artırır `m_nFreezeEvents` veri üyesi değilse `bFreeze` TRUE ve azaltır `m_nFreezeEvents` varsa `bFreeze` yanlış.

```
HRESULT FreezeEvents(BOOL bFreeze);
```

### <a name="remarks"></a>Açıklamalar

`FreezeEvents` ardından S_OK döndürür.

Bkz: [Iolecontrol::freezeevents](/windows/desktop/api/ocidl/nf-ocidl-iolecontrol-freezeevents) Windows SDK içinde.

##  <a name="getcontrolinfo"></a>  IOleControlImpl::GetControlInfo

Denetimin klavye davranışı hakkında bilgi doldurur.

```
HRESULT GetControlInfo(LPCONTROLINFO pCI);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IOleControl:GetControlInfo](/windows/desktop/api/ocidl/nf-ocidl-iolecontrol-getcontrolinfo) Windows SDK içinde.

### <a name="return-value"></a>Dönüş Değeri

Returns E_NOTIMPL.

##  <a name="onambientpropertychange"></a>  IOleControlImpl::OnAmbientPropertyChange

Bir denetimi bir veya daha fazla kapsayıcının ortam özellikleri değiştiğini bildirir.

```
HRESULT OnAmbientPropertyChange(DISPID dispid);
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz: [IOleControl::OnAmbientPropertyChange](/windows/desktop/api/ocidl/nf-ocidl-iolecontrol-onambientpropertychange) Windows SDK içinde.

##  <a name="onmnemonic"></a>  IOleControlImpl::OnMnemonic

Denetim, bir kullanıcının belirtilen bir tuş vuruşu bastığına bildirir.

```
HRESULT OnMnemonic(LPMSG pMsg);
```

### <a name="return-value"></a>Dönüş Değeri

Returns E_NOTIMPL.

### <a name="remarks"></a>Açıklamalar

Bkz: [IOleControl::OnMnemonic](/windows/desktop/api/ocidl/nf-ocidl-iolecontrol-onmnemonic) Windows SDK içinde.

## <a name="see-also"></a>Ayrıca bkz.

[IOleObjectImpl Sınıfı](../../atl/reference/ioleobjectimpl-class.md)<br/>
[Arabirimleri ActiveX denetimleri](/windows/desktop/com/activex-controls-interfaces)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
