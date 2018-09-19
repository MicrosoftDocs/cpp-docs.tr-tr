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
ms.openlocfilehash: 13ddd14ad530fa2b7ce2892ce8838b27e307381f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46135782"
---
# <a name="ipropertynotifysinkcp-class"></a>Ipropertynotifysinkcp sınıfı

Bu sınıf sunan [Ipropertynotifysink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) arabirimi bağlanılabilirlik nesnesi üzerinde giden bir arabirim olarak.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T, class CDV = CComDynamicUnkArray>
class IPropertyNotifySinkCP 
   : public IConnectionPointImpl<T, &IID_IPropertyNotifySink, CDV>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, türetilen `IPropertyNotifySinkCP`.

*CDV*<br/>
Bir bağlantı noktası ve onun havuz arasındaki bağlantıları yöneten bir sınıf. Varsayılan değer [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), sınırsız sayıda bağlantı sağlar. Ayrıca [CComUnkArray](../../atl/reference/ccomunkarray-class.md), sabit sayıda bağlantı belirtir.

## <a name="remarks"></a>Açıklamalar

`IPropertyNotifySinkCP` temel sınıfı olan tüm yöntemleri devralan [Iconnectionpointımpl](../../atl/reference/iconnectionpointimpl-class.md).

[Ipropertynotifysink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) arabirim özellik değişiklikleri hakkında bildirim almak bir havuz nesnesi sağlar. Sınıf `IPropertyNotifySinkCP` bağlanılabilirlik nesnesi üzerinde giden bir arabirim olarak bu arabirimini kullanıma sunar. İstemci uygulamalıdır `IPropertyNotifySink` havuz yöntemleri.

Öğesinden, bir sınıf türetin `IPropertyNotifySinkCP` temsil eden bir bağlantı noktası oluşturmak istediğinizde `IPropertyNotifySink` arabirimi.

ATL bağlantı noktaları hakkında daha fazla bilgi için bkz [bağlantı noktaları](../../atl/atl-connection-points.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlctl.h

## <a name="see-also"></a>Ayrıca Bkz.

[IConnectionPointImpl Sınıfı](../../atl/reference/iconnectionpointimpl-class.md)<br/>
[IConnectionPointContainerImpl Sınıfı](../../atl/reference/iconnectionpointcontainerimpl-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
