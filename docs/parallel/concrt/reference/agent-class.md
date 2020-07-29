---
title: agent Sınıfı
ms.date: 11/04/2016
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
helpviewer_keywords:
- agent class
ms.assetid: 1b09e3d2-5e37-4966-b016-907ef1512456
ms.openlocfilehash: f1d98cdc6237f182e0240a85f2fdce3410232195
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213898"
---
# <a name="agent-class"></a>agent Sınıfı

Tüm bağımsız aracılar için temel sınıf olarak kullanılması amaçlanan bir sınıf. Diğer aracılardan durumu gizlemek ve ileti geçirme kullanılarak etkileşim kurmak için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
class agent;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Aracısı](#ctor)|Fazla Yüklendi. Bir aracı oluşturur.|
|[~ Aracı yıkıcısı](#dtor)|Aracıyı yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[İptal](#cancel)|Bir aracıyı ya da durumlardan birine `agent_created` `agent_runnable` durum olarak kaydırır `agent_canceled` .|
|[start](#start)|Bir aracıyı `agent_created` durumdan `agent_runnable` duruma kaydırır ve yürütülmek üzere zamanlar.|
|[durumlarına](#status)|Aracıdan alınan durum bilgilerinin zaman uyumlu kaynağı.|
|[status_port](#status_port)|Aracıdan gelen durum bilgisi zaman uyumsuz kaynağı.|
|[bekleneceğini](#wait)|Aracının görevini tamamlamasını bekler.|
|[wait_for_all](#wait_for_all)|Belirtilen aracıların tümünün görevlerini tamamlamasını bekler.|
|[wait_for_one](#wait_for_one)|Belirtilen aracıların herhangi birinin görevini tamamlamasını bekler.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[bitti](#done)|Aracının tamamlandığını belirten bir aracıyı `agent_done` duruma kaydırır.|
|[çalışmaz](#run)|Bir aracının ana görevini temsil eder. `run`Türetilmiş bir sınıfta geçersiz kılınmalı ve aracının başlatıldıktan sonra ne yapması gerektiğini belirtir.|

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [zaman uyumsuz aracılar](../../../parallel/concrt/asynchronous-agents.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`agent`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Agents. h

**Ad alanı:** eşzamanlılık

## <a name="agent"></a><a name="ctor"></a>Aracısı

Bir aracı oluşturur.

```cpp
agent();

agent(Scheduler& _PScheduler);

agent(ScheduleGroup& _PGroup);
```

### <a name="parameters"></a>Parametreler

*_PScheduler*<br/>
`Scheduler`Aracının yürütme görevinin zamanlandığı nesne.

*_PGroup*<br/>
`ScheduleGroup`Aracının yürütme görevinin zamanlandığı nesne. `Scheduler`Kullanılan nesne, zamanlama grubu tarafından kapsanıyor.

### <a name="remarks"></a>Açıklamalar

Veya parametrelerini belirtmezseniz, çalışma zamanı varsayılan zamanlayıcıyı kullanır `_PScheduler` `_PGroup` .

## <a name="agent"></a><a name="dtor"></a>~ Aracı

Aracıyı yok eder.

```cpp
virtual ~agent();
```

### <a name="remarks"></a>Açıklamalar

Terminal durumunda olmayan bir aracıyı yok etme hatası (ya da `agent_done` `agent_canceled` ). Bu durum, aracının sınıfından devralan bir sınıfın yıkıcısında bir Terminal durumuna ulaşmasını bekleyerek önlenebilir `agent` .

## <a name="cancel"></a><a name="cancel"></a>İptal

Bir aracıyı ya da durumlardan birine `agent_created` `agent_runnable` durum olarak kaydırır `agent_canceled` .

```cpp
bool cancel();
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** Aracı iptal edildiyse, **`false`** tersi durumda. Zaten çalışmaya başlamış veya zaten tamamlanmış bir aracı iptal edilemez.

## <a name="done"></a><a name="done"></a>yapıldığını

Aracının tamamlandığını belirten bir aracıyı `agent_done` duruma kaydırır.

```cpp
bool done();
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** Aracı `agent_done` duruma taşınırsa, **`false`** tersi durumda. İptal edilen bir aracı `agent_done` durumuna taşınamaz.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `run` aracının yürütülmesinin tamamlandığını bildiğiniz durumlarda metodun sonunda çağrılmalıdır.

## <a name="run"></a><a name="run"></a>çalışmaz

Bir aracının ana görevini temsil eder. `run`Türetilmiş bir sınıfta geçersiz kılınmalı ve aracının başlatıldıktan sonra ne yapması gerektiğini belirtir.

```cpp
virtual void run() = 0;
```

### <a name="remarks"></a>Açıklamalar

`agent_started`Bu yöntem çağrılmadan önce aracı durumu sağ olarak değiştirilir. Yöntemi `done` döndürmeden önce uygun bir durum ile aracıda çağırmalıdır ve özel durum oluşturmayabilir.

## <a name="start"></a><a name="start"></a>başından

Bir aracıyı `agent_created` durumdan `agent_runnable` duruma kaydırır ve yürütülmek üzere zamanlar.

```cpp
bool start();
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** Aracı doğru şekilde başlatıldıysa, **`false`** tersi durumda. İptal edilen bir aracı başlatılamıyor.

## <a name="status"></a><a name="status"></a>durumlarına

Aracıdan alınan durum bilgilerinin zaman uyumlu kaynağı.

```cpp
agent_status status();
```

### <a name="return-value"></a>Dönüş Değeri

Aracının geçerli durumunu döndürür. Döndürülen bu durum döndürülmeden hemen sonra değişebileceğini unutmayın.

## <a name="status_port"></a><a name="status_port"></a>status_port

Aracıdan gelen durum bilgisi zaman uyumsuz kaynağı.

```cpp
ISource<agent_status>* status_port();
```

### <a name="return-value"></a>Dönüş Değeri

Aracının geçerli durumu hakkında ileti gönderebilen bir ileti kaynağı döndürür.

## <a name="wait"></a><a name="wait"></a>bekleneceğini

Aracının görevini tamamlamasını bekler.

```cpp
static agent_status __cdecl wait(
    _Inout_ agent* _PAgent,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>Parametreler

*_PAgent*<br/>
Beklemek için aracıya yönelik bir işaretçi.

*_Timeout*<br/>
Beklenmesi gereken en uzun süre (milisaniye cinsinden).

### <a name="return-value"></a>Dönüş Değeri

`agent_status`Bekleme tamamlandığında aracının. Bu ya da olabilir `agent_canceled` `agent_done` .

### <a name="remarks"></a>Açıklamalar

Aracı veya durumları girdiğinde bir aracı görevi tamamlanır `agent_canceled` `agent_done` .

Parametrenin `_Timeout` sabiti dışında bir değeri varsa `COOPERATIVE_TIMEOUT_INFINITE` , aracı görevini tamamlanmadan önce belirtilen süre dolarsa, özel durum [operation_timed_out](operation-timed-out-class.md) oluşturulur.

## <a name="wait_for_all"></a><a name="wait_for_all"></a>wait_for_all

Belirtilen aracıların tümünün görevlerini tamamlamasını bekler.

```cpp
static void __cdecl wait_for_all(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    _Out_writes_opt_(count) agent_status* _PStatus = NULL,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>Parametreler

*biriktirme*<br/>
Dizide bulunan aracı işaretçilerinin sayısı `_PAgents` .

*_PAgents*<br/>
Bekleyecek aracılara yönelik işaretçilerin bir dizisi.

*_PStatus*<br/>
Aracı durumlarının dizisine yönelik bir işaretçi. Her durum değeri, yöntemi döndüğünde ilgili aracının durumunu temsil eder.

*_Timeout*<br/>
Beklenmesi gereken en uzun süre (milisaniye cinsinden).

### <a name="remarks"></a>Açıklamalar

Aracı veya durumları girdiğinde bir aracı görevi tamamlanır `agent_canceled` `agent_done` .

Parametrenin `_Timeout` sabiti dışında bir değeri varsa `COOPERATIVE_TIMEOUT_INFINITE` , aracı görevini tamamlanmadan önce belirtilen süre dolarsa, özel durum [operation_timed_out](operation-timed-out-class.md) oluşturulur.

## <a name="wait_for_one"></a><a name="wait_for_one"></a>wait_for_one

Belirtilen aracıların herhangi birinin görevini tamamlamasını bekler.

```cpp
static void __cdecl wait_for_one(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    agent_status& _Status,
    size_t& _Index,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>Parametreler

*biriktirme*<br/>
Dizide bulunan aracı işaretçilerinin sayısı `_PAgents` .

*_PAgents*<br/>
Bekleyecek aracılara yönelik işaretçilerin bir dizisi.

*_Status*<br/>
Aracı durumunun yerleştirileceği bir değişkene başvuru.

*_Index*<br/>
Aracı dizininin yerleştirileceği bir değişkene başvuru.

*_Timeout*<br/>
Beklenmesi gereken en uzun süre (milisaniye cinsinden).

### <a name="remarks"></a>Açıklamalar

Aracı veya durumları girdiğinde bir aracı görevi tamamlanır `agent_canceled` `agent_done` .

Parametrenin `_Timeout` sabiti dışında bir değeri varsa `COOPERATIVE_TIMEOUT_INFINITE` , aracı görevini tamamlanmadan önce belirtilen süre dolarsa, özel durum [operation_timed_out](operation-timed-out-class.md) oluşturulur.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
