---
description: 'Daha fazla bilgi edinin: CFirePropNotifyEvent sınıfı'
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
ms.openlocfilehash: 09102e67408195751e083807f444c1b028fd2762
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141732"
---
# <a name="cfirepropnotifyevent-class"></a>CFirePropNotifyEvent sınıfı

Bu sınıf, kapsayıcının havuzuna denetim özelliği değişiklikleriyle ilgili bildirimde bulunmak için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
class CFirePropNotifyEvent
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFirePropNotifyEvent:: FireOnChanged](#fireonchanged)|Se Kapsayıcının havuzuna bir denetim özelliği değiştiğini bildirir.|
|[CFirePropNotifyEvent:: Fireonrequestedıt](#fireonrequestedit)|Se Kapsayıcının havuzuna bir denetim özelliğinin değiştirmek üzere olduğunu bildirir.|

## <a name="remarks"></a>Açıklamalar

`CFirePropNotifyEvent` , kapsayıcının havuzuna bir denetim özelliğinin değiştiğini veya değiştirmek üzere olduğunu bildiren iki yöntem içerir.

Denetiminizi uygulayan sınıf öğesinden türetildiyse `IPropertyNotifySink` , `CFirePropNotifyEvent` veya çağırdığınızda yöntemler çağrılır `FireOnRequestEdit` `FireOnChanged` . Denetim sınıfınız öğesinden türetilmediği takdirde `IPropertyNotifySink` , bu işlevlere yapılan çağrılar s_ok döndürür.

Denetim oluşturma hakkında daha fazla bilgi için bkz. [ATL öğreticisi](../../atl/active-template-library-atl-tutorial.md).

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl. h

## <a name="cfirepropnotifyeventfireonchanged"></a><a name="fireonchanged"></a> CFirePropNotifyEvent:: FireOnChanged

Belirtilen nesne özelliğinin değiştiği tüm bağlı [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) arabirimlerini (nesnenin her bağlantı noktasında) bilgilendirir.

```
static HRESULT FireOnChanged(IUnknown* pUnk, DISPID dispID);
```

### <a name="parameters"></a>Parametreler

*pUnk dili*<br/>
'ndaki `IUnknown` Bildirimi gönderen nesnenin işaretçisi.

*Dı*<br/>
'ndaki Değiştirilen özelliğin tanımlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Denetiminiz bağlantı noktalarını desteklemeseler bile bu işlev güvenli bir şekilde çağrılamaz.

## <a name="cfirepropnotifyeventfireonrequestedit"></a><a name="fireonrequestedit"></a> CFirePropNotifyEvent:: Fireonrequestedıt

Belirtilen nesne özelliğinin değiştirmek üzere olduğu tüm bağlı [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) arabirimlerini (nesnesinin her bağlantı noktasında) bilgilendirir.

```
static HRESULT FireOnRequestEdit(IUnknown* pUnk, DISPID dispID);
```

### <a name="parameters"></a>Parametreler

*pUnk dili*<br/>
'ndaki `IUnknown` Bildirimi gönderen nesnenin işaretçisi.

*Dı*<br/>
'ndaki Değiştirilecek özelliğin tanımlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Denetiminiz bağlantı noktalarını desteklemeseler bile bu işlev güvenli bir şekilde çağrılamaz.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
