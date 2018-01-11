---
title: "Hizmet eşleme makroları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlcom/ATL::BEGIN_SERVICE_MAP
- atlcom/ATL::END_SERVICE_MAP
- atlcom/ATL::SERVICE_ENTRY
- atlcom/ATL::SERVICE_ENTRY_CHAIN
dev_langs: C++
ms.assetid: ca02a125-454a-4cf6-aac2-1c5585025ed4
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 444d89833d84f23099ff0de8bce29bfc9d0a1344
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="service-map-macros"></a>Hizmet eşleme makroları
Bu makroları hizmet eşlemeleri ve girişleri tanımlayın.  
  
|||  
|-|-|  
|[BEGIN_SERVICE_MAP](#begin_service_map)|ATL hizmet Haritası başlangıcını işaretler.|  
|[END_SERVICE_MAP](#end_service_map)|ATL hizmet Haritası sonunu işaretler.|  
|[SERVICE_ENTRY](#service_entry)|Nesne bir özel hizmet kimliği desteklediğini gösterir|  
|[SERVICE_ENTRY_CHAIN](#service_entry_chain)|Bildirir [IServiceProviderImpl::QueryService](#queryservice) belirtilen nesneye zinciri için.|  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
   
##  <a name="begin_service_map"></a>BEGIN_SERVICE_MAP  
 Hizmet eşlemesi başlangıcını işaretler.  
  
```
BEGIN_SERVICE_MAP(theClass)
```  
  
### <a name="parameters"></a>Parametreler  
 `theClass`  
 [in] Hizmet eşlemesi içeren sınıf belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Hizmet sağlayıcı işlevselliğini COM nesnesi üzerinde uygulamak için hizmet Haritası kullanın. İlk olarak, sınıfından türetilmelidir [IServiceProviderImpl](../../atl/reference/iserviceproviderimpl-class.md). İki tür giriş vardır:  
  
- [SERVICE_ENTRY](#service_entry) belirtilen kimliği (SID) hizmeti için destek gösterir.  
  
- [SERVICE_ENTRY_CHAIN](#service_entry_chain) bildirir [IServiceProviderImpl::QueryService](#queryservice) için başka bir, belirtilen nesne zinciri.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_COM#57](../../atl/codesnippet/cpp/service-map-macros_1.h)]  
  
##  <a name="end_service_map"></a>END_SERVICE_MAP  
 Hizmet eşlemesi sonunu işaretler.  
  
```
END_SERVICE_MAP()
```  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [BEGIN_SERVICE_MAP](#begin_service_map).  
  
##  <a name="service_entry"></a>SERVICE_ENTRY  
 Nesne tarafından belirtilen hizmet kimliği desteklediğini gösterir *SID*.  
  
```
SERVICE_ENTRY( SID )
```  
  
### <a name="parameters"></a>Parametreler  
 *SID*  
 Hizmet kimliği  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [BEGIN_SERVICE_MAP](#begin_service_map).  
  
##  <a name="service_entry_chain"></a>SERVICE_ENTRY_CHAIN  
 Bildirir [IServiceProviderImpl::QueryService](#queryservice) tarafından belirtilen nesneye zinciri için `punk`.  
  
```
SERVICE_ENTRY_CHAIN( punk )
```  
  
### <a name="parameters"></a>Parametreler  
 `punk`  
 Bir işaretçi **IUnknown** arabirimin zinciri için.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [BEGIN_SERVICE_MAP](#begin_service_map).  
  
##  <a name="queryservice"></a>IServiceProviderImpl::QueryService  
 Oluşturur veya belirtilen hizmet erişir ve hizmet için belirtilen arabirimi için bir arabirim işaretçisi döndürür.  
  
```
STDMETHOD(QueryService)( 
    REFGUID guidService,
    REFIID riid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>Parametreler  
 [IN]`guidService`  
 Bir hizmet tanımlayıcı (SID) yönelik işaretçi.  
  
 [IN]`riid`  
 Çağıranın erişim kazanmak için arabirimi tanımlayıcısı.  
  
 [OUT]`ppvObj`  
 İstenen arabirim dolaylı işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürülen `HRESULT` değeri şunlardan biri değil:  
  
|Dönüş değeri|Açıklama|  
|------------------|-------------|  
|S_OK|Hizmet başarıyla oluşturuldu veya alınır.|  
|E_INVALIDARG|Bir veya daha fazla bağımsız değişken geçersiz.|  
|E_OUTOFMEMORY|Bir hizmet oluşturmak bellek yetersiz.|  
|E_UNEXPECTED|Bilinmeyen bir hata oluştu.|  
|E_NOINTERFACE|İstenen arabirim bu hizmetin bir parçası değil veya bilinmeyen bir hizmettir.|  
  
### <a name="remarks"></a>Açıklamalar  
 `QueryService`Belirtilen hizmet istenen arabiriminde dolaylı bir işaretçi döndürür. Çağıran, artık gerekli olmadığında bu işaretçinin serbest bırakma için sorumludur.  
  
 Çağırdığınızda `QueryService`, hem de bir hizmet tanımlayıcı geçirdiğiniz ( `guidService`) ve bir arabirim tanımlayıcısı ( `riid`). `guidService` Erişim için istediğiniz hizmeti belirtir ve `riid` hizmetinin bir parçası olan bir arabirim tanımlar. Buna karşılık, arabirim dolaylı bir işaretçi alırsınız.  
  
 Arabirimini uygulayan nesne aynı zamanda diğer hizmetlerin parçası olan arabirimler uygulayabilir. Aşağıdakileri göz önünde bulundurun:  
  
-   Bu arabirimleri bazıları, isteğe bağlı olabilir. Hizmet açıklamasında tanımlanan tüm arabirimleri mutlaka hizmetinin her uygulama veya her döndürülen nesne yok.  
  
-   Çağrı aksine `QueryInterface`, farklı bir hizmet tanımlayıcı geçirme mutlaka gelmez farklı bir Bileşen Nesne Modeli (COM) nesne döndürülür.  
  
-   Döndürülen nesne hizmeti tanımının bir parçası olmayan ek arabirimleri olabilir.  
  
 Arabirim uygulaması iki hizmetleri arasında ortak bir şey sahip olsanız bile SID_SMyService ve SID_SYourService, gibi iki farklı hizmet her ikisi de aynı arabirimi kullanımını belirtebilirsiniz. Bu, çünkü çalışır yapılan bir çağrı `QueryService` (SID_SMyService, IID_IDispatch) değerinden farklı bir nesne dönebilirsiniz `QueryService` (SID_SYourService, IID_IDispatch). Farklı bir hizmet tanımlayıcı belirttiğinizde nesne kimliği varsayılır değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları](../../atl/reference/atl-macros.md)
