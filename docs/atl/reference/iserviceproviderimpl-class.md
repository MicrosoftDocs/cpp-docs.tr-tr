---
title: Iserviceproviderımpl sınıfı | Microsoft Docs
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
ms.openlocfilehash: 2e298f8398041b7b83a581b95f95c4ff9521cd4b
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883612"
---
# <a name="iserviceproviderimpl-class"></a>Iserviceproviderımpl sınıfı
Bu sınıfın bir varsayılan uygulamayı sağlar `IServiceProvider` arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>  
class ATL_NO_VTABLE IServiceProviderImpl : public IServiceProvider
```  
  
#### <a name="parameters"></a>Parametreler  
 *T*  
 Sınıfınız, türetilen `IServiceProviderImpl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IServiceProviderImpl::QueryService](#queryservice)|Oluşturur veya belirtilen hizmete erişen ve hizmet için belirtilen arabirim için bir arabirim işaretçisini döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 `IServiceProvider` Arabirimi GUID'sine tarafından belirtilen bir hizmeti bulur ve hizmette istenen arabirim için arabirim işaretçisini döndürür. Sınıf `IServiceProviderImpl` bu arabirimin bir varsayılan uygulamasını sağlar.  
  
 `IServiceProviderImpl` bir yöntem belirtir: [QueryService](#queryservice), oluşturan veya belirtilen hizmete erişen ve hizmet için belirtilen arabirim için bir arabirim işaretçisini döndürür.  
  
 `IServiceProviderImpl` ile başlayarak, bir hizmet eşlemesini kullanır [BEGIN_SERVICE_MAP](service-map-macros.md#begin_service_map) ve ile biten [END_SERVICE_MAP](service-map-macros.md#end_service_map).  
  
 Hizmet eşlemesi iki girişler içeriyor: [SERVICE_ENTRY](service-map-macros.md#service_entry), nesne tarafından desteklenen bir belirtilen hizmet kimliği (SID) belirtir ve [SERVICE_ENTRY_CHAIN](service-map-macros.md#service_entry_chain), çağıran `QueryService` başka zincirdeki nesne.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IServiceProvider`  
  
 `IServiceProviderImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="queryservice"></a>  IServiceProviderImpl::QueryService  
 Oluşturur veya belirtilen hizmete erişen ve hizmet için belirtilen arabirim için bir arabirim işaretçisini döndürür.  
  
```
STDMETHOD(QueryService)(
    REFGUID guidService,
    REFIID riid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>Parametreler  
 [IN] *guidService*  
 Hizmet tanımlayıcısı (SID) yönelik işaretçi.  
  
 [IN] *riid*  
 Arayan erişim elde etmek için arabirim tanımlayıcısı.  
  
 [OUT] *ppvObj*  
 Dolaylı istenen arabirim işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürülen HRESULT değerini aşağıdakilerden biridir:  
  
|Dönüş değeri|Açıklama|  
|------------------|-------------|  
|S_OK|Hizmet başarıyla oluşturuldu veya alınır.|  
|E_INVALIDARG|Bir veya daha fazla bağımsız değişken geçersiz.|  
|E_OUTOFMEMORY|Bir hizmet oluşturmak bellek yetersiz.|  
|E_UNEXPECTED|Bilinmeyen bir hata oluştu.|  
|E_NOINTERFACE|İstenen arabirim bu hizmetin bir parçası değil veya bilinmeyen bir hizmettir.|  
  
### <a name="remarks"></a>Açıklamalar  
 `QueryService` Belirtilen hizmet istenen arabiriminde dolaylı bir işaretçi döndürür. Artık gerekli olmadığında, bu işaretçi serbest bırakma için çağıran sorumludur.  
  
 Çağırdığınızda `QueryService`, geçirdiğiniz her iki hizmet tanımlayıcısı (*guidService*) ve bir arabirim tanımlayıcısı (*riid*). *GuidService* erişim, istediğiniz hizmet belirtir ve *riid* hizmetin bir parçası olan bir arabirim tanımlar. Buna karşılık, dolaylı bir arabirim işaretçisi alır.  
  
 Arabirimini uygulayan nesnenin ayrıca diğer hizmetleri arabirimleri uygulayabilir. Aşağıdakileri göz önünde bulundurun:  
  
-   Bu arabirimlerin bazıları, isteğe bağlı olabilir. Hizmet açıklamasında tanımlanan tüm arabirimleri mutlaka hizmetinin her bir uygulama ya da her döndürülen nesne yok.  
  
-   Çağrıları aksine `QueryInterface`, farklı hizmet tanımlayıcısı geçirme mutlaka gelmez farklı bir Bileşen Nesne Modeli (COM) nesne döndürülür.  
  
-   Döndürülen nesne hizmet tanımının bir parçası olmayan ek arabirimleri olabilir.  
  
 Hiçbir şey iki hizmet arasında ortak arabiriminin uygulamasını sahip olsanız bile SID_SMyService ve SID_SYourService, gibi iki farklı hizmet her ikisi de aynı arabirimi kullanımını belirtebilirsiniz. Bu, çalışır çünkü bir çağrı `QueryService` (SID_SMyService, IID_IDispatch) değerinden farklı bir nesne döndürebilir `QueryService` (SID_SYourService, IID_IDispatch). Farklı hizmet tanımlayıcısı belirttiğinizde nesne kimliğini kabul değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
