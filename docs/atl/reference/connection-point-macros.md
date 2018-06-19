---
title: Bağlantı noktası makroları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::BEGIN_CONNECTION_POINT_MAP
- atlcom/ATL::END_CONNECTION_POINT_MAP
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], macros
ms.assetid: cc3a6dd3-5538-45df-b027-1f34963c31e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e50a868dd87628873b2a43f0ace55690b0583fd5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362936"
---
# <a name="connection-point-macros"></a>Bağlantı noktası makroları
Bu makroları bağlantı noktası eşlemeleri ve girişleri tanımlayın.  
  
|||  
|-|-|  
|[BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)|Bağlantı noktası eşleme girdilerini başlangıcını işaretler.|  
|[CONNECTION_POINT_ENTRY](#connection_point_entry)|Bağlantı noktaları eşlemeye girer.|  
|[CONNECTION_POINT_ENTRY_P](#connection_point_entry)| (Visual Studio 2017) CONNECTION_POINT_ENTRY benzer, ancak IID gösteren bir işaretçi alır.|
|[END_CONNECTION_POINT_MAP](#end_connection_point_map)|Bağlantı noktası eşleme girdilerini sonunu işaretler.|  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h 
   
##  <a name="begin_connection_point_map"></a>  BEGIN_CONNECTION_POINT_MAP  
 Bağlantı noktası eşleme girdilerini başlangıcını işaretler.  
  
```
BEGIN_CONNECTION_POINT_MAP(x)
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 [in] Bağlantı noktaları içeren sınıfın adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bağlantı noktası eşlemesi ile başlangıç `BEGIN_CONNECTION_POINT_MAP` makrosu, her bağlantı noktalarıyla girişleri eklemek [CONNECTION_POINT_ENTRY](#connection_point_entry) makro ve Haritası tamamlamak [END_CONNECTION_POINT_MAP](#end_connection_point_map) makrosu.  
  
 ATL bağlantı noktaları hakkında daha fazla bilgi için bkz: [bağlantı noktaları](../../atl/atl-connection-points.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#101](../../atl/codesnippet/cpp/connection-point-macros_1.h)]  
  
##  <a name="connection_point_entry"></a>  CONNECTION_POINT_ENTRY ve CONNECTION_POINT_ENTRY_P  
 Bir bağlantı noktası, belirtilen arabirim için bağlantı noktası eşlemeye girer buna erişebilir.  
  
```
CONNECTION_POINT_ENTRY(iid)
CONNECTION_POINT_ENTRY_P(piid) // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Parametreler  
 `iid`  
 [in] Bağlantı noktası eşlemesi için eklenmekte olan arabirimi GUID. 
 
 `piid`  
 [in] İşaretçi adde olan arabirimi GUID.   
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından kullanılan bağlantı noktası eşleme girişlerinde [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md). Bağlantı noktası eşlemesi içeren sınıf öğesinden devralmalıdır `IConnectionPointContainerImpl`.  
  
 Bağlantı noktası eşlemesi ile başlangıç [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map) makrosu, her bağlantı noktalarıyla girişleri eklemek `CONNECTION_POINT_ENTRY` makro ve Haritası tamamlamak [END_CONNECTION_POINT_MAP ](#end_connection_point_map) makrosu.  
  
 ATL bağlantı noktaları hakkında daha fazla bilgi için bkz: [bağlantı noktaları](../../atl/atl-connection-points.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#120](../../atl/codesnippet/cpp/connection-point-macros_2.h)]  
  
##  <a name="end_connection_point_map"></a>  END_CONNECTION_POINT_MAP  
 Bağlantı noktası eşleme girdilerini sonunu işaretler.  
  
```
END_CONNECTION_POINT_MAP()
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bağlantı noktası eşlemesi ile başlangıç [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map) makrosu, her bağlantı noktalarıyla girişleri eklemek [CONNECTION_POINT_ENTRY](#connection_point_entry) makro ve Haritasıtamamlayın`END_CONNECTION_POINT_MAP` makrosu.  
  
 ATL bağlantı noktaları hakkında daha fazla bilgi için bkz: [bağlantı noktaları](../../atl/atl-connection-points.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#128](../../atl/codesnippet/cpp/connection-point-macros_3.h)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları](../../atl/reference/atl-macros.md)   
 [Bağlantı Noktası Genel İşlevleri](../../atl/reference/connection-point-global-functions.md)
