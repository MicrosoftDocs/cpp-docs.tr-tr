---
title: Bağlantı noktası makroları
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_CONNECTION_POINT_MAP
- atlcom/ATL::END_CONNECTION_POINT_MAP
helpviewer_keywords:
- connection points [C++], macros
ms.assetid: cc3a6dd3-5538-45df-b027-1f34963c31e5
ms.openlocfilehash: 6c716ad85ecb458b4be418a7e8554687dd19f3d8
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833523"
---
# <a name="connection-point-macros"></a>Bağlantı noktası makroları

Bu makrolar bağlantı noktası eşlemelerini ve girdilerini tanımlar.

|Makroya|Açıklama|
|-|-|
|[BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)|Bağlantı noktası eşleme girdilerinin başlangıcını işaretler.|
|[CONNECTION_POINT_ENTRY](#connection_point_entry)|Bağlantı noktalarını haritaya girer.|
|[CONNECTION_POINT_ENTRY_P](#connection_point_entry)| (Visual Studio 2017) CONNECTION_POINT_ENTRY benzer ancak IID için bir işaretçi alır.|
|[END_CONNECTION_POINT_MAP](#end_connection_point_map)|Bağlantı noktası eşleme girdilerinin sonunu işaretler.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="begin_connection_point_map"></a><a name="begin_connection_point_map"></a> BEGIN_CONNECTION_POINT_MAP

Bağlantı noktası eşleme girdilerinin başlangıcını işaretler.

```
BEGIN_CONNECTION_POINT_MAP(x)
```

### <a name="parameters"></a>Parametreler

*x*<br/>
'ndaki Bağlantı noktalarını içeren sınıfın adı.

### <a name="remarks"></a>Açıklamalar

BEGIN_CONNECTION_POINT_MAP makrosu ile bağlantı noktası eşlemenizi başlatın, bağlantı noktalarınızın her biri için [CONNECTION_POINT_ENTRY](#connection_point_entry) makrosuna girdi ekleyin ve [END_CONNECTION_POINT_MAP](#end_connection_point_map) makrosu ile Haritayı doldurun.

ATL 'deki bağlantı noktaları hakkında daha fazla bilgi için bkz. [bağlantı noktaları](../../atl/atl-connection-points.md)makalesi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#101](../../atl/codesnippet/cpp/connection-point-macros_1.h)]

## <a name="connection_point_entry-and-connection_point_entry_p"></a><a name="connection_point_entry"></a> CONNECTION_POINT_ENTRY ve CONNECTION_POINT_ENTRY_P

Erişilebilmesi için, bağlantı noktası eşlemesine belirtilen arabirim için bir bağlantı noktası girer.

```
CONNECTION_POINT_ENTRY(iid)
CONNECTION_POINT_ENTRY_P(piid) // (Visual Studio 2017)
```

### <a name="parameters"></a>Parametreler

*'si*<br/>
'ndaki Bağlantı noktası eşlemesine eklenmekte olan arabirimin GUID 'SI.

*piıd*<br/>
'ndaki Adde olan arabirimin GUID 'sine yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Haritadaki bağlantı noktası girdileri [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)tarafından kullanılır. Bağlantı noktası eşlemesini içeren sınıfın öğesinden devralması gerekir `IConnectionPointContainerImpl` .

[BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map) makrosu ile bağlantı noktası eşlemenizi başlatın, bağlantı noktalarınızın her biri için CONNECTION_POINT_ENTRY makrosuna girdi ekleyin ve [END_CONNECTION_POINT_MAP](#end_connection_point_map) makrosu ile Haritayı doldurun.

ATL 'deki bağlantı noktaları hakkında daha fazla bilgi için bkz. [bağlantı noktaları](../../atl/atl-connection-points.md)makalesi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#120](../../atl/codesnippet/cpp/connection-point-macros_2.h)]

## <a name="end_connection_point_map"></a><a name="end_connection_point_map"></a> END_CONNECTION_POINT_MAP

Bağlantı noktası eşleme girdilerinin sonunu işaretler.

```
END_CONNECTION_POINT_MAP()
```

### <a name="remarks"></a>Açıklamalar

[BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map) makrosu ile bağlantı noktası eşlemenizi başlatın, bağlantı noktalarınızın her biri için [CONNECTION_POINT_ENTRY](#connection_point_entry) makrosuna girdi ekleyin ve END_CONNECTION_POINT_MAP makrosu ile Haritayı doldurun.

ATL 'deki bağlantı noktaları hakkında daha fazla bilgi için bkz. [bağlantı noktaları](../../atl/atl-connection-points.md)makalesi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#128](../../atl/codesnippet/cpp/connection-point-macros_3.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)<br/>
[Bağlantı noktası genel Işlevleri](../../atl/reference/connection-point-global-functions.md)
