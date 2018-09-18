---
title: Agent sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 33afc48ab06bc12937b36c4ee5ccb4ee0f170216
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047206"
---
# <a name="agent-class"></a>agent Sınıfı
Tüm bağımsız aracıları için temel sınıf olarak kullanılacak bir sınıf yöneliktir. Bu durum diğer aracılardan Gizle ve ileti geçirme kullanarak etkileşim kurmak için kullanılır.  
  
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
|[İptal](#cancel)|Bir aracı herhangi birinden taşır `agent_created` veya `agent_runnable` için durumları `agent_canceled` durumu.|  
|[Başlangıç](#start)|Bir Aracıdan taşır `agent_created` durumunu `agent_runnable` belirtin ve yürütme için zamanlanır.|  
|[Durumu](#status)|Aracı durumu bilgileri, zaman uyumlu bir kaynağı.|  
|[status_port](#status_port)|Zaman uyumsuz bir Aracıdan durum bilgileri kaynağı.|  
|[bekleme](#wait)|Bir aracı, görevini tamamlamak üzere bekler.|  
|[wait_for_all](#wait_for_all)|Tüm görevlerini tamamlamak için belirtilen aracılar için bekler.|  
|[wait_for_one](#wait_for_one)|Görevi tamamlamak için belirtilen aracılar herhangi biri için bekler.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Bitti](#done)|Bir aracı içine taşır `agent_done` durumu, aracının tamamlandığı gösterilir.|  
|[Çalıştırma](#run)|Ana görevi bir aracının temsil eder. `run` türetilen bir sınıfta geçersiz kılınmalıdır ve aracının ne yapması gerektiğini belirtir, başlatıldıktan sonra.|  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için [zaman uyumsuz aracılar](../../../parallel/concrt/asynchronous-agents.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `agent`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** agents.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="ctor"></a> Aracı 

 Bir aracı oluşturur.  
  
```
agent();

agent(Scheduler& _PScheduler);

agent(ScheduleGroup& _PGroup);
```  
  
### <a name="parameters"></a>Parametreler  
*_PScheduler*<br/>
`Scheduler` Nesne aracı yürütme görevini zamanlanmış içinde.  
  
*_PGroup*<br/>
`ScheduleGroup` Nesne aracı yürütme görevini zamanlanmış içinde. `Scheduler` Kullanılan nesnesi zamanlama grubu tarafından belirtilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Çalışma zamanı belirtmezseniz varsayılan Zamanlayıcı kullanıyorsa `_PScheduler` veya `_PGroup` parametreleri.  
  
##  <a name="dtor"></a> ~ Aracı 

 Aracı yok eder.  
  
```
virtual ~agent();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir terminal durumunda bir aracı yok etmek için bir hata olduğunu (ya da `agent_done` veya `agent_canceled`). Bu aracının devralan bir sınıfın yok edici bir terminal durumuna ulaşmasını bekleyerek önlenebilir `agent` sınıfı.  
  
##  <a name="cancel"></a> İptal 

 Bir aracı herhangi birinden taşır `agent_created` veya `agent_runnable` için durumları `agent_canceled` durumu.  
  
```
bool cancel();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` aracıyı iptal edildiyse `false` Aksi takdirde. Bir aracı çalıştırma zaten başlatıldı veya zaten tamamlandı, iptal edilemez.  
  
##  <a name="done"></a> Bitti 

 Bir aracı içine taşır `agent_done` durumu, aracının tamamlandığı gösterilir.  
  
```
bool done();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Aracı için taşınırsa `agent_done` durumu `false` Aksi takdirde. İptal edilmiş bir aracı taşınamaz `agent_done` durumu.  
  
### <a name="remarks"></a>Açıklamalar  
 Sonunda bu yöntem çağrılmalıdır `run` aracınızı yürütülmesini bildiğinizde yöntemi tamamlandı.  
  
##  <a name="run"></a> Çalıştırma 

 Ana görevi bir aracının temsil eder. `run` türetilen bir sınıfta geçersiz kılınmalıdır ve aracının ne yapması gerektiğini belirtir, başlatıldıktan sonra.  
  
```
virtual void run() = 0;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Aracı durumu değiştirilecek `agent_started` bu yöntem çağrılmadan önce sağ. Yöntem çağırması gereken `done` döndürmek önce uygun bir durum aracıdaki ve herhangi bir özel durum oluşturması beklenmiyor.  
  
##  <a name="start"></a> Başlangıç 

 Bir Aracıdan taşır `agent_created` durumunu `agent_runnable` belirtin ve yürütme için zamanlanır.  
  
```
bool start();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` aracıyı doğru başlattıysanız `false` Aksi takdirde. İptal edilmiş bir aracı başlatılamıyor.  
  
##  <a name="status"></a> Durumu 

 Aracı durumu bilgileri, zaman uyumlu bir kaynağı.  
  
```
agent_status status();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Aracı geçerli durumunu döndürür. Döndürülen bu durumu hemen döndürülen sonra değişebilir unutmayın.  
  
##  <a name="status_port"></a> status_port 

 Zaman uyumsuz bir Aracıdan durum bilgileri kaynağı.  
  
```
ISource<agent_status>* status_port();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İleti Aracısı'nın geçerli durumu hakkında bir ileti kaynağı döndürür.  
  
##  <a name="wait"></a> bekleme 

 Bir aracı, görevini tamamlamak üzere bekler.  
  
```
static agent_status __cdecl wait(
    _Inout_ agent* _PAgent,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Parametreler  
*_PAgent*<br/>
Aracı için beklenecek bir işaretçi.  
  
*_Zaman aşımı*<br/>
Hangi beklenecek milisaniye cinsinden en uzun süre.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `agent_status` Bekleme tamamlandığında Aracısı. Bu da olabilir `agent_canceled` veya `agent_done`.  
  
### <a name="remarks"></a>Açıklamalar  
 Aracıyı girdiğinde bir aracı görevi tamamlandıktan `agent_canceled` veya `agent_done` durumları.  
  
 Parametre `_Timeout` sabiti dışında bir değere sahip `COOPERATIVE_TIMEOUT_INFINITE`, özel durum [operation_timed_out](operation-timed-out-class.md) aracı görevi tamamlanmadan önce belirtilen sürede sona ererse oluşturulur.  
  
##  <a name="wait_for_all"></a> wait_for_all 

 Tüm görevlerini tamamlamak için belirtilen aracılar için bekler.  
  
```
static void __cdecl wait_for_all(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    _Out_writes_opt_(count) agent_status* _PStatus = NULL,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Parametreler  
*Sayısı*<br/>
Aracı işaretçilerin dizisinde `_PAgents`.  
  
*_PAgents*<br/>
Aracılara beklemek için işaretçiler dizisi.  
  
*_PStatus*<br/>
Bir dizi Aracısı durumları için bir işaretçi. Yöntem döndürüldüğünde, her durum değeri karşılık gelen aracı durumunu temsil eder.  
  
*_Zaman aşımı*<br/>
Hangi beklenecek milisaniye cinsinden en uzun süre.  
  
### <a name="remarks"></a>Açıklamalar  
 Aracıyı girdiğinde bir aracı görevi tamamlandıktan `agent_canceled` veya `agent_done` durumları.  
  
 Parametre `_Timeout` sabiti dışında bir değere sahip `COOPERATIVE_TIMEOUT_INFINITE`, özel durum [operation_timed_out](operation-timed-out-class.md) aracı görevi tamamlanmadan önce belirtilen sürede sona ererse oluşturulur.  
  
##  <a name="wait_for_one"></a> wait_for_one 

 Görevi tamamlamak için belirtilen aracılar herhangi biri için bekler.  
  
```
static void __cdecl wait_for_one(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    agent_status& _Status,
    size_t& _Index,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Parametreler  
*Sayısı*<br/>
Aracı işaretçilerin dizisinde `_PAgents`.  
  
*_PAgents*<br/>
Aracılara beklemek için işaretçiler dizisi.  
  
*_Status*<br/>
Aracı durumu yerleştirileceği bir değişken başvuru.  
  
*_Index*<br/>
Aracı dizini yerleştirileceği bir değişken başvuru.  
  
*_Zaman aşımı*<br/>
Hangi beklenecek milisaniye cinsinden en uzun süre.  
  
### <a name="remarks"></a>Açıklamalar  
 Aracıyı girdiğinde bir aracı görevi tamamlandıktan `agent_canceled` veya `agent_done` durumları.  
  
 Parametre `_Timeout` sabiti dışında bir değere sahip `COOPERATIVE_TIMEOUT_INFINITE`, özel durum [operation_timed_out](operation-timed-out-class.md) aracı görevi tamamlanmadan önce belirtilen sürede sona ererse oluşturulur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
