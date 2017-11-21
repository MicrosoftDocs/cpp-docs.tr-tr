---
title: "Çalışan Archetype | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords: Worker archetype
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a408af2ac7de2f71c98467e08c49187c346304e0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="worker-archetype"></a>Çalışan Archetype
Uygun sınıfları *çalışan* archetype sağlamak işlem iş öğeleri için kod sıraya alınmış bir iş parçacığı havuzu.  
  
 **Uygulama**  
  
 Bu archetype uyumsuz bir sınıf uygulama için sınıf aşağıdaki özellikleri sağlamanız gerekir:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Başlatma](#initialize)|Tüm istekler için geçirilmeden önce çalışan nesneyi başlatmak üzere çağrılır [yürütme](#execute).|  
|[Yürütme](#execute)|Bir iş öğesi işlemek üzere çağrılır.|  
|[Sonlandırma](#terminate)|Alt nesne için tüm istekleri iletildi sonra kapatmak için çağrılan [yürütme](#execute).|  
  
|TypeDef|Açıklama|  
|-------------|-----------------|  
|[RequestType](#requesttype)|Typedef çalışan sınıfı tarafından işlenen iş öğesi türü için.|  
  
 Tipik bir *çalışan* sınıfı şu şekilde görünür:  
  
 [!code-cpp[NVC_ATL_Utilities#137](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]  
  
 **Var olan uygulamalar**  
  
 Bu sınıfların bu archetype uygun:  
  
|örneği|Açıklama|  
|-----------|-----------------|  
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|İş parçacığı havuzundan isteklerini alır ve bunları oluşturulur ve her istek için yok bir alt nesne açın aktarır.|  
  
 **Kullanın**  
  
 Bu şablon parametreleri sınıfı bu archetype uygun olması için bekler:  
  
|Parametre adı|Kullanan|  
|--------------------|-------------|  
|*Çalışan*|[CThreadPool](../../atl/reference/cthreadpool-class.md)|  
|*Çalışan*|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlutil.h  
  
## <a name="execute"></a>WorkerArchetype::Execute
Bir iş öğesi işlemek üzere çağrılır.  
  
  
  
```  
void Execute(
    RequestType request,  
    void* pvWorkerParam,  
    OVERLAPPED* pOverlapped);
```  
  
#### <a name="parameters"></a>Parametreler  
 `request`  
 İşlenmek üzere iş öğesi. İş öğesi aynı türde olduğundan `RequestType`.  
  
 `pvWorkerParam`  
 Alt sınıf tarafından anlaşılan özel bir parametre. Ayrıca geçirilen `WorkerArchetype::Initialize` ve `Terminate`.  
  
 `pOverlapped`  
 Bir işaretçi [ÇAKIŞAN](http://msdn.microsoft.com/library/windows/desktop/ms684342) üzerinde hangi çalışma öğeleri kuyruğa alındı kuyruk oluşturmak için kullanılan yapısı.  
  
## <a name="initialize"></a>WorkerArchetype::Initialize
Tüm istekler için geçirilmeden önce çalışan nesneyi başlatmak üzere çağrılır `WorkerArchetype::Execute`.  
```
BOOL Initialize(void* pvParam) throw();
```  
  
#### <a name="parameters"></a>Parametreler  
 `pvParam`  
 Alt sınıf tarafından anlaşılan özel bir parametre. Ayrıca geçirilen `WorkerArchetype::Terminate` ve `WorkerArchetype::Execute`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş **TRUE** başarılı, **FALSE** hatasında.  
  
## <a name="requesttype"></a>WorkerArchetype::RequestType
Typedef çalışan sınıfı tarafından işlenen iş öğesi türü için.  
  
```  
typedef MyRequestType RequestType;    
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu tür ilk parametre olarak kullanılması gereken `WorkerArchetype::Execute` ve bir iç ULONG_PTR gelen ve giden cast yeteneğinin olması gerekir.  
  
## <a name="terminate"></a>WorkerArchetype::Terminate
Alt nesne için tüm istekleri iletildi sonra kapatmak için çağrılan `WorkerArchetype::Execute`).  
    
``` 
void Terminate(void* pvParam) throw();
```  
  
#### <a name="parameters"></a>Parametreler  
 `pvParam`  
 Alt sınıf tarafından anlaşılan özel bir parametre. Ayrıca geçirilen `WorkerArchetype::Initialize` ve `WorkerArchetype::Execute`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Mimarisi türleri](../../atl/reference/atl-archetypes.md)   
 [Kavramları](../../atl/active-template-library-atl-concepts.md)   
 [ATL COM Masaüstü bileşenleri](../../atl/atl-com-desktop-components.md)



