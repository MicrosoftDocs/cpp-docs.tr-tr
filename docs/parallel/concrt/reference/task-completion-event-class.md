---
title: task_completion_event Sınıfı
ms.date: 11/04/2016
f1_keywords:
- task_completion_event
- PPLTASKS/concurrency::task_completion_event
- PPLTASKS/concurrency::task_completion_event::task_completion_event
- PPLTASKS/concurrency::task_completion_event::set
- PPLTASKS/concurrency::task_completion_event::set_exception
helpviewer_keywords:
- task_completion_event class
ms.assetid: fb19ed98-f245-48dc-9ba5-487ba879b28a
ms.openlocfilehash: ae4cce94dd7b36cebadea5f6d05890d979cce474
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498962"
---
# <a name="taskcompletionevent-class"></a>task_completion_event Sınıfı

`task_completion_event` Sınıfı bir koşul sağlanana kadar bir görevin yürütülmesini geciktirmek veya dış bir olaya yanıt olarak bir görevi başlatma olanak tanır.

## <a name="syntax"></a>Sözdizimi

```
template<typename _ResultType>
class task_completion_event;

template<>
class task_completion_event<void>;
```

#### <a name="parameters"></a>Parametreler

*_ResultType*<br/>
Bu sonuç türü `task_completion_event` sınıfı.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[task_completion_event](#ctor)|Oluşturur bir `task_completion_event` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[set](#set)|Fazla Yüklendi. Görev tamamlama olayını ayarlar.|
|[set_exception](#set_exception)|Fazla Yüklendi. Bu olay ile ilişkilendirilmiş tüm görevler için bir özel durum yayar.|

## <a name="remarks"></a>Açıklamalar

Senaryonuz tamamlanacak bir görev oluşturmanızı gerektirir ve böylece devamlılıkları gelecekte bir noktada, yürütme için zamanlanır sahip olduğunda bir görev tamamlama olayından oluşturulan bir görev kullanın. `task_completion_event` , Oluşturun ve bu türdeki bir değerle görev tamamlama olayı küme yöntemini çağırma ilişkili görevin neden ve bu değeri sonuç olarak kendi devamlılıklarının sağlamak görev aynı türde olmalıdır.

Görev tamamlanma olayı hiç sinyal vermediyse, ondan oluşturulan tüm görevler imha edildiğinde iptal edilir.

`task_completion_event` Akıllı bir işaretçi gibi davranır ve değerine göre geçirilmelidir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`task_completion_event`

## <a name="requirements"></a>Gereksinimler

**Başlık:** ppltasks.h

**Namespace:** eşzamanlılık

##  <a name="set"></a> Ayarlayın

Görev tamamlama olayını ayarlar.

```
bool set(_ResultType _Result) const ;

bool set() const ;
```

### <a name="parameters"></a>Parametreler

*_Result*<br/>
Bu olayın ayarlanacağı sonuç.

### <a name="return-value"></a>Dönüş Değeri

Yöntem döndürür **true** olayı ayarlamada başarılı olursa. Döndürür **false** olay zaten ayarlanmışsa.

### <a name="remarks"></a>Açıklamalar

Birden fazla varsa veya eş zamanlı çağrı `set`, sadece ilk çağrı başarılı olur ve sonucu (varsa) görev tamamlama olayı depolanır. Geri kalan kümeler yoksayılır ve yöntem false döndürür. Bir görev tamamlama olayı ayarladığınızda, tüm görevleri olay hemen tamamlanır ve varsa devamları zamanlanır oluşturulan. Görev tamamlama nesneleri bir `_ResultType` dışında **void** değeri için bunların devamlılıklarına geçirir.

##  <a name="set_exception"></a> set_exception

Bu olay ile ilişkilendirilmiş tüm görevler için bir özel durum yayar.

```
template<typename _E>
__declspec(noinline) bool set_exception(_E _Except) const;

__declspec(noinline) bool set_exception(std::exception_ptr _ExceptionPtr) const ;
```

### <a name="parameters"></a>Parametreler

*_E*<br/>
Özel durum türü.

*_Except*<br/>
Ayarlanacak durum.

*_ExceptionPtr*<br/>
Ayarlamak için özel durum işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

##  <a name="ctor"></a> task_completion_event

Oluşturur bir `task_completion_event` nesne.

```
task_completion_event();
```

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
