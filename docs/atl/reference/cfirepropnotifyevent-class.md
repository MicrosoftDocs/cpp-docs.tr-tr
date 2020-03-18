---
title: CFirePropNotifyEvent sınıfı
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
ms.openlocfilehash: 694127ceccc1d1b55e5da9abca799dff77dcfc60
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79417868"
---
# <a name="cfirepropnotifyevent-class"></a>CFirePropNotifyEvent sınıfı

Bu sınıf, kapsayıcının havuzuna denetim özelliği değişiklikleriyle ilgili bildirimde bulunmak için yöntemler sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CFirePropNotifyEvent
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Genel Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CFirePropNotifyEvent:: FireOnChanged](#fireonchanged)|Se Kapsayıcının havuzuna bir denetim özelliği değiştiğini bildirir.|
|[CFirePropNotifyEvent:: Fireonrequestedıt](#fireonrequestedit)|Se Kapsayıcının havuzuna bir denetim özelliğinin değiştirmek üzere olduğunu bildirir.|

## <a name="remarks"></a>Açıklamalar

`CFirePropNotifyEvent`, kapsayıcının havuzuna bir denetim özelliğinin değiştiğini veya değiştirmek üzere olduğunu bildiren iki yöntem içerir.

Denetiminizi uygulayan sınıf `IPropertyNotifySink`türetildiyse, `FireOnRequestEdit` veya `FireOnChanged`çağırdığınızda `CFirePropNotifyEvent` yöntemleri çağrılır. Denetim sınıfınız `IPropertyNotifySink`türetilmediği takdirde, bu işlevlere yapılan çağrılar S_OK döndürür.

Denetim oluşturma hakkında daha fazla bilgi için bkz. [ATL öğreticisi](../../atl/active-template-library-atl-tutorial.md).

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl. h

##  <a name="fireonchanged"></a>CFirePropNotifyEvent:: FireOnChanged

Belirtilen nesne özelliğinin değiştiği tüm bağlı [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) arabirimlerini (nesnenin her bağlantı noktasında) bilgilendirir.

```
static HRESULT FireOnChanged(IUnknown* pUnk, DISPID dispID);
```

### <a name="parameters"></a>Parametreler

*pUnk dili*<br/>
'ndaki Bildirimi gönderen nesnenin `IUnknown` işaretçisi.

*Dı*<br/>
'ndaki Değiştirilen özelliğin tanımlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Denetiminiz bağlantı noktalarını desteklemeseler bile bu işlev güvenli bir şekilde çağrılamaz.

##  <a name="fireonrequestedit"></a>CFirePropNotifyEvent:: Fireonrequestedıt

Belirtilen nesne özelliğinin değiştirmek üzere olduğu tüm bağlı [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) arabirimlerini (nesnesinin her bağlantı noktasında) bilgilendirir.

```
static HRESULT FireOnRequestEdit(IUnknown* pUnk, DISPID dispID);
```

### <a name="parameters"></a>Parametreler

*pUnk dili*<br/>
'ndaki Bildirimi gönderen nesnenin `IUnknown` işaretçisi.

*Dı*<br/>
'ndaki Değiştirilecek özelliğin tanımlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Denetiminiz bağlantı noktalarını desteklemeseler bile bu işlev güvenli bir şekilde çağrılamaz.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
