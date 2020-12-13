---
description: 'Daha fazla bilgi edinin: IOleControlImpl sınıfı'
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
ms.openlocfilehash: e224f6f8db79c05cb8a774cd57517ba06108e592
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139431"
---
# <a name="iolecontrolimpl-class"></a>IOleControlImpl sınıfı

Bu sınıf, arabiriminin varsayılan bir uygulamasını sağlar `IOleControl` ve uygular `IUnknown` .

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class IOleControlImpl
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, öğesinden türetilir `IOleControlImpl` .

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IOleControlImpl:: FreezeEvents](#freezeevents)|Kapsayıcının denetimden olayları yoksayıp saymayacağını veya kabul etmeyeceğini belirtir.|
|[IOleControlImpl:: Getcontrolinınfo](#getcontrolinfo)|Denetimin klavye davranışı hakkında bilgi doldurur. ATL uygulama E_NOTIMPL döndürür.|
|[IOleControlImpl:: OnAmbientPropertyChange](#onambientpropertychange)|Bir veya daha fazla kapsayıcının çevresel özelliklerinin değiştiğini bir denetime bildirir. ATL uygulama S_OK döndürür.|
|[IOleControlImpl:: Onanımsatıcı](#onmnemonic)|Denetimi bir kullanıcının belirli bir tuş vuruşunu bastığını bildirir. ATL uygulama E_NOTIMPL döndürür.|

## <a name="remarks"></a>Açıklamalar

Sınıfı `IOleControlImpl` , [IOleControl](/windows/win32/api/ocidl/nn-ocidl-iolecontrol) arabiriminin varsayılan bir uygulamasını sağlar ve `IUnknown` hata ayıklama yapılarında döküm cihazına bilgi göndererek uygular.

**Ilgili makaleler** [ATL öğreticisi](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IOleControl`

`IOleControlImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl. h

## <a name="iolecontrolimplfreezeevents"></a><a name="freezeevents"></a> IOleControlImpl:: FreezeEvents

ATL 'nin uygulamasında, `FreezeEvents` true ise denetim sınıfının `m_nFreezeEvents` veri üyesini ARTıRıR ve yanlış ise bu değeri `bFreeze` azaltır `m_nFreezeEvents` `bFreeze` .

```
HRESULT FreezeEvents(BOOL bFreeze);
```

### <a name="remarks"></a>Açıklamalar

`FreezeEvents` sonra S_OK döndürür.

Windows SDK için bkz. [IOleControl:: FreezeEvents](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-freezeevents) .

## <a name="iolecontrolimplgetcontrolinfo"></a><a name="getcontrolinfo"></a> IOleControlImpl:: Getcontrolinınfo

Denetimin klavye davranışı hakkında bilgi doldurur.

```
HRESULT GetControlInfo(LPCONTROLINFO pCI);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. [IOleControl: Getcontrolinınfo](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-getcontrolinfo) .

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

## <a name="iolecontrolimplonambientpropertychange"></a><a name="onambientpropertychange"></a> IOleControlImpl:: OnAmbientPropertyChange

Bir veya daha fazla kapsayıcının çevresel özelliklerinin değiştiğini bir denetime bildirir.

```
HRESULT OnAmbientPropertyChange(DISPID dispid);
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK için bkz. [IOleControl:: OnAmbientPropertyChange](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-onambientpropertychange) .

## <a name="iolecontrolimplonmnemonic"></a><a name="onmnemonic"></a> IOleControlImpl:: Onanımsatıcı

Denetimi bir kullanıcının belirli bir tuş vuruşunu bastığını bildirir.

```
HRESULT OnMnemonic(LPMSG pMsg);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK için bkz. [IOleControl:: Onanımsatıcı](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-onmnemonic) .

## <a name="see-also"></a>Ayrıca bkz.

[IOleObjectImpl sınıfı](../../atl/reference/ioleobjectimpl-class.md)<br/>
[ActiveX denetimleri arabirimleri](/windows/win32/com/activex-controls-interfaces)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
