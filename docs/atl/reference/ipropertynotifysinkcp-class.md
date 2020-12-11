---
description: ': IPropertyNotifySinkCP sınıfı hakkında daha fazla bilgi'
title: IPropertyNotifySinkCP sınıfı
ms.date: 11/04/2016
f1_keywords:
- IPropertyNotifySinkCP
- atlctl/ATL::IPropertyNotifySinkCP
helpviewer_keywords:
- connection points [C++], managing
- sinks, notifying of changes
- IPropertyNotifySinkCP class
ms.assetid: 1b41445e-bc88-4fa6-bb62-d68aacec2bd5
ms.openlocfilehash: 096a24a22634be23c7ede955c7ae49c3dd963f66
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158367"
---
# <a name="ipropertynotifysinkcp-class"></a>IPropertyNotifySinkCP sınıfı

Bu sınıf, [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) arabirimini bağlanılabilir bir nesne üzerinde giden arabirim olarak gösterir.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T, class CDV = CComDynamicUnkArray>
class IPropertyNotifySinkCP
   : public IConnectionPointImpl<T, &IID_IPropertyNotifySink, CDV>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, öğesinden türetilir `IPropertyNotifySinkCP` .

*CDV*<br/>
Bağlantı noktası ve havuzları arasındaki bağlantıları yöneten bir sınıf. Varsayılan değer, sınırsız bağlantılara izin veren [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)' dir. Ayrıca, sabit sayıda bağlantıyı belirten [CComUnkArray](../../atl/reference/ccomunkarray-class.md)' i de kullanabilirsiniz.

## <a name="remarks"></a>Açıklamalar

`IPropertyNotifySinkCP` tüm yöntemleri kendi temel sınıfı, [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)aracılığıyla devralır.

[IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) arabirimi, bir havuz nesnesinin özellik değişiklikleri hakkında bildirimler almasına izin verir. Sınıfı, `IPropertyNotifySinkCP` Bu arabirimi bağlanılabilir bir nesne üzerinde giden bir arabirim olarak kullanıma sunar. İstemci, `IPropertyNotifySink` havuzu üzerinde yöntemleri uygulamalıdır.

`IPropertyNotifySinkCP`Arabirimini temsil eden bir bağlantı noktası oluşturmak istediğinizde sınıfınızı sınıfından türetebilirsiniz `IPropertyNotifySink` .

ATL 'de bağlantı noktalarını kullanma hakkında daha fazla bilgi için, [bağlantı noktaları](../../atl/atl-connection-points.md)makalesine bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl. h

## <a name="see-also"></a>Ayrıca bkz.

[Inewctionpointımpl sınıfı](../../atl/reference/iconnectionpointimpl-class.md)<br/>
[Inewctionpointcontainerımpl sınıfı](../../atl/reference/iconnectionpointcontainerimpl-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
