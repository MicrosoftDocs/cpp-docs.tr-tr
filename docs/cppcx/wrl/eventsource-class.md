---
description: 'Daha fazla bilgi edinin: EventSource sınıfı'
title: EventSource Sınıfı
ms.date: 09/12/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource
- event/Microsoft::WRL::EventSource::Add
- event/Microsoft::WRL::EventSource::addRemoveLock_
- event/Microsoft::WRL::EventSource::EventSource
- event/Microsoft::WRL::EventSource::GetSize
- event/Microsoft::WRL::EventSource::InvokeAll
- event/Microsoft::WRL::EventSource::Remove
- event/Microsoft::WRL::EventSource::targets_
- event/Microsoft::WRL::EventSource::targetsPointerLock_
helpviewer_keywords:
- Microsoft::WRL::EventSource class
- Microsoft::WRL::EventSource::Add method
- Microsoft::WRL::EventSource::addRemoveLock_ data member
- Microsoft::WRL::EventSource::EventSource, constructor
- Microsoft::WRL::EventSource::GetSize method
- Microsoft::WRL::EventSource::InvokeAll method
- Microsoft::WRL::EventSource::Remove method
- Microsoft::WRL::EventSource::targets_ data member
- Microsoft::WRL::EventSource::targetsPointerLock_ data member
ms.assetid: 91f1c072-6af4-44e6-b6d8-ac6d0c688dde
ms.openlocfilehash: 2553d82a0fc16cd759f43ef2e4ae9527884cab10
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272818"
---
# <a name="eventsource-class"></a>EventSource Sınıfı

Çevik olmayan bir olayı temsil eder. `EventSource` üye işlevleri olay işleyicilerini ekler, kaldırır ve çağırır. Çevik olaylar için [Agileeventsource](agileeventsource-class.md)kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename TDelegateInterface>
class EventSource;
```

### <a name="parameters"></a>Parametreler

*Tdelegateınterface*<br/>
Bir olay işleyicisini temsil eden bir temsilci için arabirim.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

| Ad                                     | Açıklama                                            |
| ---------------------------------------- | ------------------------------------------------------ |
| [EventSource:: EventSource](#eventsource) | `EventSource` sınıfının yeni bir örneğini başlatır. |

### <a name="public-methods"></a>Ortak Yöntemler

| Ad                                 | Açıklama                                                                                                                                                      |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [EventSource:: Add](#add)             | Belirtilen temsilci arabirimiyle temsil edilen olay işleyicisini geçerli nesne için olay işleyicileri kümesine ekler `EventSource` .                     |
| [EventSource:: GetSize](#getsize)     | Geçerli nesneyle ilişkili olay işleyicilerinin sayısını alır `EventSource` .                                                                         |
| [EventSource:: InvokeAll](#invokeall) | `EventSource`Belirtilen bağımsız değişken türlerini ve bağımsız değişkenlerini kullanarak geçerli nesneyle ilişkili her olay işleyicisini çağırır.                                      |
| [EventSource:: Remove](#remove)       | Belirtilen olay kayıt belirteci tarafından temsil edilen olay işleyicisini geçerli nesneyle ilişkili olay işleyicileri kümesinden siler `EventSource` . |

### <a name="protected-data-members"></a>Korumalı veri üyeleri

| Ad                                                    | Açıklama                                                                                                                       |
| ------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| [EventSource:: addRemoveLock_](#addremovelock)           | Olay işleyicilerini eklerken, kaldırırken veya çağırırken [targets_](#targets) dizisine erişimi eşitler.                          |
| [EventSource:: targets_](#targets)                       | Bir veya daha fazla olay işleyicilerinden oluşan bir dizi.                                                                                           |
| [EventSource:: targetsPointerLock_](#targetspointerlock) | Bu EventSource için olay işleyicileri eklendikten, kaldırılmakta veya çağrıldığında bile iç veri üyelerine erişimi eşitler. |

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`EventSource`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Event. h

**Ad alanı:** Microsoft:: WRL

## <a name="eventsourceadd"></a><a name="add"></a> EventSource:: Add

Belirtilen temsilci arabirimiyle temsil edilen olay işleyicisini geçerli nesne için olay işleyicileri kümesine ekler `EventSource` .

```cpp
HRESULT Add(
   _In_ TDelegateInterface* delegateInterface,
   _Out_ EventRegistrationToken* token
);
```

### <a name="parameters"></a>Parametreler

*Delegateınterface*<br/>
Bir olay işleyicisini temsil eden bir temsilci nesnesine arabirim.

*simgesinde*<br/>
Bu işlem tamamlandığında, olayı temsil eden bir tanıtıcı. Olay işleyicisini atmak için [Remove ()](#remove) yöntemine parametre olarak bu belirteci kullanın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı gösteren bir HRESULT.

## <a name="eventsourceaddremovelock_"></a><a name="addremovelock"></a> EventSource:: addRemoveLock_

Olay işleyicilerini eklerken, kaldırırken veya çağırırken [targets_](#targets) dizisine erişimi eşitler.

```cpp
Wrappers::SRWLock addRemoveLock_;
```

## <a name="eventsourceeventsource"></a><a name="eventsource"></a> EventSource:: EventSource

`EventSource` sınıfının yeni bir örneğini başlatır.

```cpp
EventSource();
```

## <a name="eventsourcegetsize"></a><a name="getsize"></a> EventSource:: GetSize

Geçerli nesneyle ilişkili olay işleyicilerinin sayısını alır `EventSource` .

```cpp
size_t GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

[Targets_](#targets)içindeki olay işleyicilerinin sayısı.

## <a name="eventsourceinvokeall"></a><a name="invokeall"></a> EventSource:: InvokeAll

`EventSource`Belirtilen bağımsız değişken türlerini ve bağımsız değişkenlerini kullanarak geçerli nesneyle ilişkili her olay işleyicisini çağırır.

```cpp
void InvokeAll();
template <
   typename T0
>
void InvokeAll(
   T0arg0
);
template <
   typename T0,
   typename T1
>
void InvokeAll(
   T0arg0,
   T1arg1
);
template <
   typename T0,
   typename T1,
   typename T2
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6,
   typename T7
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6,
   T7arg7
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6,
   typename T7,
   typename T8
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6,
   T7arg7,
   T8arg8
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6,
   typename T7,
   typename T8,
   typename T9
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6,
   T7arg7,
   T8arg8,
   T9arg9
);
```

### <a name="parameters"></a>Parametreler

*T0*<br/>
Diğer olay işleyicisi bağımsız değişkeninin türü.

*T1*<br/>
İlk olay işleyicisi bağımsız değişkeninin türü.

*T2*<br/>
İkinci olay işleyicisi bağımsız değişkeninin türü.

*T3*<br/>
Üçüncü olay işleyicisi bağımsız değişkeninin türü.

*T4*<br/>
Dördüncü olay işleyicisi bağımsız değişkeninin türü.

*T5*<br/>
Beşinci olay işleyicisi bağımsız değişkeninin türü.

*T6*<br/>
Altıncı olay işleyicisi bağımsız değişkeninin türü.

*T7*<br/>
Yedinci olay işleyicisi bağımsız değişkeninin türü.

*T8*<br/>
Sekizinci olay işleyicisi bağımsız değişkeninin türü.

*T9*<br/>
Dokuzuncu olay işleyicisi bağımsız değişkeninin türü.

*arg0*<br/>
Diğer olay işleyicisi bağımsız değişkeni.

*arg1*<br/>
İlk olay işleyicisi bağımsız değişkeni.

*arg2*<br/>
İkinci olay işleyicisi bağımsız değişkeni.

*arg3*<br/>
Üçüncü olay işleyicisi bağımsız değişkeni.

*arg4*<br/>
Dördüncü olay işleyicisi bağımsız değişkeni.

*arg5*<br/>
Beşinci olay işleyicisi bağımsız değişkeni.

*arg6*<br/>
Altıncı olay işleyicisi bağımsız değişkeni.

*arg7*<br/>
Yedinci olay işleyicisi bağımsız değişkeni.

*arg8*<br/>
Sekizinci olay işleyicisi bağımsız değişkeni.

*arg9*<br/>
Dokuzuncu olay işleyicisi bağımsız değişkeni.

## <a name="eventsourceremove"></a><a name="remove"></a> EventSource:: Remove

Belirtilen olay kayıt belirteci tarafından temsil edilen olay işleyicisini geçerli nesneyle ilişkili olay işleyicileri kümesinden siler `EventSource` .

```cpp
HRESULT Remove(
   EventRegistrationToken token
);
```

### <a name="parameters"></a>Parametreler

*simgesinde*<br/>
Olay işleyicisini temsil eden bir tanıtıcı. Bu belirteç, olay işleyicisi [Add ()](#add) yöntemiyle kaydedildiğinde döndürülür.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı gösteren bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Yapı hakkında daha fazla bilgi için `EventRegistrationToken` , **Windows çalışma zamanı** başvuru belgelerindeki **Windows:: Foundation:: EventRegistrationToken yapısı** konusuna bakın.

## <a name="eventsourcetargets_"></a><a name="targets"></a> EventSource:: targets_

Bir veya daha fazla olay işleyicilerinden oluşan bir dizi.

```cpp
ComPtr<Details::EventTargetArray> targets_;
```

### <a name="remarks"></a>Açıklamalar

Geçerli nesne tarafından temsil edilen olay `EventSource` oluştuğunda, olay işleyicileri çağırılır.

## <a name="eventsourcetargetspointerlock_"></a><a name="targetspointerlock"></a> EventSource:: targetsPointerLock_

Bu, için olay işleyicileri `EventSource` eklendikten, kaldırılmakta veya çağrıldığında bile iç veri üyelerine erişimi eşitler.

```cpp
Wrappers::SRWLock targetsPointerLock_;
```
