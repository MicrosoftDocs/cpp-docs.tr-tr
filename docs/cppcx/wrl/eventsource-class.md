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
ms.openlocfilehash: e9070fe756410e3e1bb1e5840eb3f06e29c2f46b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398517"
---
# <a name="eventsource-class"></a>EventSource Sınıfı

Çevik olmayan bir olayı temsil eder. `EventSource` üye işlevleri ekleme, kaldırma ve olay işleyicilerini çağırır. Çevik olaylar için kullanın [AgileEventSource](agileeventsource-class.md).

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename TDelegateInterface>
class EventSource;
```

### <a name="parameters"></a>Parametreler

*TDelegateInterface*<br/>
Bir olay işleyicisi temsil eden bir temsilci için arabirim.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

| Ad                                     | Açıklama                                            |
| ---------------------------------------- | ------------------------------------------------------ |
| [EventSource::EventSource](#eventsource) | Yeni bir örneğini başlatır `EventSource` sınıfı. |

### <a name="public-methods"></a>Ortak Yöntemler

| Ad                                 | Açıklama                                                                                                                                                      |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [EventSource::Add](#add)             | Ekler için geçerli olay işleyicileri kümesini belirtilen temsilci arabirimi tarafından temsil edilen olay işleyicisi `EventSource` nesne.                     |
| [EventSource::GetSize](#getsize)     | Geçerli ile ilişkili olay işleyicileri sayısını alır `EventSource` nesne.                                                                         |
| [EventSource::ınvokeall](#invokeall) | Geçerli ile ilgili her olay işleyicisini çağırır `EventSource` belirtilen bağımsız değişken türleri ve bağımsız değişkenleri kullanarak nesne.                                      |
| [EventSource::Remove](#remove)       | Olay işleyicisi geçerli ile ilişkili olay işleyicileri kümesinden tarafından belirtilen olay kaydı belirtecini temsil siler `EventSource` nesne. |

### <a name="protected-data-members"></a>Korumalı veri üyeleri

| Ad                                                    | Açıklama                                                                                                                       |
| ------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| [EventSource::addRemoveLock_](#addremovelock)           | Erişimi eşitler [targets_](#targets) eklerken dizi, kaldırma veya olay işleyicisi çağırma.                          |
| [EventSource::targets_](#targets)                       | Bir veya daha fazla olay işleyicileri dizisi.                                                                                           |
| [EventSource::targetsPointerLock_](#targetspointerlock) | Bu EventSource için olay işleyicileri bile eklenmiş olsa da kaldırılan veya çağrılan iç veri üyelerine erişimi eşitler. |

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`EventSource`

## <a name="requirements"></a>Gereksinimler

**Başlık:** event.h

**Namespace:** Microsoft::WRL

## <a name="add"></a>EventSource::Add

Ekler için geçerli olay işleyicileri kümesini belirtilen temsilci arabirimi tarafından temsil edilen olay işleyicisi `EventSource` nesne.

```cpp
HRESULT Add(
   _In_ TDelegateInterface* delegateInterface,
   _Out_ EventRegistrationToken* token
);
```

### <a name="parameters"></a>Parametreler

*delegateInterface*<br/>
Bir olay işleyicisi temsil eden bir temsilci nesnesi için arabirim.

*Belirteç*<br/>
Bu işlem tamamlandığında, olayı temsil eden bir işleyici. Parametre olarak bu belirteci kullanmasına [foreach()](#remove) olay işleyicisi atmak için yöntemi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

## <a name="addremovelock"></a>EventSource::addRemoveLock_

Erişimi eşitler [targets_](#targets) eklerken dizi, kaldırma veya olay işleyicisi çağırma.

```cpp
Wrappers::SRWLock addRemoveLock_;
```

## <a name="eventsource"></a>EventSource::EventSource

Yeni bir örneğini başlatır `EventSource` sınıfı.

```cpp
EventSource();
```

## <a name="getsize"></a>EventSource::GetSize

Geçerli ile ilişkili olay işleyicileri sayısını alır `EventSource` nesne.

```cpp
size_t GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olay işleyicileri sayısını [targets_](#targets).

## <a name="invokeall"></a>EventSource::ınvokeall

Geçerli ile ilgili her olay işleyicisini çağırır `EventSource` belirtilen bağımsız değişken türleri ve bağımsız değişkenleri kullanarak nesne.

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
Sıfırıncı olay işleyicisi bağımsız değişken türü.

*T1*<br/>
İlk olay işleyicisi bağımsız değişken türü.

*T2*<br/>
İkinci olay işleyicisi bağımsız değişken türü.

*T3*<br/>
Üçüncü olay işleyicisi bağımsız değişken türü.

*T4*<br/>
Dördüncü olay işleyicisi bağımsız değişken türü.

*T5*<br/>
Beşinci olay işleyicisi bağımsız değişken türü.

*T6*<br/>
Altıncı olay işleyicisi bağımsız değişken türü.

*T7*<br/>
Yedinci olay işleyicisi bağımsız değişken türü.

*T8*<br/>
Sekizinci olay işleyicisi bağımsız değişken türü.

*T9*<br/>
Dokuzuncu olay işleyicisi bağımsız değişken türü.

*arg0*<br/>
Sıfırıncı olay işleyicisi bağımsız değişken.

*arg1*<br/>
İlk olay işleyicisi bağımsız değişken.

*arg2*<br/>
İkinci olay işleyicisi bağımsız değişken.

*Arg3*<br/>
Üçüncü olay işleyicisi bağımsız değişken.

*Arg4*<br/>
Dördüncü olay işleyicisi bağımsız değişken.

*arg5*<br/>
Beşinci olay işleyicisi bağımsız.

*arg6*<br/>
Altıncı olay işleyicisi bağımsız değişken.

*arg7*<br/>
Yedinci olay işleyicisi bağımsız değişken.

*arg8*<br/>
Sekizinci olay işleyicisi bağımsız değişken.

*arg9*<br/>
Dokuzuncu olay işleyicisi bağımsız değişken.

## <a name="remove"></a>EventSource::Remove

Olay işleyicisi geçerli ile ilişkili olay işleyicileri kümesinden tarafından belirtilen olay kaydı belirtecini temsil siler `EventSource` nesne.

```cpp
HRESULT Remove(
   EventRegistrationToken token
);
```

### <a name="parameters"></a>Parametreler

*Belirteç*<br/>
Bir olay işleyicisi temsil eden bir tanıtıcı. Olay işleyicisi tarafından kaydedildiğinde bu belirteci döndürüldü [Add()](#add) yöntemi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

### <a name="remarks"></a>Açıklamalar

Hakkında daha fazla bilgi için `EventRegistrationToken` yapısı için bkz: **:: eventregistrationtoken yapısı** konudaki **Windows çalışma zamanı** başvuru belgeleri.

## <a name="targets"></a>EventSource::targets_

Bir veya daha fazla olay işleyicileri dizisi.

```cpp
ComPtr<Details::EventTargetArray> targets_;
```

### <a name="remarks"></a>Açıklamalar

Zaman geçerli tarafından temsil edilen olay `EventSource` nesne oluşturulur, olay işleyicileri olarak adlandırılır.

## <a name="targetspointerlock"></a>EventSource::targetsPointerLock_

Bunun için olay işleyicileri çalışırken bile iç veri üyelerine erişimi eşitler `EventSource` kaldırılan veya çağrılan eklenmektedir.

```cpp
Wrappers::SRWLock targetsPointerLock_;
```
