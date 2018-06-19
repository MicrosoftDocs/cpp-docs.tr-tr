---
title: Iresourcemanager yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- IResourceManager
- CONCRTRM/concurrency::IResourceManager
- CONCRTRM/concurrency::IResourceManager::IResourceManager::OSVersion
- CONCRTRM/concurrency::IResourceManager::IResourceManager::CreateNodeTopology
- CONCRTRM/concurrency::IResourceManager::IResourceManager::GetAvailableNodeCount
- CONCRTRM/concurrency::IResourceManager::IResourceManager::GetFirstNode
- CONCRTRM/concurrency::IResourceManager::IResourceManager::Reference
- CONCRTRM/concurrency::IResourceManager::IResourceManager::RegisterScheduler
- CONCRTRM/concurrency::IResourceManager::IResourceManager::Release
dev_langs:
- C++
helpviewer_keywords:
- IResourceManager structure
ms.assetid: 3dd5ec2c-fe53-4121-ae77-1bc1d1167ff4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: afd87a71c8f5d41e38f6a1b18be96a7bab8f3bb8
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33693503"
---
# <a name="iresourcemanager-structure"></a>IResourceManager Yapısı
Eşzamanlılık Çalışma zamanı kaynak yöneticisi için bir arabirim. Bu, zamanlayıcılar Resource Manager ile iletişim kurmak arabirimidir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct IResourceManager;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-enumerations"></a>Ortak numaralandırmaları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Iresourcemanager::osversion](#osversion)|İşletim sistemi sürümünü temsil eden numaralandırılmış tür.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Iresourcemanager::createnodetopology](#createnodetopology)|Yalnızca hata ayıklama içinde mevcut çalışma zamanı derlemeleri, bu yöntem kaynak yapılandırma eşleşen gerçek donanım gerektirmeden donanım topolojileri değişen üzerinde Yöneticisi sınama kolaylaştırmak için tasarlanmış bir test kancası. İle perakende yapıları çalışma zamanının bu yöntem herhangi bir eylem gerçekleştirmeden döndürür.|  
|[Iresourcemanager::getavailablenodecount](#getavailablenodecount)|Resource Manager kullanılabilir düğüm sayısını döndürür.|  
|[Iresourcemanager::getfirstnode](#getfirstnode)|İlk düğüm, kaynak yöneticisi tarafından tanımlanan numaralandırma sırada döndürür.|  
|[Iresourcemanager::Reference](#reference)|Resource Manager örneğinde başvurusu sayısını artırır.|  
|[Iresourcemanager::registerscheduler](#registerscheduler)|Bir zamanlayıcı Resource Manager ile kaydeder. Zamanlayıcı kaydedildikten sonra Kaynak Yöneticisi'ni kullanarak ile iletişim kurmanız gerekir `ISchedulerProxy` döndürüldü arabirim.|  
|[Iresourcemanager::Release](#release)|Başvuru sayım Resource Manager örneğinde azaltır. Kaynak Yöneticisi, başvuru sayımı moduna alındığında yok `0`.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım [CreateResourceManager](concurrency-namespace-functions.md) işlevi singleton Resource Manager örneği için bir arabirim elde edilir. Bir başvuru sayısı Resource Manager'daki yöntemi artırır ve çağırma [Iresourcemanager::Release](#release) Resource Manager ile bittiğinde başvuru yayımlamayı yöntemi. Genellikle, oluşturduğunuz her Zamanlayıcı oluşturma sırasında bu yöntemi çağırır ve onu kapandıktan sonra başvurusu için kaynak yöneticisi bırakın.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IResourceManager`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrtrm.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="createnodetopology"></a>  Iresourcemanager::createnodetopology yöntemi  
 Yalnızca hata ayıklama içinde mevcut çalışma zamanı derlemeleri, bu yöntem kaynak yapılandırma eşleşen gerçek donanım gerektirmeden donanım topolojileri değişen üzerinde Yöneticisi sınama kolaylaştırmak için tasarlanmış bir test kancası. İle perakende yapıları çalışma zamanının bu yöntem herhangi bir eylem gerçekleştirmeden döndürür.  
  
```
virtual void CreateNodeTopology(
    unsigned int nodeCount,
    _In_reads_(nodeCount) unsigned int* pCoreCount,
    _In_reads_opt_(nodeCount) unsigned int** pNodeDistance,
    _In_reads_(nodeCount) unsigned int* pProcessorGroups) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `nodeCount`  
 Benzetimli işlemci düğüm sayısı.  
  
 `pCoreCount`  
 Çekirdek sayısı her düğümde belirten bir dizi.  
  
 `pNodeDistance`  
 Düğüm uzaklığı herhangi iki düğüm arasında belirten bir matris. Bu parametre değerine sahip `NULL`.  
  
 `pProcessorGroups`  
 İşlemci grubu belirten bir dizi her düğüme ait.  
  
### <a name="remarks"></a>Açıklamalar  
 [invalid_argument](../../../standard-library/invalid-argument-class.md) erişilirse durum parametresi `nodeCount` değerine sahip `0` , geçildi veya parametre `pCoreCount` değerine sahip `NULL`.  
  
 [invalid_operation](invalid-operation-class.md) diğer zamanlayıcılar işleminde varken bu yöntemi çağrıldıysa atılır.  
  
##  <a name="getavailablenodecount"></a>  Iresourcemanager::getavailablenodecount yöntemi  
 Resource Manager kullanılabilir düğüm sayısını döndürür.  
  
```
virtual unsigned int GetAvailableNodeCount() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Resource Manager kullanılabilir düğüm sayısı.  
  
##  <a name="getfirstnode"></a>  Iresourcemanager::getfirstnode yöntemi  
 İlk düğüm, kaynak yöneticisi tarafından tanımlanan numaralandırma sırada döndürür.  
  
```
virtual ITopologyNode* GetFirstNode() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kaynak Yöneticisi tarafından tanımlanan numaralandırma sırasında ilk düğüm.  
  
##  <a name="iresourcemanager__osversion"></a>  Iresourcemanager::osversion numaralandırması  
 İşletim sistemi sürümünü temsil eden numaralandırılmış tür.  
  
```
enum OSVersion;
```  
  
##  <a name="reference"></a>  Iresourcemanager::Reference yöntemi  
 Resource Manager örneğinde başvurusu sayısını artırır.  
  
```
virtual unsigned int Reference() = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sonuçta elde edilen başvuru sayısı.  
  
##  <a name="registerscheduler"></a>  Iresourcemanager::registerscheduler yöntemi  
 Bir zamanlayıcı Resource Manager ile kaydeder. Zamanlayıcı kaydedildikten sonra Kaynak Yöneticisi'ni kullanarak ile iletişim kurmanız gerekir `ISchedulerProxy` döndürüldü arabirim.  
  
```
virtual ISchedulerProxy *RegisterScheduler(
    _Inout_ IScheduler* pScheduler,
    unsigned int version) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `pScheduler`  
 Bir `IScheduler` kaydedilmesi için Zamanlayıcı arabirimi.  
  
 `version`  
 İletişim arabirimi sürümünü Resource Manager ile iletişim kurmak için Zamanlayıcı'yı kullanıyor. Bir sürümünü kullanmak için eski özellikleri erişim elde etme zamanlayıcılar verirken iletişim arabirimi gelişmesi Kaynak Yöneticisi'ni sağlar. Visual Studio 2010'da mevcut Kaynak Yöneticisi özellikleri kullanmak istediğiniz zamanlayıcılar sürüm kullanması gereken `CONCRT_RM_VERSION_1`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `ISchedulerProxy` Kaynak Manager Zamanlayıcısı ile ilişkilendirilen arabirimi. Zamanlayıcı, bu noktadan Resource Manager ile iletişim için bu arabirimi kullanmanız gerekir.  
  
### <a name="remarks"></a>Açıklamalar  
 Resource Manager ile iletişim başlatmak için bu yöntemi kullanın. Yöntem ilişkilendirir `IScheduler` Zamanlayıcısı ile arabirimdeki bir `ISchedulerProxy` arabirimi ve size geri ellere. İstek, Zamanlayıcı tarafından kullanılmak üzere yürütme kaynakları veya iş parçacığı Resource Manager ile abone olmak için döndürülen arabirimi kullanabilirsiniz. Kaynak Yöneticisi tarafından döndürülen Zamanlayıcı ilkeyi ilke öğelerinden kullanacağı [Ischeduler::getpolicy](ischeduler-structure.md#getpolicy) Zamanlayıcı iş parçacıklarının ne tür belirlemek amacıyla yöntemi iş yürütme gerekecektir. Varsa, `SchedulerKind` İlkesi anahtara sahip değeri `UmsThreadDefault` ve ilke değeri olarak geri dışında değer okuma `UmsThreadDefault`, `IScheduler` yönteme geçirilen arabirimi olmalıdır bir `IUMSScheduler` arabirimi.  
  
 Yöntem oluşturulur bir `invalid_argument` özel durum, parametre `pScheduler` değerine sahip `NULL` veya parametre `version` iletişim arabirimi için geçerli bir sürüm değil.  
  
##  <a name="release"></a>  Iresourcemanager::Release yöntemi  
 Başvuru sayım Resource Manager örneğinde azaltır. Kaynak Yöneticisi, başvuru sayımı moduna alındığında yok `0`.  
  
```
virtual unsigned int Release() = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sonuçta elde edilen başvuru sayısı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [Ischedulerproxy yapısı](ischedulerproxy-structure.md)   
 [IScheduler Yapısı](ischeduler-structure.md)
