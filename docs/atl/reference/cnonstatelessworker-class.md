---
title: CNonStatelessWorker sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker::RequestType
- ATLUTIL/ATL::CNonStatelessWorker::Execute
- ATLUTIL/ATL::CNonStatelessWorker::Initialize
- ATLUTIL/ATL::CNonStatelessWorker::Terminate
dev_langs:
- C++
helpviewer_keywords:
- CNonStatelessWorker class
ms.assetid: d00936c6-9e7d-49fb-b87d-417b963367d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de03ded4bc0021a8884f608d10368e3d09c11cf8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359613"
---
# <a name="cnonstatelessworker-class"></a>CNonStatelessWorker sınıfı
Bir iş parçacığı havuzu isteklerini alır ve bunları oluşturulan ve yok bir alt nesne açın her istekte aktarır.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class Worker>  
class CNonStatelessWorker
```  
  
#### <a name="parameters"></a>Parametreler  
 *Çalışan*  
 Bir çalışan iş parçacığı sınıf uyumludur [çalışan archetype](../../atl/reference/worker-archetype.md) üzerinde sıraya isteklerini işlemek için uygun [CThreadPool](../../atl/reference/cthreadpool-class.md).  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CNonStatelessWorker::RequestType](#requesttype)|Uygulaması [WorkerArchetype::RequestType](worker-archetype.md#requesttype).|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CNonStatelessWorker::Execute](#execute)|Uygulaması [WorkerArchetype::Execute](worker-archetype.md#execute).|  
|[CNonStatelessWorker::Initialize](#initialize)|Uygulaması [WorkerArchetype::Initialize](worker-archetype.md#initialize).|  
|[CNonStatelessWorker::Terminate](#terminate)|Uygulaması [WorkerArchetype::Terminate](worker-archetype.md#terminate).|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir basit çalışan iş parçacığı ile kullanmak için bu sınıf, [CThreadPool](../../atl/reference/cthreadpool-class.md). Bu sınıf, herhangi bir istek işleme yetenek kendi sağlamaz. Bunun yerine, tek bir örneğini başlatır *çalışan* istek başına ve bu örneğe yöntemlerini uyarlamasını atar.  
  
 Bu sınıf yararı var olan çalışan iş parçacığı sınıfları için durumu modeli değiştirmek için kolay bir yol sağlamasıdır. `CThreadPool` tek bir çalışan iş parçacığı ömrü boyunca oluşturacak alt sınıf durumu barındırıyorsa, birden çok istekte aktarabilecek şekilde. Yalnızca bu sınıfta kaydırma tarafından `CNonStatelessWorker` ile kullanmadan önce şablonu `CThreadPool`, çalışan ve tutan tek bir istek sınırlıdır durumunun etkin kalma süresi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlutil.h  
  
##  <a name="execute"></a>  CNonStatelessWorker::Execute  
 Uygulaması [WorkerArchetype::Execute](worker-archetype.md#execute).  

  
```
void Execute(
    Worker::RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem bir örneğini oluşturur *çalışan* sınıfı çağrıları ve yığını [başlatma](worker-archetype.md#initialize) bu nesne üzerinde. Başlatma başarılı olursa, bu yöntem de çağırır [yürütme](worker-archetype.md#execute) ve [Sonlandır](worker-archetype.md#terminate) aynı nesne üzerinde.  

  
##  <a name="initialize"></a>  CNonStatelessWorker::Initialize  
 Uygulaması [WorkerArchetype::Initialize](worker-archetype.md#initialize).  
  
```
BOOL Initialize(void* /* pvParam */) throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her zaman TRUE değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sınıf sıfırlamaları yapmaz `Initialize`.  
  
##  <a name="requesttype"></a>  CNonStatelessWorker::RequestType  
 Uygulaması [WorkerArchetype::RequestType](worker-archetype.md#requesttype).  
  
```
typedef Worker::RequestType RequestType;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sınıf için kullanılan sınıf aynı türde iş öğesini işler *çalışan* şablon parametresi. Bkz: [CNonStatelessWorker genel bakış](../../atl/reference/cnonstatelessworker-class.md) Ayrıntılar için.  
  
##  <a name="terminate"></a>  CNonStatelessWorker::Terminate  
 Uygulaması [WorkerArchetype::Terminate](worker-archetype.md#terminate).  
  
```
void Terminate(void* /* pvParam */) throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sınıf herhangi temizleme yapmaz `Terminate`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CThreadPool sınıfı](../../atl/reference/cthreadpool-class.md)   
 [Çalışan Archetype](../../atl/reference/worker-archetype.md)   
 [Sınıflar](../../atl/reference/atl-classes.md)
