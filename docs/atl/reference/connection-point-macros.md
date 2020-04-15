---
title: Bağlantı Noktası Makroları
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_CONNECTION_POINT_MAP
- atlcom/ATL::END_CONNECTION_POINT_MAP
helpviewer_keywords:
- connection points [C++], macros
ms.assetid: cc3a6dd3-5538-45df-b027-1f34963c31e5
ms.openlocfilehash: 361cf6ab2c7af142c1d57c002681ccf6e4a87bda
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331492"
---
# <a name="connection-point-macros"></a>Bağlantı Noktası Makroları

Bu makrolar bağlantı noktası eşlemlerini ve girişleri tanımlar.

|||
|-|-|
|[BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)|Bağlantı noktası eşlem girişlerinin başlangıcını işaretler.|
|[CONNECTION_POINT_ENTRY](#connection_point_entry)|Bağlantı noktalarını haritaya girer.|
|[CONNECTION_POINT_ENTRY_P](#connection_point_entry)| (Visual Studio 2017) CONNECTION_POINT_ENTRY benzer ama iid için bir işaretçi alır.|
|[END_CONNECTION_POINT_MAP](#end_connection_point_map)|Bağlantı noktası eşlem girişlerinin sonunu işaretler.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="begin_connection_point_map"></a><a name="begin_connection_point_map"></a>BEGIN_CONNECTION_POINT_MAP

Bağlantı noktası eşlem girişlerinin başlangıcını işaretler.

```
BEGIN_CONNECTION_POINT_MAP(x)
```

### <a name="parameters"></a>Parametreler

*X*<br/>
[içinde] Bağlantı noktalarını içeren sınıfın adı.

### <a name="remarks"></a>Açıklamalar

bağlantı noktası haritanızı BEGIN_CONNECTION_POINT_MAP makrosuyla başlatın, [CONNECTION_POINT_ENTRY](#connection_point_entry) makroile bağlantı noktalarınızın her biri için girişler ekleyin ve [END_CONNECTION_POINT_MAP](#end_connection_point_map) makrosuyla haritayı tamamlayın.

ATL'deki bağlantı noktaları hakkında daha fazla bilgi için [Bağlantı Noktaları](../../atl/atl-connection-points.md)makalesine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#101](../../atl/codesnippet/cpp/connection-point-macros_1.h)]

## <a name="connection_point_entry-and-connection_point_entry_p"></a><a name="connection_point_entry"></a>CONNECTION_POINT_ENTRY ve CONNECTION_POINT_ENTRY_P

Bağlantı noktası haritasına, erişilebilmek için belirtilen arabirim için bir bağlantı noktası girer.

```
CONNECTION_POINT_ENTRY(iid)
CONNECTION_POINT_ENTRY_P(piid) // (Visual Studio 2017)
```

### <a name="parameters"></a>Parametreler

*ııd*<br/>
[içinde] Bağlantı noktası haritasına eklenen arabirimin GUID'i.

*piid*<br/>
[içinde] Adde olan arabirimin GUID işaretçisi.

### <a name="remarks"></a>Açıklamalar

Haritadaki bağlantı noktası girişleri [iConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)tarafından kullanılır. Bağlantı noktası eşlemi içeren `IConnectionPointContainerImpl`sınıf.

bağlantı noktası haritanızı [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map) makrosuyla başlatın, CONNECTION_POINT_ENTRY makroile bağlantı noktalarınızın her biri için girişler ekleyin ve [END_CONNECTION_POINT_MAP](#end_connection_point_map) makrosuyla haritayı tamamlayın.

ATL'deki bağlantı noktaları hakkında daha fazla bilgi için [Bağlantı Noktaları](../../atl/atl-connection-points.md)makalesine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#120](../../atl/codesnippet/cpp/connection-point-macros_2.h)]

## <a name="end_connection_point_map"></a><a name="end_connection_point_map"></a>END_CONNECTION_POINT_MAP

Bağlantı noktası eşlem girişlerinin sonunu işaretler.

```
END_CONNECTION_POINT_MAP()
```

### <a name="remarks"></a>Açıklamalar

Bağlantı noktası haritanızı [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map) makrosuyla başlatın, [CONNECTION_POINT_ENTRY](#connection_point_entry) makroile bağlantı noktalarınızın her biri için girişler ekleyin ve END_CONNECTION_POINT_MAP makrosuyla haritayı tamamlayın.

ATL'deki bağlantı noktaları hakkında daha fazla bilgi için [Bağlantı Noktaları](../../atl/atl-connection-points.md)makalesine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#128](../../atl/codesnippet/cpp/connection-point-macros_3.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)<br/>
[Bağlantı Noktası Genel İşlevleri](../../atl/reference/connection-point-global-functions.md)
