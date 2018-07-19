---
title: Hazırlama genel işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlFreeMarshalStream
- atlbase/ATL::AtlMarshalPtrInProc
- atlbase/ATL::AtlUnmarshalPtr
dev_langs:
- C++
ms.assetid: 877100b5-6ad9-44c5-a2e0-09414f1720d0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 44c5205416ff19eeb849b0532d015275e4eb166e
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879345"
---
# <a name="marshaling-global-functions"></a>Hazırlama genel işlevleri
Bu işlevler, hazırlama ve veri hazırlama, arabirim işaretçilerini dönüştürme için destek sağlar.  
  
> [!IMPORTANT]
>  Aşağıdaki tabloda listelenen İşlevler, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
|||  
|-|-|  
|[AtlFreeMarshalStream](#atlfreemarshalstream)|Sıralama verilerini serbest bırakır ve `IStream` işaretçi.|  
|[AtlMarshalPtrInProc](#atlmarshalptrinproc)|Yeni bir akış nesnesi oluşturur ve belirtilen arabirim işaretçisini sıralar.|  
|[AtlUnmarshalPtr](#atlunmarshalptr)|Bir akışın sıralama verilerini bir arabirim işaretçisi dönüştürür.|  

## <a name="requirements"></a>Gereksinimler:
**Başlık:** atlbase.h
  
##  <a name="atlfreemarshalstream"></a>  AtlFreeMarshalStream  
 Akıştaki sıralama verilerini serbest bırakır, ardından da akış işaretçisini serbest bırakır.  

```
HRESULT AtlFreeMarshalStream(IStream* pStream);
```  
  
### <a name="parameters"></a>Parametreler  
 *pStream*  
 [in] Bir işaretçi `IStream` arabirimde sıralama için kullanılan akış.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [AtlMarshalPtrInProc](#atlmarshalptrinproc).  
  
##  <a name="atlmarshalptrinproc"></a>  AtlMarshalPtrInProc  
 Yeni bir akış nesnesi oluşturur, proxy CLSID değerini akışa yazar ve proxy'yi akış içinde başlatmak üzere gerekli olan veriyi yazarak belirtilen arabirim işaretçisini sıralar.  
  
```
HRESULT AtlMarshalPtrInProc(
    IUnknown* pUnk,
    const IID& iid,
    IStream** ppStream);
```  
  
### <a name="parameters"></a>Parametreler  
 *pUnk*  
 [in] Sıralanması arabirim işaretçisi.  
  
 *IID*  
 [in] Sıralanmış arabiriminin GUID'si.  
  
 *ppStream*  
 [out] Bir işaretçi `IStream` arabirimde sıralama için kullanılan yeni akış nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değerini.  
  
### <a name="remarks"></a>Açıklamalar  
 İşaretçi için birden çok akış sıralanabilir şekilde MSHLFLAGS_TABLESTRONG bayrağı ayarlanır. İşaretçiyi, ayrıca birden çok kez iptal olabilir.  
  
 Hazırlama başarısız olursa, akış işaretçisini serbest bırakılır.  
  
 `AtlMarshalPtrInProc` yalnızca işlem içi nesneye bir işaretçi üzerinde kullanılabilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#50](../../atl/codesnippet/cpp/marshaling-global-functions_1.cpp)]  
  
##  <a name="atlunmarshalptr"></a>  AtlUnmarshalPtr  
 Akışın sıralama verilerini istemci tarafından kullanılabilen bir arabirim işaretçisine dönüştürür.  
   
```
HRESULT AtlUnmarshalPtr(
    IStream* pStream,
    const IID& iid,
    IUnknown** ppUnk);
```  
  
### <a name="parameters"></a>Parametreler  
 *pStream*  
 [in] Yanlış akış için bir işaretçi.  
  
 *IID*  
 [in] Yanlış arabiriminin GUID'si.  
  
 *ppUnk*  
 [out] İptal arabirim işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değerini.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [AtlMarshalPtrInProc](#atlmarshalptrinproc).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](../../atl/reference/atl-functions.md)
