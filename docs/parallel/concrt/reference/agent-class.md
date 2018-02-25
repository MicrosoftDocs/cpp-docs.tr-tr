---
title: "Agent sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- agent
- AGENTS/concurrency::agent
- AGENTS/concurrency::agent::agent
- AGENTS/concurrency::agent::cancel
- AGENTS/concurrency::agent::start
- AGENTS/concurrency::agent::status
- AGENTS/concurrency::agent::status_port
- AGENTS/concurrency::agent::wait
- AGENTS/concurrency::agent::wait_for_all
- AGENTS/concurrency::agent::wait_for_one
- AGENTS/concurrency::agent::done
- AGENTS/concurrency::agent::run
dev_langs:
- C++
helpviewer_keywords:
- agent class
ms.assetid: 1b09e3d2-5e37-4966-b016-907ef1512456
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4a4617007525fdd924dce7b09f1d351c7c18cc96
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="agent-class"></a>agent Sınıfı
Tüm bağımsız aracılar için temel sınıf olarak kullanılmak üzere bir sınıf. Diğer aracıları durumundan gizleme ve ileti geçirme kullanarak etkileşim kurmak için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class agent;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Aracı](#ctor)|Fazla Yüklendi. Bir aracı oluşturur.|  
|[~ agent yok Edicisi](#dtor)|Aracı yok eder.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[İptal](#cancel)|Bir aracı üzerinden taşır `agent_created` veya `agent_runnable` için durumları `agent_canceled` durumu.|  
|[start](#start)|Bir Aracıdan taşır `agent_created` durumunu `agent_runnable` belirtin ve yürütme için zamanlar.|  
|[Durumu](#status)|Aracı durumu bilgileri, zaman uyumlu bir kaynağı.|  
|[status_port](#status_port)|Zaman uyumsuz bir kaynağı aracısından durum bilgilerinin.|  
|[bekleme](#wait)|Bir aracı, görevini tamamlamak üzere bekler.|  
|[wait_for_all](#wait_for_all)|Tüm kullanıcıların görevleri tamamlamasını belirtilen aracılar için bekler.|  
|[wait_for_one](#wait_for_one)|Görevini tamamlamak üzere belirtilen aracıları herhangi biri için bekler.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Bitti](#done)|Bir aracı halinde taşır `agent_done` aracı tamamlandığını gösteren durum.|  
|[run](#run)|Bir aracının ana görev temsil eder. `run` türetilen bir sınıfta geçersiz kılınmalıdır ve aracı ne yapması gerektiğini belirten, başlatıldıktan sonra.|  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [zaman uyumsuz aracılar](../../../parallel/concrt/asynchronous-agents.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `agent`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** agents.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="ctor">Aracı</a> 

 Bir aracı oluşturur.  
  
```
agent();

agent(Scheduler& _PScheduler);

agent(ScheduleGroup& _PGroup);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PScheduler`  
 `Scheduler` Nesne aracı yürütme görevini zamanlanmış içinde.  
  
 `_PGroup`  
 `ScheduleGroup` Nesne aracı yürütme görevini zamanlanmış içinde. `Scheduler` Kullanılan nesnesi zamanlama grubu tarafından kapsanan.  
  
### <a name="remarks"></a>Açıklamalar  
 Çalışma zamanı belirtmezseniz varsayılan Zamanlayıcısı'nı kullanıyorsa `_PScheduler` veya `_PGroup` parametreleri.  
  
##  <a name="dtor"></a> ~ Aracısı 

 Aracı yok eder.  
  
```
virtual ~agent();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir terminal durumda olmayan bir aracı yok etmek için bir hata olduğunu (ya da `agent_done` veya `agent_canceled`). Bu terminal durumda yıkıcı öğesinden devralınan bir sınıf ulaşmak aracı için bekleyen tarafından önlenebilir `agent` sınıfı.  
  
##  <a name="cancel">İptal</a> 

 Bir aracı üzerinden taşır `agent_created` veya `agent_runnable` için durumları `agent_canceled` durumu.  
  
```
bool cancel();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Aracı iptal edilirse `false` Aksi takdirde. Zaten çalışan başlatıldı veya zaten tamamlanmış olan bir aracı iptal edilemez.  
  
##  <a name="done">Bitti</a> 

 Bir aracı halinde taşır `agent_done` aracı tamamlandığını gösteren durum.  
  
```
bool done();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Aracı için taşınırsa `agent_done` durumunu `false` Aksi takdirde. İptal edilmiş bir aracı taşınamıyor `agent_done` durumu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem sonunda çağrılmalıdır `run` aracınızı yürütülmesi bildiğinizde yöntemi tamamlandı.  
  
##  <a name="run"></a> çalıştırma 

 Bir aracının ana görev temsil eder. `run` türetilen bir sınıfta geçersiz kılınmalıdır ve aracı ne yapması gerektiğini belirten, başlatıldıktan sonra.  
  
```
virtual void run() = 0;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Aracı durumu olarak değiştirildiğinde `agent_started` bu yöntemi çağrılmadan önce sağ. Invoke yöntemi `done` dönmeden önce uygun bir durum ile aracısında ve özel durumlar atabilir değil.  
  
##  <a name="start"></a> Başlat 

 Bir Aracıdan taşır `agent_created` durumunu `agent_runnable` belirtin ve yürütme için zamanlar.  
  
```
bool start();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Aracı, doğru başlattıysanız `false` Aksi takdirde. İptal edilmiş bir aracı başlatılamıyor.  
  
##  <a name="status">Durumu</a> 

 Aracı durumu bilgileri, zaman uyumlu bir kaynağı.  
  
```
agent_status status();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aracının geçerli durumunu döndürür. Bu döndürülen durum hemen döndürülmesini sonra değişebilir unutmayın.  
  
##  <a name="status_port"></a> status_port 

 Zaman uyumsuz bir kaynağı aracısından durum bilgilerinin.  
  
```
ISource<agent_status>* status_port();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İleti Aracısı'nın geçerli durumu hakkında bir ileti kaynağı döndürür.  
  
##  <a name="wait">bekleme</a> 

 Bir aracı, görevini tamamlamak üzere bekler.  
  
```
static agent_status __cdecl wait(
    _Inout_ agent* _PAgent,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PAgent`  
 Bekleyin aracı için bir işaretçi.  
  
 `_Timeout`  
 Kendisi beklenecek milisaniye cinsinden en uzun süre.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `agent_status` Bekleme tamamlandığında Aracısı. Bu da olabilir `agent_canceled` veya `agent_done`.  
  
### <a name="remarks"></a>Açıklamalar  
 Aracı girdiğinde bir aracı görevi tamamlandıktan `agent_canceled` veya `agent_done` durumları.  
  
 Varsa parametresi `_Timeout` sabiti dışında bir değere sahip `COOPERATIVE_TIMEOUT_INFINITE`, özel durum [operation_timed_out](operation-timed-out-class.md) aracı kendi görev tamamlanmadan önce belirtilen sürede sona ererse atılır.  
  
##  <a name="wait_for_all"></a> wait_for_all 

 Tüm kullanıcıların görevleri tamamlamasını belirtilen aracılar için bekler.  
  
```
static void __cdecl wait_for_all(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    _Out_writes_opt_(count) agent_status* _PStatus = NULL,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Parametreler  
 `count`  
 Aracı işaretçileri dizisinde sayısı `_PAgents`.  
  
 `_PAgents`  
 Beklemek için aracıları işaretçiler dizisi.  
  
 `_PStatus`  
 Aracı durumlar dizisi için bir işaretçi. Yöntem döndüğünde her durum değeri karşılık gelen aracısının durumunu temsil eder.  
  
 `_Timeout`  
 Kendisi beklenecek milisaniye cinsinden en uzun süre.  
  
### <a name="remarks"></a>Açıklamalar  
 Aracı girdiğinde bir aracı görevi tamamlandıktan `agent_canceled` veya `agent_done` durumları.  
  
 Varsa parametresi `_Timeout` sabiti dışında bir değere sahip `COOPERATIVE_TIMEOUT_INFINITE`, özel durum [operation_timed_out](operation-timed-out-class.md) aracı kendi görev tamamlanmadan önce belirtilen sürede sona ererse atılır.  
  
##  <a name="wait_for_one"></a> wait_for_one 

 Görevini tamamlamak üzere belirtilen aracıları herhangi biri için bekler.  
  
```
static void __cdecl wait_for_one(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    agent_status& _Status,
    size_t& _Index,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Parametreler  
 `count`  
 Aracı işaretçileri dizisinde sayısı `_PAgents`.  
  
 `_PAgents`  
 Beklemek için aracıları işaretçiler dizisi.  
  
 `_Status`  
 Aracı durumunu yerleştirileceği bir değişkeni bir başvuru.  
  
 `_Index`  
 Aracı dizin yerleştirileceği bir değişkeni bir başvuru.  
  
 `_Timeout`  
 Kendisi beklenecek milisaniye cinsinden en uzun süre.  
  
### <a name="remarks"></a>Açıklamalar  
 Aracı girdiğinde bir aracı görevi tamamlandıktan `agent_canceled` veya `agent_done` durumları.  
  
 Varsa parametresi `_Timeout` sabiti dışında bir değere sahip `COOPERATIVE_TIMEOUT_INFINITE`, özel durum [operation_timed_out](operation-timed-out-class.md) aracı kendi görev tamamlanmadan önce belirtilen sürede sona ererse atılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
