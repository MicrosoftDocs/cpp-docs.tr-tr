---
description: 'Hakkında daha fazla bilgi edinin: task_completion_event sınıfı'
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
ms.openlocfilehash: 791b68d6a67ea2f8a9697b69266e8744455f845c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188371"
---
# <a name="task_completion_event-class"></a>task_completion_event Sınıfı

Sınıfı, bir `task_completion_event` koşul karşılanana kadar bir görevin yürütülmesini ertelemenize veya dış bir olaya yanıt olarak bir görev başlatmanıza olanak sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename _ResultType>
class task_completion_event;

template<>
class task_completion_event<void>;
```

### <a name="parameters"></a>Parametreler

*_ResultType*<br/>
Bu sınıfın sonuç türü `task_completion_event` .

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[task_completion_event](#ctor)|Bir `task_completion_event` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[kurmak](#set)|Fazla Yüklendi. Görev tamamlama olayını ayarlar.|
|[set_exception](#set_exception)|Fazla Yüklendi. Bu olayla ilişkili tüm görevlere özel bir durum yayar.|

## <a name="remarks"></a>Açıklamalar

Senaryolarınız tamamlanacak bir görev oluşturmanızı gerektirdiğinde ve bu nedenle gelecekteki bir noktada yürütmeye zamanlanan devamlılıklar varsa, görev tamamlama olayından oluşturulan bir görevi kullanın. , `task_completion_event` Oluşturduğunuz görevle aynı türde olmalıdır ve bu tür bir değere sahip görev tamamlama olayında set yöntemini çağırmak ilişkili görevin tamamlanmasına neden olur ve bu değeri devamlılıkları sonucu olarak sağlar.

Görev tamamlama olayı hiçbir zaman sinyal alınmadıysa, bundan sonra oluşturulan tüm görevler, yinelenenleri kaldırma sırasında iptal edilir.

`task_completion_event` akıllı bir işaretçi gibi davranır ve değere göre geçirilmelidir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`task_completion_event`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** ppltasks. h

**Ad alanı:** eşzamanlılık

## <a name="set"></a><a name="set"></a> kurmak

Görev tamamlama olayını ayarlar.

```cpp
bool set(_ResultType _Result) const ;

bool set() const ;
```

### <a name="parameters"></a>Parametreler

*_Result*<br/>
Bu olayı ayarlama sonucu.

### <a name="return-value"></a>Dönüş Değeri

Yöntemi, **`true`** olay ayarlanırken başarılı olduysa döndürür. **`false`** Olayın zaten ayarlanmış olup olmadığını döndürür.

### <a name="remarks"></a>Açıklamalar

Birden çok veya eşzamanlı çağrısı `set` olması durumunda, yalnızca ilk çağrı başarılı olur ve sonucu (varsa) görev tamamlanma olayında depolanır. Kalan kümeler yok sayılır ve yöntem false döndürür. Bir görev tamamlama olayı ayarladığınızda, bu olaydan oluşturulan tüm görevler hemen tamamlanır ve varsa devamlılıkları planlanacaktır. Dışındaki görev tamamlama nesneleri `_ResultType` **`void`** değeri devamlılığa geçirir.

## <a name="set_exception"></a><a name="set_exception"></a> set_exception

Bu olayla ilişkili tüm görevlere özel bir durum yayar.

```cpp
template<typename _E>
__declspec(noinline) bool set_exception(_E _Except) const;

__declspec(noinline) bool set_exception(std::exception_ptr _ExceptionPtr) const ;
```

### <a name="parameters"></a>Parametreler

*_E*<br/>
Özel durum türü.

*_Except*<br/>
Ayarlanacak özel durum.

*_ExceptionPtr*<br/>
Ayarlanacak özel durum işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

## <a name="task_completion_event"></a><a name="ctor"></a> task_completion_event

Bir `task_completion_event` nesnesi oluşturur.

```cpp
task_completion_event();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
