---
title: CFirePropNotifyEvent sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnChanged
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnRequestEdit
dev_langs:
- C++
helpviewer_keywords:
- sinks, notifying of ATL events
- CFirePropNotifyEvent class
- connection points [C++], notifying of events
ms.assetid: eb7a563e-6bce-4cdf-8d20-8c6a5307781b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 88c816fecf71b94d25ac676f8169eeb26a2982fc
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43760223"
---
# <a name="cfirepropnotifyevent-class"></a>CFirePropNotifyEvent sınıfı

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

*pUnk*  
[in] İşaretçi `IUnknown` bildirimi gönderilmesi nesnenin.

*dispID*  
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

*pUnk*  
[in] İşaretçi `IUnknown` bildirimi gönderilmesi nesnenin.

*dispID*  
[in] Değişmek üzere özellik tanımlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Bu işlev, denetimi bağlantı noktalarını desteklemiyor olsa bile çağrılması güvenlidir.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
