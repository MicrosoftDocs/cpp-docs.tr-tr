---
title: "COM eşleme makroları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlcom/ATL::BEGIN_COM_MAP
- atlcom/ATL::END_COM_MAP
dev_langs: C++
helpviewer_keywords: COM interfaces, COM map macros
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5493d2a1777b999dd13f2fe295b9ee9192580d33
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="com-map-macros"></a>COM eşleme makroları
Bu makroları COM arabirimi eşlemeleri tanımlayın.  
  
|||  
|-|-|  
|[BEGIN_COM_MAP](#begin_com_map)|COM arabirimi eşleme girdilerini başlangıcını işaretler.|  
|[END_COM_MAP](#end_com_map)|COM arabirimi eşleme girdilerini sonunu işaretler.|  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
   
##  <a name="begin_com_map"></a>BEGIN_COM_MAP  
 COM eşlemesi üzerinden bir istemciye bir nesne üzerinde arabirimlerini sunan mekanizmasıdır `QueryInterface`.  
  
```
BEGIN_COM_MAP(x)
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 [in] Üzerinde arabirimleri gösterme sınıfı nesnesinin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 [CComObjectRootEx::InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) arabirimleri işaretçileri COM eşleminde yalnızca döndürür. Arabirim haritanızı Başlat `BEGIN_COM_MAP` makrosu, her ile arabirimlerinizin girişleri eklemek [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) makrosu veya türevleri, biri ve Haritası tamamlamak [END_COM_MAP](#end_com_map) Makro.  

  
### <a name="example"></a>Örnek  
 ATL gelen [sesli İKAZ](../../visual-cpp-samples.md) örnek:  
  
 [!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]  
  

  
##  <a name="end_com_map"></a>END_COM_MAP  
 COM arabirimi haritanızı tanımını sona erer.  
  
```
END_COM_MAP()
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları](../../atl/reference/atl-macros.md)   
 [COM eşlemesi genel işlevler](../../atl/reference/com-map-global-functions.md)
