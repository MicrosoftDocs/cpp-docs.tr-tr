---
title: IPropertyNotifySinkCP Sınıfı
ms.date: 11/04/2016
f1_keywords:
- IPropertyNotifySinkCP
- atlctl/ATL::IPropertyNotifySinkCP
helpviewer_keywords:
- connection points [C++], managing
- sinks, notifying of changes
- IPropertyNotifySinkCP class
ms.assetid: 1b41445e-bc88-4fa6-bb62-d68aacec2bd5
ms.openlocfilehash: c6d98bf5a6dfe5566839eb22bcd2bab2a9c28e4d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329605"
---
# <a name="ipropertynotifysinkcp-class"></a>IPropertyNotifySinkCP Sınıfı

Bu sınıf, bağlanabilen bir nesne üzerinde giden bir arabirim olarak [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) arabirimini ortaya çıkarır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T, class CDV = CComDynamicUnkArray>
class IPropertyNotifySinkCP
   : public IConnectionPointImpl<T, &IID_IPropertyNotifySink, CDV>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `IPropertyNotifySinkCP`türetilmiştir.

*Cdv*<br/>
Bağlantı noktası ile lavaboları arasındaki bağlantıları yöneten sınıf. Varsayılan değer [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), sınırsız bağlantı sağlar. Sabit sayıda bağlantı belirten [CComUnkArray'i](../../atl/reference/ccomunkarray-class.md)de kullanabilirsiniz.

## <a name="remarks"></a>Açıklamalar

`IPropertyNotifySinkCP`taban sınıf, [iConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)üzerinden tüm yöntemleri devralır.

[IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) arabirimi, bir lavabo nesnesinin özellik değişiklikleri yle ilgili bildirimler almasını sağlar. Sınıf, `IPropertyNotifySinkCP` bu arabirimi bağlanabilir bir nesneüzerinde giden bir arabirim olarak ortaya çıkarır. İstemci lavaboda `IPropertyNotifySink` yöntemleri uygulamalıdır.

Arabirimi temsil `IPropertyNotifySinkCP` eden bir bağlantı noktası oluşturmak istediğinizde sınıfınızı türetin. `IPropertyNotifySink`

ATL'de bağlantı noktalarını kullanma hakkında daha fazla bilgi için [Bağlantı Noktaları](../../atl/atl-connection-points.md)makalesine bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl.h

## <a name="see-also"></a>Ayrıca bkz.

[IConnectionPointImpl Sınıfı](../../atl/reference/iconnectionpointimpl-class.md)<br/>
[IConnectionPointContainerImpl Sınıfı](../../atl/reference/iconnectionpointcontainerimpl-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
