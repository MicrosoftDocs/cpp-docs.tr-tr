---
title: ScheduleGroup sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- ScheduleGroup
- CONCRT/concurrency::ScheduleGroup
- CONCRT/concurrency::ScheduleGroup::Id
- CONCRT/concurrency::ScheduleGroup::Reference
- CONCRT/concurrency::ScheduleGroup::Release
- CONCRT/concurrency::ScheduleGroup::ScheduleTask
dev_langs:
- C++
helpviewer_keywords:
- ScheduleGroup class
ms.assetid: 86d380ff-f2e8-411c-b1a8-22bd3079824a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90687a1e0cb77694fce9e60004f3e43d0ea9acf0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427426"
---
# <a name="schedulegroup-class"></a>ScheduleGroup Sınıfı

Bir zamanlama grubu için bir soyutlamayı temsil eder. Zamanlama grupları zamansal olarak, başka bir gruba geçmeden önce aynı grupta başka bir görev yürütülürken veya mekan, aynı birden çok öğe aynı grupta yürüterek birbirine yakın zamanlanmasını gelen faydalanan bir dizi ilgili iş düzenleme NUMA düğümünde veya fiziksel yuvadaki.

## <a name="syntax"></a>Sözdizimi

```
class ScheduleGroup;
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[~ ScheduleGroup yok Edicisi](#dtor)||

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Kimliği](#id)|Grubun ait olduğu zamanlayıcıda benzersiz olan zamanlama grubu için bir tanımlayıcı döndürür.|
|[Başvuru](#reference)|Zamanlama grubu başvuru sayısını artırır.|
|[Sürüm](#release)|Zamanlayıcı grubu başvuru sayısını azaltır.|
|[ScheduleTask](#scheduletask)|Bir zamanlama grubundaki hafif görevi zamanlar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ScheduleGroup`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h

**Namespace:** eşzamanlılık

##  <a name="id"></a> Kimliği

Grubun ait olduğu zamanlayıcıda benzersiz olan zamanlama grubu için bir tanımlayıcı döndürür.

```
virtual unsigned int Id() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Grubun ait olduğu zamanlayıcıda benzersiz olan zamanlama grubu için bir tanımlayıcı.

##  <a name="operator_delete"></a> delete işleci

A `ScheduleGroup` nesnesi yok edildiğinde dahili olarak çalışma zamanı tarafından tüm dış başvuruları serbest bırakıldığında. Açıkça silinemiyor.

```
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
Silinecek nesnenin bir işaretçi.

##  <a name="reference"></a> Başvuru

Zamanlama grubu başvuru sayısını artırır.

```
virtual unsigned int Reference() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Yeni artan başvuru sayısı.

### <a name="remarks"></a>Açıklamalar

Bu, genellikle birleştirme için zamanlama grubu ömrünü yönetmek için kullanılır. Bir zamanlama grubu başvuru sayısını sıfıra düşerse, zamanlama grubu için çalışma zamanı tarafından silindi. Ya da kullanılarak oluşturulan bir zamanlama grubu [CurrentScheduler::CreateScheduleGroup](currentscheduler-class.md#createschedulegroup) yöntemi veya [Scheduler::CreateScheduleGroup](scheduler-class.md#createschedulegroup) yöntemi bir başvuru sayımı Bir'den başlatır.

##  <a name="release"></a> Yayın

Zamanlayıcı grubu başvuru sayısını azaltır.

```
virtual unsigned int Release() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Yeni indirildiği başvuru sayısı.

### <a name="remarks"></a>Açıklamalar

Bu, genellikle birleştirme için zamanlama grubu ömrünü yönetmek için kullanılır. Bir zamanlama grubu başvuru sayısını sıfıra düşerse, zamanlama grubu için çalışma zamanı tarafından silindi. Çağrısı yapmanız sonrasında `Release` yöntemi oluşturma kaldırmak için belirli sayıda başvuru sayısı ve herhangi ek başvurular kullanarak yerleştirilen `Reference` yöntemi, daha fazla zamanlama grubu faydalanamaz. Bunun yapılması, tanımsız davranışlara neden.

Bir zamanlama grubu, belirli bir zamanlayıcı örneğini ile ilişkilidir. Tüm başvuruları Zamanlayıcı yayımlanmadan önce ikinci imha Zamanlayıcısı'nda neden olabileceğinden zamanlama grubu için tüm başvurularını serbest bırakıldığından emin olmanız gerekir. Aksi takdirde sonuç tanımsız davranışa yapılıyor.

##  <a name="dtor"></a> ~ ScheduleGroup

```
virtual ~ScheduleGroup();
```

##  <a name="scheduletask"></a> ScheduleTask

Bir zamanlama grubundaki hafif görevi zamanlar.

```
virtual void ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data) = 0;
```

### <a name="parameters"></a>Parametreler

*_Proc*<br/>
İşlev gövdesi basit görev gerçekleştirmek için yürütmek için bir işaretçi.

*_Veri*<br/>
Void bir işaretçi verilere gövdesi bir görev için bir parametre olarak geçirilir.

### <a name="remarks"></a>Açıklamalar

Çağırma `ScheduleTask` yöntemi örtülü olarak yerleştirir başvuru sayısını görev yürütüldükten sonra uygun bir zamanda çalışma zamanı tarafından kaldırılır zamanlama grubu üzerinde.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[CurrentScheduler Sınıfı](currentscheduler-class.md)<br/>
[Zamanlayıcı Sınıfı](scheduler-class.md)<br/>
[Görev Zamanlayıcısı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)

