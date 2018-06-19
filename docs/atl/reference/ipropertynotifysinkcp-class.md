---
title: IPropertyNotifySinkCP sınıfı | Microsoft Docs
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
ms.openlocfilehash: d9612cf65479e474b9a6e89a8f5a57ca078c9ed0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361632"
---
# <a name="ipropertynotifysinkcp-class"></a>IPropertyNotifySinkCP sınıfı
Bu sınıf sunan [Ipropertynotifysink](http://msdn.microsoft.com/library/windows/desktop/ms692638) arabirimi bağlanılabilirlik nesne üzerinde giden bir arabirim olarak.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T, class CDV = CComDynamicUnkArray>  
class IPropertyNotifySinkCP 
   : public IConnectionPointImpl<T, &IID_IPropertyNotifySink, CDV>
```    
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `IPropertyNotifySinkCP`.  
  
 `CDV`  
 Bir bağlantı noktası ve onun havuzlarını arasındaki bağlantıları yöneten bir sınıf. Varsayılan değer [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), sınırsız izin verir. Aynı zamanda [CComUnkArray](../../atl/reference/ccomunkarray-class.md), sabit bir bağlantı sayısını belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 `IPropertyNotifySinkCP` temel sınıfı olan tüm yöntemleri devralır [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md).  
  
 [Ipropertynotifysink](http://msdn.microsoft.com/library/windows/desktop/ms692638) arabirimi özelliği değişiklikler hakkında bildirim almak için bir havuz nesnesi sağlar. Sınıf `IPropertyNotifySinkCP` bu arabirim bağlanılabilirlik nesne üzerinde giden bir arabirim olarak kullanıma sunar. İstemci uygulamalıdır `IPropertyNotifySink` havuz yöntemleri.  
  
 Sınıfından türetilen `IPropertyNotifySinkCP` temsil eden bir bağlantı noktası oluşturmak istediğinizde `IPropertyNotifySink` arabirimi.  
  
 İçinde ATL bağlantı noktaları hakkında daha fazla bilgi için bkz: [bağlantı noktaları](../../atl/atl-connection-points.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlctl.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IConnectionPointImpl sınıfı](../../atl/reference/iconnectionpointimpl-class.md)   
 [IConnectionPointContainerImpl sınıfı](../../atl/reference/iconnectionpointcontainerimpl-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
