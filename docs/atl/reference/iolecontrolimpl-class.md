---
title: IOleControlImpl Sınıfı
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
ms.openlocfilehash: 947ec16e91b99cc42cff90abe7df4a5d13576e98
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329618"
---
# <a name="iolecontrolimpl-class"></a>IOleControlImpl Sınıfı

Bu sınıf `IOleControl` arabirimin varsayılan uygulamasını sağlar `IUnknown`ve uygular.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class IOleControlImpl
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `IOleControlImpl`türetilmiştir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IOleControlImpl::FreezeEvents](#freezeevents)|Kapsayıcının denetimden olayları yok sayıp yoksaymadığını veya kabul edip etmediğini gösterir.|
|[IOleControlImpl::GetControlInfo](#getcontrolinfo)|Denetimin klavye davranışı yla ilgili bilgileri doldurur. ATL uygulaması E_NOTIMPL döndürür.|
|[IOleControlImpl::OnAmbientPropertyChange](#onambientpropertychange)|Bir veya daha fazla kapsayıcının ortam özelliklerinin değiştiğini kontrol eder. ATL uygulaması S_OK döndürür.|
|[IOleControlImpl::OnMnemonic](#onmnemonic)|Kullanıcının belirli bir tuş vuruşuna basdığı denetimini bildirir. ATL uygulaması E_NOTIMPL döndürür.|

## <a name="remarks"></a>Açıklamalar

Sınıf, `IOleControlImpl` Hata Ayıklama yapılarında döküm aygıta `IUnknown` bilgi göndererek [IOleControl](/windows/win32/api/ocidl/nn-ocidl-iolecontrol) arabiriminin varsayılan uygulamasını sağlar ve uygular.

**İlgili Makaleler** [ATL Tutorial](../../atl/active-template-library-atl-tutorial.md), [ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IOleControl`

`IOleControlImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl.h

## <a name="iolecontrolimplfreezeevents"></a><a name="freezeevents"></a>IOleControlImpl::FreezeEvents

ATL'nin uygulamasında, `FreezeEvents` `m_nFreezeEvents` doğruysa `bFreeze` denetim sınıfının veri üyesini, FALSE `m_nFreezeEvents` `bFreeze` ise de kararları.

```
HRESULT FreezeEvents(BOOL bFreeze);
```

### <a name="remarks"></a>Açıklamalar

`FreezeEvents`sonra S_OK döndürür.

Bkz. [IOleControl::Windows](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-freezeevents) SDK'daki Olayları Dondurma.

## <a name="iolecontrolimplgetcontrolinfo"></a><a name="getcontrolinfo"></a>IOleControlImpl::GetControlInfo

Denetimin klavye davranışı yla ilgili bilgileri doldurur.

```
HRESULT GetControlInfo(LPCONTROLINFO pCI);
```

### <a name="remarks"></a>Açıklamalar

Bkz. Windows SDK'daki [IOleControl:GetControlInfo.](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-getcontrolinfo)

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

## <a name="iolecontrolimplonambientpropertychange"></a><a name="onambientpropertychange"></a>IOleControlImpl::OnAmbientPropertyChange

Bir veya daha fazla kapsayıcının ortam özelliklerinin değiştiğini kontrol eder.

```
HRESULT OnAmbientPropertyChange(DISPID dispid);
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IOleControl::Windows SDK'da OnAmbientPropertyChange.](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-onambientpropertychange)

## <a name="iolecontrolimplonmnemonic"></a><a name="onmnemonic"></a>IOleControlImpl::OnMnemonic

Kullanıcının belirli bir tuş vuruşuna basdığı denetimini bildirir.

```
HRESULT OnMnemonic(LPMSG pMsg);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IOleControl::Windows SDK'da OnMnemonic.](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-onmnemonic)

## <a name="see-also"></a>Ayrıca bkz.

[IOleObjectImpl Sınıfı](../../atl/reference/ioleobjectimpl-class.md)<br/>
[ActiveX Arayüzleri Kontrol Eder](/windows/win32/com/activex-controls-interfaces)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
