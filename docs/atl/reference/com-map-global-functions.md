---
title: "COM eşlemesi genel işlevler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlInternalQueryInterface
- atlbase/ATL::InlineIsEqualIUnknown
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, COM map global functions
ms.assetid: b9612d30-eb23-46ef-8093-d56f237d3cf1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f7a0a02e46906ae8d3b6c62b8cc1b9147d396966
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="com-map-global-functions"></a>COM eşlemesi genel işlevler
Bu işlevler COM eşlemesi için desteği **IUnknown** uygulamaları.  
  
|||  
|-|-|  
|[AtlInternalQueryInterface](#atlinternalqueryinterface)|İçin temsilciler **IUnknown** toplanmayan bir nesne.|  
|[InlineIsEqualIUnknown](#inlineisequaliunknown)|Arabirimleri karşı karşılaştırma için verimli kod oluşturur **IUnknown**.|  

  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  

##  <a name="atlinternalqueryinterface"></a>AtlInternalQueryInterface  
 İstenen arabirim için bir işaretçi alır.  
  
```
HRESULT AtlInternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>Parametreler  
 `pThis`  
 [in] COM eşlemesi maruz arabirimleri içeren nesneyi gösteren bir işaretçi `QueryInterface`.  
  
 `pEntries`  
 [in] Bir dizi **_ATL_INTMAP_ENTRY** kullanılabilir arabirimleri haritasını erişim yapıları.  
  
 `iid`  
 [in] İstenen arabirimi GUID.  
  
 `ppvObject`  
 [out] Belirtilen arabirim işaretçisi gösteren bir işaretçi `iid`, veya **NULL** arabirimi bulunmazsa.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="remarks"></a>Açıklamalar  
 `AtlInternalQueryInterface`yalnızca COM eşleme tablosu arabirimlerde işler. Nesnenizin toplanır, `AtlInternalQueryInterface` dış bilinmeyen temsilci değil. Makro COM harita tabloya arabirimleri girebilirsiniz [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) veya türevleri biri.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#94](../../atl/codesnippet/cpp/com-map-global-functions_1.cpp)]  
  
##  <a name="inlineisequaliunknown"></a>InlineIsEqualIUnknown  
 Özel bir durum için sınama için bu işlevi çağırmak **IUnknown**.  
  
```
BOOL InlineIsEqualUnknown(REFGUID rguid1);
```  
  
### <a name="parameters"></a>Parametreler  
 *rguid1*  
 [in] Karşılaştırma yapılacak GUID **IID_IUnknown**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](../../atl/reference/atl-functions.md)   
 [COM Eşleme Makroları](../../atl/reference/com-map-macros.md)
