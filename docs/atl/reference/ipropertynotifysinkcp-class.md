---
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
ms.openlocfilehash: 9838a48b078cbc59a5ae86669ad9f26792d9816e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495634"
---
# <a name="ipropertynotifysinkcp-class"></a>IPropertyNotifySinkCP sınıfı

Bu sınıf, [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) arabirimini bağlanılabilir bir nesne üzerinde giden arabirim olarak gösterir.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T, class CDV = CComDynamicUnkArray>
class IPropertyNotifySinkCP
   : public IConnectionPointImpl<T, &IID_IPropertyNotifySink, CDV>
```

#### <a name="parameters"></a>Parametreler

*ŞI*<br/>
Sınıfınız, öğesinden `IPropertyNotifySinkCP`türetilir.

*CDV*<br/>
Bağlantı noktası ve havuzları arasındaki bağlantıları yöneten bir sınıf. Varsayılan değer, sınırsız bağlantılara izin veren [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)' dir. Ayrıca, sabit sayıda bağlantıyı belirten [CComUnkArray](../../atl/reference/ccomunkarray-class.md)' i de kullanabilirsiniz.

## <a name="remarks"></a>Açıklamalar

`IPropertyNotifySinkCP`tüm yöntemleri kendi temel sınıfı, [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)aracılığıyla devralır.

[IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) arabirimi, bir havuz nesnesinin özellik değişiklikleri hakkında bildirimler almasına izin verir. Sınıfı `IPropertyNotifySinkCP` , bu arabirimi bağlanılabilir bir nesne üzerinde giden bir arabirim olarak kullanıma sunar. İstemci, havuzu üzerinde `IPropertyNotifySink` yöntemleri uygulamalıdır.

Arabirimini temsil eden bir `IPropertyNotifySinkCP` bağlantı noktası oluşturmak istediğinizde sınıfınızı sınıfından türetebilirsiniz. `IPropertyNotifySink`

ATL 'de bağlantı noktalarını kullanma hakkında daha fazla bilgi için, [bağlantı noktaları](../../atl/atl-connection-points.md)makalesine bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl. h

## <a name="see-also"></a>Ayrıca bkz.

[IConnectionPointImpl Sınıfı](../../atl/reference/iconnectionpointimpl-class.md)<br/>
[IConnectionPointContainerImpl Sınıfı](../../atl/reference/iconnectionpointcontainerimpl-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
