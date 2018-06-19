---
title: IServiceProviderImpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl::QueryService
dev_langs:
- C++
helpviewer_keywords:
- IServiceProviderImpl class
- IServiceProvider interface, ATL implementation
ms.assetid: 251254d3-c4ce-40d7-aee0-3d676d1d72f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b1472fe5d952e93b45240128383db9fdec5b093
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363680"
---
# <a name="iserviceproviderimpl-class"></a>IServiceProviderImpl sınıfı
Bu sınıf, bir varsayılan uygulamasını sağlar `IServiceProvider` arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>  
class ATL_NO_VTABLE IServiceProviderImpl : public IServiceProvider
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `IServiceProviderImpl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IServiceProviderImpl::QueryService](#queryservice)|Oluşturur veya belirtilen hizmet erişir ve hizmet için belirtilen arabirimi için bir arabirim işaretçisi döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 `IServiceProvider` Arabirimi GUID'sine tarafından belirtilen bir hizmeti bulur ve istenen arabirimi arabirim işaretçisi hizmette döndürür. Sınıf `IServiceProviderImpl` bu arabirimin varsayılan uygulamasını sağlar.  
  
 **IServiceProviderImpl** bir yöntemini belirtir: [QueryService](#queryservice), hangi oluşturur veya belirtilen hizmet erişir ve hizmet için belirtilen arabirimi için bir arabirim işaretçisi döndürür.  
  
 `IServiceProviderImpl` ile başlayan bir hizmet eşlemesi kullanan [BEGIN_SERVICE_MAP](service-map-macros.md#begin_service_map) ve ile biten [END_SERVICE_MAP](service-map-macros.md#end_service_map).  
  
 Hizmet eşlemesi iki girdiler içeriyor: [SERVICE_ENTRY](service-map-macros.md#service_entry), nesne tarafından desteklenen bir belirtilen hizmet kimliği (SID) gösterir ve [SERVICE_ENTRY_CHAIN](service-map-macros.md#service_entry_chain), çağıran `QueryService` başka bir zincir için nesne.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IServiceProvider`  
  
 `IServiceProviderImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="queryservice"></a>  IServiceProviderImpl::QueryService  
 Oluşturur veya belirtilen hizmet erişir ve hizmet için belirtilen arabirimi için bir arabirim işaretçisi döndürür.  
  
```
STDMETHOD(QueryService)(
    REFGUID guidService,
    REFIID riid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>Parametreler  
 [IN] `guidService`  
 Bir hizmet tanımlayıcı (SID) yönelik işaretçi.  
  
 [IN] `riid`  
 Çağıranın erişim kazanmak için arabirimi tanımlayıcısı.  
  
 [OUT] `ppvObj`  
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
 `QueryService` Belirtilen hizmet istenen arabiriminde dolaylı bir işaretçi döndürür. Çağıran, artık gerekli olmadığında bu işaretçinin serbest bırakma için sorumludur.  
  
 Çağırdığınızda `QueryService`, hem de bir hizmet tanımlayıcı geçirdiğiniz ( `guidService`) ve bir arabirim tanımlayıcısı ( `riid`). `guidService` Erişim için istediğiniz hizmeti belirtir ve `riid` hizmetinin bir parçası olan bir arabirim tanımlar. Buna karşılık, arabirim dolaylı bir işaretçi alırsınız.  
  
 Arabirimini uygulayan nesne aynı zamanda diğer hizmetlerin parçası olan arabirimler uygulayabilir. Aşağıdakileri göz önünde bulundurun:  
  
-   Bu arabirimleri bazıları, isteğe bağlı olabilir. Hizmet açıklamasında tanımlanan tüm arabirimleri mutlaka hizmetinin her uygulama veya her döndürülen nesne yok.  
  
-   Çağrı aksine `QueryInterface`, farklı bir hizmet tanımlayıcı geçirme mutlaka gelmez farklı bir Bileşen Nesne Modeli (COM) nesne döndürülür.  
  
-   Döndürülen nesne hizmeti tanımının bir parçası olmayan ek arabirimleri olabilir.  
  
 Arabirim uygulaması iki hizmetleri arasında ortak bir şey sahip olsanız bile SID_SMyService ve SID_SYourService, gibi iki farklı hizmet her ikisi de aynı arabirimi kullanımını belirtebilirsiniz. Bu, çünkü çalışır yapılan bir çağrı `QueryService` (SID_SMyService, IID_IDispatch) değerinden farklı bir nesne dönebilirsiniz `QueryService` (SID_SYourService, IID_IDispatch). Farklı bir hizmet tanımlayıcı belirttiğinizde nesne kimliği varsayılır değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
