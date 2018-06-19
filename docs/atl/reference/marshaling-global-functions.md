---
title: Genel işlevler hazırlama | Microsoft Docs
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
ms.openlocfilehash: 6d93839002ce5136d735e4740388109e855561fb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362833"
---
# <a name="marshaling-global-functions"></a>Genel işlevler hazırlama
Bu işlevler hazırlama ve arabirim İşaretçileri hazırlama veri dönüştürme için destek sağlar.  
  
> [!IMPORTANT]
>  Windows çalışma zamanı'nda yürütme uygulamalarda aşağıdaki tabloda listelenen işlevleri kullanılamaz.  
  
|||  
|-|-|  
|[AtlFreeMarshalStream](#atlfreemarshalstream)|Sıralama verileri serbest bırakır ve `IStream` işaretçi.|  
|[AtlMarshalPtrInProc](#atlmarshalptrinproc)|Yeni bir akış nesnesi oluşturur ve belirtilen arabirim işaretçisi sıralar.|  
|[AtlUnmarshalPtr](#atlunmarshalptr)|Veri hazırlama bir akışın bir arabirim işaretçisi dönüştürür.|  

## <a name="requirements"></a>Gereksinimleri:
**Başlık:** atlbase.h
  
##  <a name="atlfreemarshalstream"></a>  AtlFreeMarshalStream  
 Akıştaki sıralama verilerini serbest bırakır, ardından da akış işaretçisini serbest bırakır.  

```
HRESULT AtlFreeMarshalStream(IStream* pStream);
```  
  
### <a name="parameters"></a>Parametreler  
 `pStream`  
 [in] Bir işaretçi `IStream` sıralama için kullanılan akış arabirimi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [AtlMarshalPtrInProc](#atlmarshalptrinproc).  
  
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
 [in] Bir işaretçi sıralanması arabirimi.  
  
 `iid`  
 [in] Sıralanmış arabirimi GUID.  
  
 `ppStream`  
 [out] Bir işaretçi `IStream` sıralama için kullanılan yeni akış nesnesindeki arabirim.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değer.  
  
### <a name="remarks"></a>Açıklamalar  
 **MSHLFLAGS_TABLESTRONG** bayrağı işaretçiyi birden çok akış sıralanabilir şekilde ayarlanır. İşaretçinin, aynı zamanda birden çok kez iptal olabilir.  
  
 Başarısız hazırlama, akış işaretçi yayımlanır.  
  
 `AtlMarshalPtrInProc` yalnızca bir işlem içi nesnesine bir işaretçi üzerinde kullanılabilir.  
  
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
 `pStream`  
 [in] Yanlış akış için bir işaretçi.  
  
 `iid`  
 [in] Yanlış arabirimi GUID.  
  
 `ppUnk`  
 [out] İptal arabirimi için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT değer.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [AtlMarshalPtrInProc](#atlmarshalptrinproc).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](../../atl/reference/atl-functions.md)
