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
ms.openlocfilehash: 728f4e973a7ef74dcdbb44150375df235e0d990e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360994"
---
# <a name="cfirepropnotifyevent-class"></a>CFirePropNotifyEvent sınıfı
Bu sınıf kapsayıcının havuz denetim özelliği değişiklikleri ile ilgili bilgilendirmek için yöntemleri sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CFirePropNotifyEvent
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFirePropNotifyEvent::FireOnChanged](#fireonchanged)|(Statik) Bir denetim özelliği değişti kapsayıcının havuz bildirir.|  
|[CFirePropNotifyEvent::FireOnRequestEdit](#fireonrequestedit)|(Statik) Bir denetim değiştirilmek özelliktir kapsayıcının havuz bildirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CFirePropNotifyEvent` bir denetim özelliğini değiştirildi veya değiştirilmek kapsayıcının havuz bildir iki yöntem vardır.  
  
 Denetim uygulayan sınıfa türetilir varsa `IPropertyNotifySink`, `CFirePropNotifyEvent` yöntemlerini çağırdığınızda çağrılır `FireOnRequestEdit` veya `FireOnChanged`. Denetim sınıfınıza türetilmedi varsa `IPropertyNotifySink`, bu işlevler çağrıları dönmek `S_OK`.  
  
 Denetimler oluşturma hakkında daha fazla bilgi için bkz: [ATL öğretici](../../atl/active-template-library-atl-tutorial.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlctl.h  
  
##  <a name="fireonchanged"></a>  CFirePropNotifyEvent::FireOnChanged  
 Tüm bildirir bağlı [Ipropertynotifysink](http://msdn.microsoft.com/library/windows/desktop/ms692638) belirtilen nesne özelliği değişen arabirimlerde (nesnenin her bağlantı noktası).  
  
```
static HRESULT FireOnChanged(IUnknown* pUnk, DISPID dispID);
```  
  
### <a name="parameters"></a>Parametreler  
 *pUnk*  
 [in] İşaretçi **IUnknown** bildirim göndererek nesnesi.  
  
 *dispID*  
 [in] Değişti özellik tanımlayıcısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart birini `HRESULT` değerleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, denetim bağlantı noktalarını desteklemiyor olsa bile çağrılması güvenlidir.  
  
##  <a name="fireonrequestedit"></a>  CFirePropNotifyEvent::FireOnRequestEdit  
 Tüm bildirir bağlı [Ipropertynotifysink](http://msdn.microsoft.com/library/windows/desktop/ms692638) değiştirilmek üzere belirtilen nesne özelliği olan arabirimlerde (nesnenin her bağlantı noktası).  
  
```
static HRESULT FireOnRequestEdit(IUnknown* pUnk, DISPID dispID);
```  
  
### <a name="parameters"></a>Parametreler  
 *pUnk*  
 [in] İşaretçi **IUnknown** bildirim göndererek nesnesi.  
  
 *dispID*  
 [in] Değiştirilmek özellik tanımlayıcısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart birini `HRESULT` değerleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, denetim bağlantı noktalarını desteklemiyor olsa bile çağrılması güvenlidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
