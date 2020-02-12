---
title: ScheduleGroup Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ScheduleGroup
- CONCRT/concurrency::ScheduleGroup
- CONCRT/concurrency::ScheduleGroup::Id
- CONCRT/concurrency::ScheduleGroup::Reference
- CONCRT/concurrency::ScheduleGroup::Release
- CONCRT/concurrency::ScheduleGroup::ScheduleTask
helpviewer_keywords:
- ScheduleGroup class
ms.assetid: 86d380ff-f2e8-411c-b1a8-22bd3079824a
ms.openlocfilehash: 8686b5ef0906e3188a1e683d1190bbe6124cd19e
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143262"
---
# <a name="schedulegroup-class"></a>ScheduleGroup Sınıfı

Bir zamanlama grubu için bir soyutlama temsil eder. Zamanlama grupları, farklı bir gruba geçmeden önce aynı grupta başka bir görevi yürüterek veya aynı grupta aynı grup içinde birden çok öğe yürütülerek, zamana bağlı birlikte, aynı grupta daha fazla görev yürütülerek bir ilgili iş kümesini düzenler. NUMA düğümü veya fiziksel yuva.

## <a name="syntax"></a>Sözdizimi

```cpp
class ScheduleGroup;
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[~ ScheduleGroup yok edici](#dtor)||

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Kimlik](#id)|Grubun ait olduğu Zamanlayıcı dahilinde benzersiz olan zamanlama grubu için bir tanımlayıcı döndürür.|
|[Başvuru](#reference)|Zamanlama grubu başvuru sayısını artırır.|
|[Sürüm](#release)|Zamanlayıcı grubu başvuru sayısını azaltır.|
|[ScheduleTask](#scheduletask)|Zamanlama grubu içinde bir hafif görevi zamanlar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ScheduleGroup`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="id"></a>Numarasını

Grubun ait olduğu Zamanlayıcı dahilinde benzersiz olan zamanlama grubu için bir tanımlayıcı döndürür.

```cpp
virtual unsigned int Id() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Grubun ait olduğu Zamanlayıcı dahilinde benzersiz olan zamanlama grubu için bir tanımlayıcı.

## <a name="operator_delete"></a>delete işleci

Bir `ScheduleGroup` nesnesi, tüm dış başvuruları serbest bırakıldığında çalışma zamanı tarafından dahili olarak yok edilir. Açıkça silinemez.

```cpp
void operator delete(
    void* _PObject);

void operator delete(
    void* _PObject,
    int,
const char *,
    int);
```

### <a name="parameters"></a>Parametreler

*_PObject*<br/>
Silinecek nesneye yönelik bir işaretçi.

## <a name="reference"></a>Başvurunun

Zamanlama grubu başvuru sayısını artırır.

```cpp
virtual unsigned int Reference() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Yeni artan başvuru sayısı.

### <a name="remarks"></a>Açıklamalar

Bu genellikle, oluşturma için Zamanlama grubunun ömrünü yönetmek için kullanılır. Bir zamanlama grubunun başvuru sayısı sıfır olduğunda, zamanlama grubu çalışma zamanı tarafından silinir. [CurrentScheduler:: CreateScheduleGroup](currentscheduler-class.md#createschedulegroup) yöntemi kullanılarak oluşturulan bir zamanlama grubu ya da [Scheduler:: CreateScheduleGroup](scheduler-class.md#createschedulegroup) yöntemi bir başvuru sayısı ile başlar.

## <a name="release"></a>Yayın

Zamanlayıcı grubu başvuru sayısını azaltır.

```cpp
virtual unsigned int Release() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Yeni küçültülenen başvuru sayısı.

### <a name="remarks"></a>Açıklamalar

Bu genellikle, oluşturma için Zamanlama grubunun ömrünü yönetmek için kullanılır. Bir zamanlama grubunun başvuru sayısı sıfır olduğunda, zamanlama grubu çalışma zamanı tarafından silinir. `Release` yöntemini çağırdıktan sonra, oluşturma başvuru sayısını ve `Reference` yöntemi kullanılarak yerleştirilmiş ek başvuruları kaldırmak için belirli sayıda kez, zamanlama grubundan daha fazla yararlanamaz. Bunun yapılması tanımsız davranışa neden olur.

Bir zamanlama grubu, belirli bir zamanlayıcı örneğiyle ilişkilendirilir. İkinci olarak Scheduler 'ın yok edileceği için Zamanlayıcı grubuna yönelik tüm başvuruların serbest bırakılmadan önce serbest bırakıldığından emin olmanız gerekir. Aksi takdirde, tanımsız davranışa neden olur.

## <a name="dtor"></a>~ ScheduleGroup

```cpp
virtual ~ScheduleGroup();
```

## <a name="scheduletask"></a>ScheduleTask

Zamanlama grubu içinde bir hafif görevi zamanlar.

```cpp
virtual void ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data) = 0;
```

### <a name="parameters"></a>Parametreler

*_Proc*<br/>
Hafif görevin gövdesini gerçekleştirmek için yürütülecek işleve yönelik bir işaretçi.

*_Data*<br/>
Görevin gövdesine parametre olarak geçirilecek verilerin void işaretçisi.

### <a name="remarks"></a>Açıklamalar

`ScheduleTask` yöntemini çağırmak, görev yürütüldükten sonra uygun bir zamanda çalışma zamanı tarafından kaldırılan zamanlama grubuna bir başvuru sayımı koyar.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[CurrentScheduler Sınıfı](currentscheduler-class.md)<br/>
[Zamanlayıcı Sınıfı](scheduler-class.md)<br/>
[Görev Zamanlayıcı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)
