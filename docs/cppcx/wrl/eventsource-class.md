---
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
ms.openlocfilehash: bb9151e55d133e3e5d8bf10baeb8448101ad6ce0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371536"
---
# <a name="eventsource-class"></a>EventSource Sınıfı

Çevik olmayan bir olayı temsil eder. `EventSource`üye işlevler olay işleyicileri ekleyin, kaldırın ve çağırır. Çevik olaylar için [AgileEventSource'u](agileeventsource-class.md)kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename TDelegateInterface>
class EventSource;
```

### <a name="parameters"></a>Parametreler

*TDelegateArayüzü*<br/>
Olay işleyicisini temsil eden bir temsilcinin arabirimi.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

| Adı                                     | Açıklama                                            |
| ---------------------------------------- | ------------------------------------------------------ |
| [EventSource::EventSource](#eventsource) | `EventSource` sınıfının yeni bir örneğini başlatır. |

### <a name="public-methods"></a>Ortak Yöntemler

| Adı                                 | Açıklama                                                                                                                                                      |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [EventSource::Ekle](#add)             | Belirtilen temsilci arabirimi tarafından temsil edilen olay işleyicisini geçerli `EventSource` nesne için olay işleyicileri kümesine ekler.                     |
| [EventSource::GetSize](#getsize)     | Geçerli `EventSource` nesneyle ilişkili olay işleyicilerinin sayısını alır.                                                                         |
| [EventSource::InvokeAll](#invokeall) | Belirtilen bağımsız değişken türlerini `EventSource` ve bağımsız değişkenlerini kullanarak geçerli nesneyle ilişkili her olay işleyicisini çağırır.                                      |
| [EventSource::Kaldır](#remove)       | Geçerli `EventSource` nesneyle ilişkili olay işleyicileri kümesinden belirtilen olay kaydı belirteci tarafından temsil edilen olay işleyicisini siler. |

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

| Adı                                                    | Açıklama                                                                                                                       |
| ------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| [EventSource:addRemoveLock_](#addremovelock)           | Olay işleyicileri eklerken, kaldırırken veya çağırırken [targets_](#targets) diziye erişimi eşitler.                          |
| [EventSource:targets_](#targets)                       | Bir veya daha fazla olay işleyicisi dizisi.                                                                                           |
| [OlayKaynak:targetsPointerLock_](#targetspointerlock) | Bu EventSource'un olay işleyicileri eklenirken, kaldırılırken veya çağrılsa bile dahili veri üyelerine erişimi eşitler. |

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`EventSource`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** event.h

**Ad alanı:** Microsoft::WRL

## <a name="eventsourceadd"></a><a name="add"></a>EventSource::Ekle

Belirtilen temsilci arabirimi tarafından temsil edilen olay işleyicisini geçerli `EventSource` nesne için olay işleyicileri kümesine ekler.

```cpp
HRESULT Add(
   _In_ TDelegateInterface* delegateInterface,
   _Out_ EventRegistrationToken* token
);
```

### <a name="parameters"></a>Parametreler

*delegeArayüz*<br/>
Olay işleyicisini temsil eden bir temsilci nesnesine arabirim.

*token*<br/>
Bu işlem tamamlandığında, olayı temsil eden bir tutamaç. Olay işleyicisini atmak için [Kaldır()](#remove) yönteminin parametresi olarak bu belirteci kullanın.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, hatayı gösteren bir HRESULT.

## <a name="eventsourceaddremovelock_"></a><a name="addremovelock"></a>EventSource:addRemoveLock_

Olay işleyicileri eklerken, kaldırırken veya çağırırken [targets_](#targets) diziye erişimi eşitler.

```cpp
Wrappers::SRWLock addRemoveLock_;
```

## <a name="eventsourceeventsource"></a><a name="eventsource"></a>EventSource::EventSource

`EventSource` sınıfının yeni bir örneğini başlatır.

```cpp
EventSource();
```

## <a name="eventsourcegetsize"></a><a name="getsize"></a>EventSource::GetSize

Geçerli `EventSource` nesneyle ilişkili olay işleyicilerinin sayısını alır.

```cpp
size_t GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

[targets_'daki](#targets)olay işleyicilerinin sayısı.

## <a name="eventsourceinvokeall"></a><a name="invokeall"></a>EventSource::InvokeAll

Belirtilen bağımsız değişken türlerini `EventSource` ve bağımsız değişkenlerini kullanarak geçerli nesneyle ilişkili her olay işleyicisini çağırır.

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
Sıfırıncı olay işleyicisi bağımsız değişkeninin türü.

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
Sıfırıncı olay işleyicisi bağımsız değişkeni.

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

## <a name="eventsourceremove"></a><a name="remove"></a>EventSource::Kaldır

Geçerli `EventSource` nesneyle ilişkili olay işleyicileri kümesinden belirtilen olay kaydı belirteci tarafından temsil edilen olay işleyicisini siler.

```cpp
HRESULT Remove(
   EventRegistrationToken token
);
```

### <a name="parameters"></a>Parametreler

*token*<br/>
Olay işleyicisi temsil eden bir tanıtıcı. Bu belirteç, olay işleyicisi [Ekle()](#add) yöntemi yle kaydedildiğinde döndürüldü.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, hatayı gösteren bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Yapı hakkında daha fazla bilgi için **Windows::Foundation::EventRegistrationToken Yapı** konusuna bakın. **Windows Runtime** `EventRegistrationToken`

## <a name="eventsourcetargets_"></a><a name="targets"></a>EventSource:targets_

Bir veya daha fazla olay işleyicisi dizisi.

```cpp
ComPtr<Details::EventTargetArray> targets_;
```

### <a name="remarks"></a>Açıklamalar

Geçerli `EventSource` nesne tarafından temsil edilen olay oluştuğunda, olay işleyicileri çağrılır.

## <a name="eventsourcetargetspointerlock_"></a><a name="targetspointerlock"></a>OlayKaynak:targetsPointerLock_

Bunun `EventSource` için olay işleyicileri eklenirken, kaldırılırken veya çağrılsa bile dahili veri üyelerine erişimi eşitler.

```cpp
Wrappers::SRWLock targetsPointerLock_;
```
