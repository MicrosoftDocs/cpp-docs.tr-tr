---
description: 'Daha fazla bilgi edinin: EventTargetArray Sınıfı'
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
ms.openlocfilehash: ac3199d2374a47e94705f8f51672bfedd0b7bf20
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198589"
---
# <a name="eventtargetarray-class"></a>EventTargetArray Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Syntax

```cpp
class EventTargetArray :
    public Microsoft::WRL::RuntimeClass<
        Microsoft::WRL::RuntimeClassFlags<ClassicCom>,
        IUnknown
    >;
```

## <a name="remarks"></a>Açıklamalar

Bir olay işleyicileri dizisini temsil eder.

Bir [EventSource](eventsource-class.md) nesnesiyle ilişkili olay işleyicileri korunan bir `EventTargetArray` veri üyesinde saklanır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                                           | Açıklama
-------------------------------------------------------------- | -----------------------------------------------------------
[EventTargetArray:: EventTargetArray](#eventtargetarray)        | `EventTargetArray` sınıfının yeni bir örneğini başlatır.
[EventTargetArray:: ~ EventTargetArray](#tilde-eventtargetarray) | Geçerli sınıfın seçimini kaldırır `EventTargetArray` .

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                  | Açıklama
------------------------------------- | ---------------------------------------------------------------------------------------
[EventTargetArray:: AddTail](#addtail) | Belirtilen olay işleyicisini, olay işleyicilerinin iç dizisinin sonuna ekler.
[EventTargetArray:: Begin](#begin)     | Olay işleyicilerinin iç dizisindeki ilk öğenin adresini alır.
[EventTargetArray:: End](#end)         | Olay işleyicilerinin iç dizisindeki son öğenin adresini alır.
[EventTargetArray:: length](#length)   | Olay işleyicilerinin iç dizisindeki öğelerin geçerli sayısını alır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`EventTargetArray`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Event. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="eventtargetarrayeventtargetarray"></a><a name="tilde-eventtargetarray"></a> EventTargetArray:: ~ EventTargetArray

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
~EventTargetArray();
```

### <a name="remarks"></a>Açıklamalar

Geçerli sınıfın seçimini kaldırır `EventTargetArray` .

## <a name="eventtargetarrayaddtail"></a><a name="addtail"></a> EventTargetArray:: AddTail

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
void AddTail(
   _In_ IUnknown* element
);
```

### <a name="parameters"></a>Parametreler

*dosyalarında*<br/>
Eklenecek olay işleyicisine yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Belirtilen olay işleyicisini, olay işleyicilerinin iç dizisinin sonuna ekler.

`AddTail()` yalnızca sınıfı tarafından dahili olarak kullanılmak üzere tasarlanmıştır `EventSource` .

## <a name="eventtargetarraybegin"></a><a name="begin"></a> EventTargetArray:: Begin

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
ComPtr<IUnknown>* Begin();
```

### <a name="return-value"></a>Dönüş Değeri

Olay işleyicilerinin iç dizisindeki ilk öğenin adresi.

### <a name="remarks"></a>Açıklamalar

Olay işleyicilerinin iç dizisindeki ilk öğenin adresini alır.

## <a name="eventtargetarrayend"></a><a name="end"></a> EventTargetArray:: End

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
ComPtr<IUnknown>* End();
```

### <a name="return-value"></a>Dönüş Değeri

Olay işleyicilerinin iç dizisindeki son öğenin adresi.

### <a name="remarks"></a>Açıklamalar

Olay işleyicilerinin iç dizisindeki son öğenin adresini alır.

## <a name="eventtargetarrayeventtargetarray"></a><a name="eventtargetarray"></a> EventTargetArray:: EventTargetArray

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
EventTargetArray(
   _Out_ HRESULT* hr,
   size_t items
);
```

### <a name="parameters"></a>Parametreler

*sa*<br/>
Bu Oluşturucu işlemlerinden sonra, *HR* parametresi dizi ayırmanın başarılı veya başarısız olduğunu gösterir. Aşağıdaki listede *HR* için olası değerler gösterilmektedir.

- S_OK<br/>
  İşlem başarılı oldu.

- E_OUTOFMEMORY<br/>
  Dizi için bellek ayrılamadı.

- S_FALSE<br/>
  Parametre *öğeleri* sıfırdan küçük veya eşit.

*öğeler*<br/>
Ayrılacak dizi öğelerinin sayısı.

### <a name="remarks"></a>Açıklamalar

`EventTargetArray` sınıfının yeni bir örneğini başlatır.

`EventTargetArray` bir nesnede olay işleyicileri dizisini tutmak için kullanılır `EventSource` .

## <a name="eventtargetarraylength"></a><a name="length"></a> EventTargetArray:: length

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
size_t Length();
```

### <a name="return-value"></a>Dönüş Değeri

Olay işleyicilerinin iç dizisindeki geçerli öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Olay işleyicilerinin iç dizisindeki öğelerin geçerli sayısını alır.
