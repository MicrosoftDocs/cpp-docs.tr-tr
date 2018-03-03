---
title: "Bağlantı noktası genel işlevler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlAdvise
- atlbase/ATL::AtlUnadvise
- atlbase/ATL::AtlAdviseSinkMap
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], global functions
ms.assetid: bcb4bf50-2155-4e20-b8bb-f2908b03a6e7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ce7f6fc3d2a0b51f88952dd720955367b1dfe9d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="connection-point-global-functions"></a>Bağlantı noktası genel işlevler
Bu işlevler bağlantı noktaları için destek sağlar ve haritalar havuzu.  
  
> [!IMPORTANT]
>  Windows çalışma zamanı'nda yürütme uygulamalarda aşağıdaki tabloda listelenen işlevleri kullanılamaz.  
  
|||  
|-|-|  
|[AtlAdvise](#atladvise)|Bir nesnenin bağlantı noktası ve istemcinin havuzu arasında bir bağlantı oluşturur.|  
|[AtlUnadvise](#atlunadvise)|İle kurulan bağlantıyı sonlandırır `AtlAdvise`.|  
|[AtlAdviseSinkMap](#atladvisesinkmap)|Öneren veya bir olay havuz eşlemesi girişlerinde unadvises.|  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
   
##  <a name="atladvise"></a>AtlAdvise  
 Bir nesnenin bağlantı noktası ve istemcinin havuzu arasında bir bağlantı oluşturur.  
  
> [!IMPORTANT]
>  Windows çalışma zamanı'nda yürütme uygulamalarında bu işlevi kullanılamaz.  
  
```
HRESULT    AtlAdvise(
    IUnknown* pUnkCP,
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw);
```  
  
### <a name="parameters"></a>Parametreler  
 `pUnkCP`  
 [in] Bir işaretçi **IUnknown** bağlamak istemci nesne istemektedir.  
  
 *pUnk*  
 [in] İstemcinin bir işaretçi **IUnknown**.  
  
 `iid`  
 [in] Bağlantı noktası GUID. Genellikle, bu bağlantı noktası tarafından yönetilen giden arabirimi aynıdır.  
  
 `pdw`  
 [out] Bağlantı benzersiz olarak tanıtan tanımlama bilgisi için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Havuz bağlantı noktası tarafından desteklenen giden arabirimini uygular. İstemcinin kullandığı `pdw` geçirerek bağlantıyı kaldırmak için tanımlama bilgisi [AtlUnadvise](#atlunadvise).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#91](../../atl/codesnippet/cpp/connection-point-global-functions_1.cpp)]  
  
##  <a name="atlunadvise"></a>AtlUnadvise  
 İle kurulan bağlantıyı sonlandırır [AtlAdvise](#atladvise).  
  
> [!IMPORTANT]
>  Windows çalışma zamanı'nda yürütme uygulamalarında bu işlevi kullanılamaz.  
  
```
HRESULT    AtlUnadvise(
    IUnknown* pUnkCP,
    const IID& iid,
    DWORD dw);
```  
  
### <a name="parameters"></a>Parametreler  
 `pUnkCP`  
 [in] Bir işaretçi **IUnknown** istemci ile bağlı nesne.  
  
 `iid`  
 [in] Bağlantı noktası GUID. Genellikle, bu bağlantı noktası tarafından yönetilen giden arabirimi aynıdır.  
  
 `dw`  
 [in] Bağlantı benzersiz olarak tanıtan tanımlama bilgisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değer.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#96](../../atl/codesnippet/cpp/connection-point-global-functions_2.cpp)]  
  
##  <a name="atladvisesinkmap"></a>AtlAdviseSinkMap  
 Nesnenin havuz olayı eşlemesindeki tüm girişleri önermek veya öneriyi kaldırmak için bu işlevi çağırın.   
  
> [!IMPORTANT]
>  Windows çalışma zamanı'nda yürütme uygulamalarında bu işlevi kullanılamaz.  
  
```
HRESULT AtlAdviseSinkMap(T* pT, bool bAdvise);
```  
  
### <a name="parameters"></a>Parametreler  
 *pT*  
 [in] Havuz eşleme içeren nesne için bir işaretçi.  
  
 `bAdvise`  
 [in] **true** tüm havuz girişleri dikkat edin; olması durumunda **false** tüm havuz girişleri unadvised olması durumunda.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değer.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#92](../../atl/codesnippet/cpp/connection-point-global-functions_3.h)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](../../atl/reference/atl-functions.md)   
 [Bağlantı Noktası Makroları](../../atl/reference/connection-point-macros.md)
