---
title: COM eşlemesi genel işlevleri | Microsoft Docs
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
ms.openlocfilehash: a23dc598d499071183cfcf7b0172611a693e569d
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884242"
---
# <a name="com-map-global-functions"></a>COM eşlemesi genel işlevleri
Bu işlevler için COM eşleme desteği `IUnknown` uygulamaları.  
  
|||  
|-|-|  
|[AtlInternalQueryInterface](#atlinternalqueryinterface)|Devreder `IUnknown` toplanmayan bir nesne.|  
|[InlineIsEqualIUnknown](#inlineisequaliunknown)|Arabirimleri karşı karşılaştırma verimli kod oluşturur `IUnknown`.|  

  
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
 *pThis*  
 [in] Açık arabirimler COM haritasını içeren nesneye bir işaretçi `QueryInterface`.  
  
 *pEntries*  
 [in] Bir dizi `_ATL_INTMAP_ENTRY` kullanılabilir arabirim haritasını erişim yapılar.  
  
 *IID*  
 [in] İstenen arabiriminin GUID'si.  
  
 *ppvObject*  
 [out] Belirtilen arabirim işaretçisini bir işaretçi *IID*, veya arabirim bulunamazsa NULL.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart HRESULT değerlerinden biri.  
  
### <a name="remarks"></a>Açıklamalar  
 `AtlInternalQueryInterface` yalnızca COM eşleme tablosunda arabirimleri işler. Nesne toplanırsa, `AtlInternalQueryInterface` için dış bilinmeyen temsilci değil. COM eşlemesi tablosuna makro arabirimleri girebilirsiniz [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) veya türevleri biri.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#94](../../atl/codesnippet/cpp/com-map-global-functions_1.cpp)]  
  
##  <a name="inlineisequaliunknown"></a>  InlineIsEqualIUnknown  
 Sınama özel durum için bu işlevi çağırın `IUnknown`.  
  
```
BOOL InlineIsEqualUnknown(REFGUID rguid1);
```  
  
### <a name="parameters"></a>Parametreler  
 *rguid1*  
 [in] Karşılaştırma yapılacak GUID `IID_IUnknown`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevleri](../../atl/reference/atl-functions.md)   
 [COM Eşleme Makroları](../../atl/reference/com-map-macros.md)
