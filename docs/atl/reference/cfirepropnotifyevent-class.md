---
title: CFirePropNotifyEvent Sınıfı
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
ms.openlocfilehash: 1dfce42176341d74ffc7d9b42f856e71b17bf4f5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326963"
---
# <a name="cfirepropnotifyevent-class"></a>CFirePropNotifyEvent Sınıfı

Bu sınıf, denetim özelliği değişiklikleri ile ilgili kapsayıcının lavabo bildirmek için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CFirePropNotifyEvent
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CfirepropnotifyOlay::fireonchanged](#fireonchanged)|(Statik) Konteynerin lavabosuna bir denetim özelliğinin değiştiğini haber vetir.|
|[CFirePropNotifyOlay::FireOnRequestedit](#fireonrequestedit)|(Statik) Konteynerin lavabosuna bir kontrol özelliğinin değişmek üzere olduğunu haber vetir.|

## <a name="remarks"></a>Açıklamalar

`CFirePropNotifyEvent`bir denetim özelliğinin değiştiğini veya değişmek üzere olduğunu kapsayıcının lavabosuna bildiren iki yöntem vardır.

Denetiminizi `IPropertyNotifySink`uygulayan sınıf türetilmişse, `CFirePropNotifyEvent` yöntemleri çağırdığınızda `FireOnRequestEdit` veya `FireOnChanged`. Denetim sınıfınız türetilmiş `IPropertyNotifySink`değilse, bu işlevlere yapılan çağrılar S_OK döndürün.

Denetim oluşturma hakkında daha fazla bilgi için [ATL Tutorial'a](../../atl/active-template-library-atl-tutorial.md)bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl.h

## <a name="cfirepropnotifyeventfireonchanged"></a><a name="fireonchanged"></a>CfirepropnotifyOlay::fireonchanged

Belirtilen nesne özelliğinin değiştiğini tüm bağlı [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) arabirimlerini (nesnenin her bağlantı noktasında) bildirir.

```
static HRESULT FireOnChanged(IUnknown* pUnk, DISPID dispID);
```

### <a name="parameters"></a>Parametreler

*Punk*<br/>
[içinde] Bildirimi gönderen `IUnknown` nesnenin işaretçisi.

*Dıspıd*<br/>
[içinde] Değiştirilen özelliğin tanımlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Denetiminiz bağlantı noktalarını desteklemese bile bu işlevin çağrılması güvenlidir.

## <a name="cfirepropnotifyeventfireonrequestedit"></a><a name="fireonrequestedit"></a>CFirePropNotifyOlay::FireOnRequestedit

Belirtilen nesne özelliğinin değişmek üzere olduğunu tüm bağlı [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) arabirimleri (nesnenin her bağlantı noktasında) bildirir.

```
static HRESULT FireOnRequestEdit(IUnknown* pUnk, DISPID dispID);
```

### <a name="parameters"></a>Parametreler

*Punk*<br/>
[içinde] Bildirimi gönderen `IUnknown` nesnenin işaretçisi.

*Dıspıd*<br/>
[içinde] Değişmek üzere olan özelliğin tanımlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Denetiminiz bağlantı noktalarını desteklemese bile bu işlevin çağrılması güvenlidir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
