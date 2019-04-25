---
title: CFirePropNotifyEvent Class
ms.date: 11/04/2016
f1_keywords:
- CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnChanged
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnRequestEdit
helpviewer_keywords:
- sinks, notifying of ATL events
- CFirePropNotifyEvent class
- connection points [C++], notifying of events
ms.assetid: eb7a563e-6bce-4cdf-8d20-8c6a5307781b
ms.openlocfilehash: 493bc00708d031f1bf7a4eb74d56e927a9c3f1dd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245497"
---
# <a name="cfirepropnotifyevent-class"></a>CFirePropNotifyEvent Class

Bu sınıfın sağladığı yöntemlerle kapsayıcının havuz denetimi özellik değişiklikleri ile ilgili bilgilendirme.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CFirePropNotifyEvent
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFirePropNotifyEvent::FireOnChanged](#fireonchanged)|(Statik) Denetimine özelliğin değiştirildiğini kapsayıcının havuz bildirir.|
|[CFirePropNotifyEvent::FireOnRequestEdit](#fireonrequestedit)|(Statik) Kapsayıcının havuz, bir denetim özelliği değişmek üzere olduğunu bildirir.|

## <a name="remarks"></a>Açıklamalar

`CFirePropNotifyEvent` bir denetim özelliği değiştirildi veya değiştirilmek kapsayıcının havuz bildir iki yöntem vardır.

Denetiminiz uygulayan bir sınıfa türetilir, `IPropertyNotifySink`, `CFirePropNotifyEvent` yöntemlerini çağırdığınızda çağrılır `FireOnRequestEdit` veya `FireOnChanged`. Denetim sınıfınıza türünden türetilmediğinden varsa `IPropertyNotifySink`, bu işlevlere aramaların S_OK döndürür.

Denetimler oluşturma hakkında daha fazla bilgi için bkz. [ATL öğretici](../../atl/active-template-library-atl-tutorial.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlctl.h

##  <a name="fireonchanged"></a>  CFirePropNotifyEvent::FireOnChanged

Tüm bildirir bağlı [Ipropertynotifysink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) belirtilen nesne özelliğin değiştirildiğini arabirimleri (üzerinde nesnenin her bağlantı noktası).

```
static HRESULT FireOnChanged(IUnknown* pUnk, DISPID dispID);
```

### <a name="parameters"></a>Parametreler

*pUnk*<br/>
[in] İşaretçi `IUnknown` bildirimi gönderilmesi nesnenin.

*dispID*<br/>
[in] Değişen özellik tanımlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Bu işlev, denetimi bağlantı noktalarını desteklemiyor olsa bile çağrılması güvenlidir.

##  <a name="fireonrequestedit"></a>  CFirePropNotifyEvent::FireOnRequestEdit

Tüm bildirir bağlı [Ipropertynotifysink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) değiştirilmek üzere belirtilen nesne özelliği olan arabirimleri (üzerinde nesnenin her bağlantı noktası).

```
static HRESULT FireOnRequestEdit(IUnknown* pUnk, DISPID dispID);
```

### <a name="parameters"></a>Parametreler

*pUnk*<br/>
[in] İşaretçi `IUnknown` bildirimi gönderilmesi nesnenin.

*dispID*<br/>
[in] Değişmek üzere özellik tanımlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Bu işlev, denetimi bağlantı noktalarını desteklemiyor olsa bile çağrılması güvenlidir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
