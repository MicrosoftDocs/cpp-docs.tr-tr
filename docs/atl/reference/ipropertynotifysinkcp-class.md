---
title: Ipropertynotifysinkcp sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IPropertyNotifySinkCP
- atlctl/ATL::IPropertyNotifySinkCP
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], managing
- sinks, notifying of changes
- IPropertyNotifySinkCP class
ms.assetid: 1b41445e-bc88-4fa6-bb62-d68aacec2bd5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 66fd7b267a70b962bb5c28bb5835bd96d44a92f0
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879195"
---
# <a name="ipropertynotifysinkcp-class"></a>Ipropertynotifysinkcp sınıfı
Bu sınıf sunan [Ipropertynotifysink](http://msdn.microsoft.com/library/windows/desktop/ms692638) arabirimi bağlanılabilirlik nesnesi üzerinde giden bir arabirim olarak.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T, class CDV = CComDynamicUnkArray>  
class IPropertyNotifySinkCP 
   : public IConnectionPointImpl<T, &IID_IPropertyNotifySink, CDV>
```    
  
#### <a name="parameters"></a>Parametreler  
 *T*  
 Sınıfınız, türetilen `IPropertyNotifySinkCP`.  
  
 *CDV*  
 Bir bağlantı noktası ve onun havuz arasındaki bağlantıları yöneten bir sınıf. Varsayılan değer [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), sınırsız sayıda bağlantı sağlar. Ayrıca [CComUnkArray](../../atl/reference/ccomunkarray-class.md), sabit sayıda bağlantı belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 `IPropertyNotifySinkCP` temel sınıfı olan tüm yöntemleri devralan [Iconnectionpointımpl](../../atl/reference/iconnectionpointimpl-class.md).  
  
 [Ipropertynotifysink](http://msdn.microsoft.com/library/windows/desktop/ms692638) arabirim özellik değişiklikleri hakkında bildirim almak bir havuz nesnesi sağlar. Sınıf `IPropertyNotifySinkCP` bağlanılabilirlik nesnesi üzerinde giden bir arabirim olarak bu arabirimini kullanıma sunar. İstemci uygulamalıdır `IPropertyNotifySink` havuz yöntemleri.  
  
 Öğesinden, bir sınıf türetin `IPropertyNotifySinkCP` temsil eden bir bağlantı noktası oluşturmak istediğinizde `IPropertyNotifySink` arabirimi.  
  
 ATL bağlantı noktaları hakkında daha fazla bilgi için bkz [bağlantı noktaları](../../atl/atl-connection-points.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlctl.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Iconnectionpointımpl sınıfı](../../atl/reference/iconnectionpointimpl-class.md)   
 [Iconnectionpointcontainerımpl sınıfı](../../atl/reference/iconnectionpointcontainerimpl-class.md)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
