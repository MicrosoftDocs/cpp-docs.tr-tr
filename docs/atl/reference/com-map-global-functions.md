---
title: COM eşlemesi genel işlevler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlInternalQueryInterface
- atlbase/ATL::InlineIsEqualIUnknown
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, COM map global functions
ms.assetid: b9612d30-eb23-46ef-8093-d56f237d3cf1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 509479a923203acd80eaac1ef90aa64125d208c6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359885"
---
# <a name="com-map-global-functions"></a>COM eşlemesi genel işlevler
Bu işlevler COM eşlemesi için desteği **IUnknown** uygulamaları.  
  
|||  
|-|-|  
|[AtlInternalQueryInterface](#atlinternalqueryinterface)|İçin temsilciler **IUnknown** toplanmayan bir nesne.|  
|[InlineIsEqualIUnknown](#inlineisequaliunknown)|Arabirimleri karşı karşılaştırma için verimli kod oluşturur **IUnknown**.|  

  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  

##  <a name="atlinternalqueryinterface"></a>  AtlInternalQueryInterface  
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
 `AtlInternalQueryInterface` Yalnızca COM eşleme tablosu arabirimlerde işler. Nesnenizin toplanır, `AtlInternalQueryInterface` dış bilinmeyen temsilci değil. Makro COM harita tabloya arabirimleri girebilirsiniz [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) veya türevleri biri.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#94](../../atl/codesnippet/cpp/com-map-global-functions_1.cpp)]  
  
##  <a name="inlineisequaliunknown"></a>  InlineIsEqualIUnknown  
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
