---
title: Bağlantı noktası makroları
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_CONNECTION_POINT_MAP
- atlcom/ATL::END_CONNECTION_POINT_MAP
helpviewer_keywords:
- connection points [C++], macros
ms.assetid: cc3a6dd3-5538-45df-b027-1f34963c31e5
ms.openlocfilehash: ac00b1c5a937c32ecc02e11e735541119c388588
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605796"
---
# <a name="connection-point-macros"></a>Bağlantı noktası makroları

Bu makrolar, bağlantı noktası eşlemeleri ve girişleri tanımlayın.

|||
|-|-|
|[BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)|Bağlantı noktası eşleme girişleri başlangıcını işaretler.|
|[CONNECTION_POINT_ENTRY](#connection_point_entry)|Bağlantı noktaları eşlemeye girer.|
|[CONNECTION_POINT_ENTRY_P](#connection_point_entry)| (Visual Studio 2017) CONNECTION_POINT_ENTRY benzer, ancak IID için bir işaretçi alır.|
|[END_CONNECTION_POINT_MAP](#end_connection_point_map)|Bağlantı noktası eşleme girişleri sonunu işaretler.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="begin_connection_point_map"></a>  BEGIN_CONNECTION_POINT_MAP

Bağlantı noktası eşleme girişleri başlangıcını işaretler.

```
BEGIN_CONNECTION_POINT_MAP(x)
```

### <a name="parameters"></a>Parametreler

*x*<br/>
[in] Bağlantı noktalarını içeren sınıfın adı.

### <a name="remarks"></a>Açıklamalar

BEGIN_CONNECTION_POINT_MAP makro ile bağlantı noktasına eşlemenizi başlatma, her biri ile bağlantı noktaları için girişler ekleyin [CONNECTION_POINT_ENTRY](#connection_point_entry) makro ve haritayla tamamlamak [END_CONNECTION_ POINT_MAP](#end_connection_point_map) makrosu.

ATL bağlantı noktaları hakkında daha fazla bilgi için bkz [bağlantı noktaları](../../atl/atl-connection-points.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#101](../../atl/codesnippet/cpp/connection-point-macros_1.h)]

##  <a name="connection_point_entry"></a>  CONNECTION_POINT_ENTRY ve CONNECTION_POINT_ENTRY_P

Bir bağlantı noktası, belirtilen arabirim için bağlantı noktası eşlemeye girer ona erişilebilir.

```
CONNECTION_POINT_ENTRY(iid)
CONNECTION_POINT_ENTRY_P(piid) // (Visual Studio 2017)
```

### <a name="parameters"></a>Parametreler

*IID*<br/>
[in] Bağlantı noktası eşlemeye eklenen arabiriminin GUID'si.

*piid*<br/>
[in] GUID adde olan arabirimi işaretçi.

### <a name="remarks"></a>Açıklamalar

Tarafından kullanılan bağlantı noktası eşleme girişleri [Iconnectionpointcontainerımpl](../../atl/reference/iconnectionpointcontainerimpl-class.md). Bağlantı noktası eşlemesi içeren sınıfın devralmalıdır `IConnectionPointContainerImpl`.

Bağlantı noktası eşlemesi ile Başlat [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map) makrosu, her biri, bağlantı noktaları CONNECTION_POINT_ENTRY makro için girişler ekleyin ve haritayla tamamlamak [END_CONNECTION_ POINT_MAP](#end_connection_point_map) makrosu.

ATL bağlantı noktaları hakkında daha fazla bilgi için bkz [bağlantı noktaları](../../atl/atl-connection-points.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#120](../../atl/codesnippet/cpp/connection-point-macros_2.h)]

##  <a name="end_connection_point_map"></a>  END_CONNECTION_POINT_MAP

Bağlantı noktası eşleme girişleri sonunu işaretler.

```
END_CONNECTION_POINT_MAP()
```

### <a name="remarks"></a>Açıklamalar

Bağlantı noktası eşlemesi ile Başlat [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map) makrosu, her biri ile bağlantı noktaları için girişler ekleyin [CONNECTION_POINT_ENTRY](#connection_point_entry) makro ve END_ haritayla tamamlayın CONNECTION_POINT_MAP makrosu.

ATL bağlantı noktaları hakkında daha fazla bilgi için bkz [bağlantı noktaları](../../atl/atl-connection-points.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#128](../../atl/codesnippet/cpp/connection-point-macros_3.h)]

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları](../../atl/reference/atl-macros.md)<br/>
[Bağlantı Noktası Genel İşlevleri](../../atl/reference/connection-point-global-functions.md)
