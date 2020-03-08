---
title: IOleControlImpl sınıfı
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
ms.openlocfilehash: 3bdb501d8210c98ce982719358564c4937991e12
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78864975"
---
# <a name="iolecontrolimpl-class"></a>IOleControlImpl sınıfı

Bu sınıf `IOleControl` arabiriminin varsayılan bir uygulamasını sağlar ve `IUnknown`uygular.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class IOleControlImpl
```

#### <a name="parameters"></a>Parametreler

*Şı*<br/>
Sınıfınız `IOleControlImpl`türetilir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IOleControlImpl:: FreezeEvents](#freezeevents)|Kapsayıcının denetimden olayları yoksayıp saymayacağını veya kabul etmeyeceğini belirtir.|
|[IOleControlImpl:: Getcontrolinınfo](#getcontrolinfo)|Denetimin klavye davranışı hakkında bilgi doldurur. ATL uygulama E_NOTIMPL döndürür.|
|[IOleControlImpl:: OnAmbientPropertyChange](#onambientpropertychange)|Bir veya daha fazla kapsayıcının çevresel özelliklerinin değiştiğini bir denetime bildirir. ATL uygulama S_OK döndürür.|
|[IOleControlImpl:: Onanımsatıcı](#onmnemonic)|Denetimi bir kullanıcının belirli bir tuş vuruşunu bastığını bildirir. ATL uygulama E_NOTIMPL döndürür.|

## <a name="remarks"></a>Açıklamalar

Sınıf `IOleControlImpl`, [IOleControl](/windows/win32/api/ocidl/nn-ocidl-iolecontrol) arabiriminin varsayılan bir uygulamasını sağlar ve hata ayıklama yapılarında döküm cihazına bilgi göndererek `IUnknown` uygular.

**Ilgili makaleler** [ATL öğreticisi](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IOleControl`

`IOleControlImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl. h

##  <a name="freezeevents"></a>IOleControlImpl:: FreezeEvents

ATL 'nin uygulamasında `FreezeEvents`, `bFreeze` TRUE ise denetim sınıfının `m_nFreezeEvents` veri üyesini artırır ve `bFreeze` FALSE ise `m_nFreezeEvents` azaltır.

```
HRESULT FreezeEvents(BOOL bFreeze);
```

### <a name="remarks"></a>Açıklamalar

`FreezeEvents` S_OK döndürür.

Windows SDK için bkz. [IOleControl:: FreezeEvents](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-freezeevents) .

##  <a name="getcontrolinfo"></a>IOleControlImpl:: Getcontrolinınfo

Denetimin klavye davranışı hakkında bilgi doldurur.

```
HRESULT GetControlInfo(LPCONTROLINFO pCI);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. [IOleControl: Getcontrolinınfo](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-getcontrolinfo) .

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

##  <a name="onambientpropertychange"></a>IOleControlImpl:: OnAmbientPropertyChange

Bir veya daha fazla kapsayıcının çevresel özelliklerinin değiştiğini bir denetime bildirir.

```
HRESULT OnAmbientPropertyChange(DISPID dispid);
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK için bkz. [IOleControl:: OnAmbientPropertyChange](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-onambientpropertychange) .

##  <a name="onmnemonic"></a>IOleControlImpl:: Onanımsatıcı

Denetimi bir kullanıcının belirli bir tuş vuruşunu bastığını bildirir.

```
HRESULT OnMnemonic(LPMSG pMsg);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK için bkz. [IOleControl:: Onanımsatıcı](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-onmnemonic) .

## <a name="see-also"></a>Ayrıca bkz.

[IOleObjectImpl Sınıfı](../../atl/reference/ioleobjectimpl-class.md)<br/>
[ActiveX denetimleri arabirimleri](/windows/win32/com/activex-controls-interfaces)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
