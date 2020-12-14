---
description: 'Daha fazla bilgi edinin: ScheduleGroup sınıfı'
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
ms.openlocfilehash: ca6678cd8d8c13c5d62b3d98b0a0bb1ab14e29c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188917"
---
# <a name="schedulegroup-class"></a>ScheduleGroup Sınıfı

Bir zamanlama grubu için bir soyutlama temsil eder. Zamanlama grupları, farklı bir gruba geçmeden önce aynı grupta başka bir görevi yürüterek veya aynı NUMA düğümündeki veya fiziksel yuvada aynı grup içinde birden çok öğe yürütülerek, zamana bağlı birlikte, aynı grupta daha fazla bir görev yürütülerek bir dizi ilgili işi düzenler.

## <a name="syntax"></a>Syntax

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
|[Numarasını](#id)|Grubun ait olduğu Zamanlayıcı dahilinde benzersiz olan zamanlama grubu için bir tanımlayıcı döndürür.|
|[Başvuru](#reference)|Zamanlama grubu başvuru sayısını artırır.|
|[Sürüm](#release)|Zamanlayıcı grubu başvuru sayısını azaltır.|
|[ScheduleTask](#scheduletask)|Zamanlama grubu içinde bir hafif görevi zamanlar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ScheduleGroup`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h

**Ad alanı:** eşzamanlılık

## <a name="id"></a><a name="id"></a> Numarasını

Grubun ait olduğu Zamanlayıcı dahilinde benzersiz olan zamanlama grubu için bir tanımlayıcı döndürür.

```cpp
virtual unsigned int Id() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Grubun ait olduğu Zamanlayıcı dahilinde benzersiz olan zamanlama grubu için bir tanımlayıcı.

## <a name="operator-delete"></a><a name="operator_delete"></a> delete işleci

Bir `ScheduleGroup` nesne, tüm dış başvuruları serbest bırakıldığında çalışma zamanı tarafından dahili olarak yok edilir. Açıkça silinemez.

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

## <a name="reference"></a><a name="reference"></a> Başvurunun

Zamanlama grubu başvuru sayısını artırır.

```cpp
virtual unsigned int Reference() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Yeni artan başvuru sayısı.

### <a name="remarks"></a>Açıklamalar

Bu genellikle, oluşturma için Zamanlama grubunun ömrünü yönetmek için kullanılır. Bir zamanlama grubunun başvuru sayısı sıfır olduğunda, zamanlama grubu çalışma zamanı tarafından silinir. [CurrentScheduler:: CreateScheduleGroup](currentscheduler-class.md#createschedulegroup) yöntemi kullanılarak oluşturulan bir zamanlama grubu ya da [Scheduler:: CreateScheduleGroup](scheduler-class.md#createschedulegroup) yöntemi bir başvuru sayısı ile başlar.

## <a name="release"></a><a name="release"></a> Yayın

Zamanlayıcı grubu başvuru sayısını azaltır.

```cpp
virtual unsigned int Release() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Yeni küçültülenen başvuru sayısı.

### <a name="remarks"></a>Açıklamalar

Bu genellikle, oluşturma için Zamanlama grubunun ömrünü yönetmek için kullanılır. Bir zamanlama grubunun başvuru sayısı sıfır olduğunda, zamanlama grubu çalışma zamanı tarafından silinir. `Release`Yöntemi, oluşturma başvuru sayısını ve yöntemi kullanılarak yerleştirilmiş ek başvuruları kaldırmak için belirli sayıda kez çağırdıktan sonra `Reference` , zamanlama grubunu daha fazla kullanamayabilirsiniz. Bunun yapılması tanımsız davranışa neden olur.

Bir zamanlama grubu, belirli bir zamanlayıcı örneğiyle ilişkilendirilir. İkinci olarak Scheduler 'ın yok edileceği için Zamanlayıcı grubuna yönelik tüm başvuruların serbest bırakılmadan önce serbest bırakıldığından emin olmanız gerekir. Aksi takdirde, tanımsız davranışa neden olur.

## <a name="schedulegroup"></a><a name="dtor"></a> ~ ScheduleGroup

```cpp
virtual ~ScheduleGroup();
```

## <a name="scheduletask"></a><a name="scheduletask"></a> ScheduleTask

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

Yöntemi çağırmak, `ScheduleTask` görev yürütüldükten sonra uygun bir zamanda çalışma zamanı tarafından kaldırılan zamanlama grubuna bir başvuru sayımı koyar.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[CurrentScheduler sınıfı](currentscheduler-class.md)<br/>
[Zamanlayıcı sınıfı](scheduler-class.md)<br/>
[Görev Zamanlayıcı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)
