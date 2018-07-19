---
title: Çalışan modeli | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Worker archetype
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 75f9e974a2969fa817598556e3e043626a826970
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37881311"
---
# <a name="worker-archetype"></a>Çalışan modeli
Uygun sınıfları *çalışan* archetype işlem iş öğeleri koda sıraya alınmış bir iş parçacığı havuzunda sağlayın.  
  
 **Uygulama**  
  
 Sınıfı, bu archetype için uygun bir sınıf uygulamak için aşağıdaki özellikleri sağlamanız gerekir:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Initialize](#initialize)|Tüm istekler için geçirilmeden önce alt nesne başlatmak için çağırılır [yürütme](#execute).|  
|[Yürütme](#execute)|Bir iş öğesini işlemek için çağrılır.|  
|[sonlandırma](#terminate)|Alt nesne için tüm istekleri geçildi; sonra kapatmak için çağrılan [yürütme](#execute).|  
  
|tür tanımı|Açıklama|  
|-------------|-----------------|  
|[RequestType](#requesttype)|Çalışan sınıfı tarafından işlenen iş öğesi türü için bir typedef.|  
  
 Tipik bir *çalışan* sınıfı aşağıdaki gibi görünür:  
  
 [!code-cpp[NVC_ATL_Utilities#137](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]  
  
 **Mevcut uygulamaları**  
  
 Bu sınıflar için bu archetype uyar:  
  
|örneği|Açıklama|  
|-----------|-----------------|  
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|İş parçacığı havuzu isteklerini alır ve bunları oluşturulur ve imha her istek için bir alt nesnesi açın geçirir.|  
  
 **Kullanın**  
  
 Bu şablon parametreleri için bu archetype uymak için sınıf bekler:  
  
|Parametre adı|Kullanan|  
|--------------------|-------------|  
|*Çalışan*|[CThreadPool](../../atl/reference/cthreadpool-class.md)|  
|*Çalışan*|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlutil.h  
  
## <a name="execute"></a>WorkerArchetype::Execute
Bir iş öğesini işlemek için çağrılır.  
  
  
  
```  
void Execute(
    RequestType request,  
    void* pvWorkerParam,  
    OVERLAPPED* pOverlapped);
```  
  
#### <a name="parameters"></a>Parametreler  
 *İstek*  
 İşlenmek üzere çalışma öğesi. İş öğesi aynı türde olan `RequestType`.  
  
 *pvWorkerParam*  
 Çalışan sınıfı tarafından anlaşılan bir özel parametre. Ayrıca geçirilen `WorkerArchetype::Initialize` ve `Terminate`.  
  
 *pOverlapped*  
 Bir işaretçi [ÇAKIŞAN](http://msdn.microsoft.com/library/windows/desktop/ms684342) yapısı üzerinde hangi iş öğelerini kuyruğa alındı sırayı oluşturmak için kullanılır.  
  
## <a name="initialize"></a> WorkerArchetype::Initialize
Tüm istekler için geçirilmeden önce alt nesne başlatmak için çağırılır `WorkerArchetype::Execute`.  
```
BOOL Initialize(void* pvParam) throw();
```  
  
#### <a name="parameters"></a>Parametreler  
 *pvParam*  
 Çalışan sınıfı tarafından anlaşılan bir özel parametre. Ayrıca geçirilen `WorkerArchetype::Terminate` ve `WorkerArchetype::Execute`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa TRUE döndürün başarısız olduğunda FALSE.  
  
## <a name="requesttype"></a> WorkerArchetype::RequestType
Çalışan sınıfı tarafından işlenen iş öğesi türü için bir typedef.  
  
```  
typedef MyRequestType RequestType;    
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu tür, ilk parametresi olarak kullanılmalıdır `WorkerArchetype::Execute` ve bir iç ULONG_PTR gelen ve giden cast uyumlu olması gerekir.  
  
## <a name="terminate"></a> WorkerArchetype::Terminate
Alt nesne için tüm istekleri geçildi; sonra kapatmak için çağrılan `WorkerArchetype::Execute`).  
    
``` 
void Terminate(void* pvParam) throw();
```  
  
#### <a name="parameters"></a>Parametreler  
 *pvParam*  
 Çalışan sınıfı tarafından anlaşılan bir özel parametre. Ayrıca geçirilen `WorkerArchetype::Initialize` ve `WorkerArchetype::Execute`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../../atl/active-template-library-atl-concepts.md)   
 [ATL COM Masaüstü Bileşenleri](../../atl/atl-com-desktop-components.md)



