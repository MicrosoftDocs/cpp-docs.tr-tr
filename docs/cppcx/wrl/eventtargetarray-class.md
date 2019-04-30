---
title: EventTargetArray Sınıfı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray
- event/Microsoft::WRL::Details::EventTargetArray::AddTail
- event/Microsoft::WRL::Details::EventTargetArray::Begin
- event/Microsoft::WRL::Details::EventTargetArray::End
- event/Microsoft::WRL::Details::EventTargetArray::EventTargetArray
- event/Microsoft::WRL::Details::EventTargetArray::Length
- event/Microsoft::WRL::Details::EventTargetArray::~EventTargetArray
helpviewer_keywords:
- Microsoft::WRL::Details::EventTargetArray class
- Microsoft::WRL::Details::EventTargetArray::AddTail method
- Microsoft::WRL::Details::EventTargetArray::Begin method
- Microsoft::WRL::Details::EventTargetArray::End method
- Microsoft::WRL::Details::EventTargetArray::EventTargetArray, constructor
- Microsoft::WRL::Details::EventTargetArray::Length method
- Microsoft::WRL::Details::EventTargetArray::~EventTargetArray, destructor
ms.assetid: e3cadb7c-2160-4cbb-a2f8-c28733d1e96d
ms.openlocfilehash: 1f3f8e299dba1f4b6ae5a5767f11989dc2fe8370
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398491"
---
# <a name="eventtargetarray-class"></a>EventTargetArray Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
class EventTargetArray :
    public Microsoft::WRL::RuntimeClass<
        Microsoft::WRL::RuntimeClassFlags<ClassicCom>,
        IUnknown
    >;
```

## <a name="remarks"></a>Açıklamalar

Olay işleyicileri dizisini temsil eder.

İlişkili olay işleyicileri bir [EventSource](eventsource-class.md) nesnesi depolanır, korumalı bir `EventTargetArray` veri üyesi.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                                           | Açıklama
-------------------------------------------------------------- | -----------------------------------------------------------
[EventTargetArray::EventTargetArray](#eventtargetarray)        | Yeni bir örneğini başlatır `EventTargetArray` sınıfı.
[EventTargetArray:: ~ EventTargetArray](#tilde-eventtargetarray) | Geçerli başlatılmasını geri alır `EventTargetArray` sınıfı.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                  | Açıklama
------------------------------------- | ---------------------------------------------------------------------------------------
[EventTargetArray::AddTail](#addtail) | Belirtilen olay işleyicisi, olay işleyicileri iç dizi sonuna ekler.
[EventTargetArray::Begin](#begin)     | Olay işleyicilerini iç dizideki ilk öğenin adresi alır.
[EventTargetArray::End](#end)         | Son öğenin adresi olay işleyicileri içinde iç dizisini alır.
[EventTargetArray::Length](#length)   | Olay işleyicilerini iç dizisinde geçerli öğe sayısını alır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`EventTargetArray`

## <a name="requirements"></a>Gereksinimler

**Başlık:** event.h

**Namespace:** Microsoft::wrl:: details

## <a name="tilde-eventtargetarray"></a>EventTargetArray:: ~ EventTargetArray

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
~EventTargetArray();
```

### <a name="remarks"></a>Açıklamalar

Geçerli başlatılmasını geri alır `EventTargetArray` sınıfı.

## <a name="addtail"></a>EventTargetArray::AddTail

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
void AddTail(
   _In_ IUnknown* element
);
```

### <a name="parameters"></a>Parametreler

*Öğesi*<br/>
Olay işleyicisi eklemek için işaretçi.

### <a name="remarks"></a>Açıklamalar

Belirtilen olay işleyicisi, olay işleyicileri iç dizi sonuna ekler.

`AddTail()` yalnızca tarafından dahili olarak kullanılması amaçlanmıştır `EventSource` sınıfı.

## <a name="begin"></a>EventTargetArray::Begin

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
ComPtr<IUnknown>* Begin();
```

### <a name="return-value"></a>Dönüş Değeri

Olay işleyicileri iç dizideki ilk öğe adresi.

### <a name="remarks"></a>Açıklamalar

Olay işleyicilerini iç dizideki ilk öğenin adresi alır.

## <a name="end"></a>EventTargetArray::End

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
ComPtr<IUnknown>* End();
```

### <a name="return-value"></a>Dönüş Değeri

Olay işleyicilerini iç dizi içindeki son öğeden adresi.

### <a name="remarks"></a>Açıklamalar

Son öğenin adresi olay işleyicileri içinde iç dizisini alır.

## <a name="eventtargetarray"></a>EventTargetArray::EventTargetArray

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
EventTargetArray(
   _Out_ HRESULT* hr,
   size_t items
);
```

### <a name="parameters"></a>Parametreler

*İK*<br/>
Bu oluşturucu işlemlerinden sonra parametre *ik* dizinin ayırma başarılı veya başarısız olduğunu gösterir. Aşağıdaki liste için olası değerler gösterir *ik*.

+   S_OK<br/>
    İşlem başarılı oldu.

+   E_OUTOFMEMORY<br/>
    Dizi için bellek ayrılamıyor.

+   S_FALSE<br/>
    Parametre *öğeleri* sıfırdan küçük veya ona eşit.

*Öğeleri*<br/>
Ayrılacak dizi öğelerinin sayısı.

### <a name="remarks"></a>Açıklamalar

Yeni bir örneğini başlatır `EventTargetArray` sınıfı.

`EventTargetArray` bir dizi olay işleyicileri tutmak için kullanılan bir `EventSource` nesne.

## <a name="length"></a>EventTargetArray::Length

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
size_t Length();
```

### <a name="return-value"></a>Dönüş Değeri

Olay işleyicileri iç dizideki öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Olay işleyicilerini iç dizisinde geçerli öğe sayısını alır.
