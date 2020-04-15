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
ms.openlocfilehash: 9ea8800aa22a6b5cae0b3342cf337786fb53fc76
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371492"
---
# <a name="eventtargetarray-class"></a>EventTargetArray Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

## <a name="syntax"></a>Sözdizimi

```cpp
class EventTargetArray :
    public Microsoft::WRL::RuntimeClass<
        Microsoft::WRL::RuntimeClassFlags<ClassicCom>,
        IUnknown
    >;
```

## <a name="remarks"></a>Açıklamalar

Olay işleyicileri bir dizi temsil eder.

[Bir EventSource](eventsource-class.md) nesnesi ile ilişkili olay işleyicileri `EventTargetArray` korumalı bir veri üyesinde depolanır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Adı                                                           | Açıklama
-------------------------------------------------------------- | -----------------------------------------------------------
[EventTargetArray::EventTargetArray](#eventtargetarray)        | `EventTargetArray` sınıfının yeni bir örneğini başlatır.
[EventTargetArray::~EventTargetArray](#tilde-eventtargetarray) | Geçerli `EventTargetArray` sınıfı deinitialize eder.

### <a name="public-methods"></a>Ortak Yöntemler

Adı                                  | Açıklama
------------------------------------- | ---------------------------------------------------------------------------------------
[EventTargetArray::AddTail](#addtail) | Belirtilen olay işleyicisini olay işleyicilerinin iç dizisinin sonuna ekler.
[EventTargetArray::Başla](#begin)     | Olay işleyicileri iç dizisinde ilk öğenin adresini alır.
[EventTargetArray::Bitiş](#end)         | Olay işleyicileri iç dizisinde son öğenin adresini alır.
[EventTargetArray::Uzunluk](#length)   | Olay işleyicilerinin iç dizisindeki geçerli öğe sayısını alır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`EventTargetArray`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** event.h

**Ad alanı:** Microsoft::WRL::D etails

## <a name="eventtargetarrayeventtargetarray"></a><a name="tilde-eventtargetarray"></a>EventTargetArray::~EventTargetArray

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
~EventTargetArray();
```

### <a name="remarks"></a>Açıklamalar

Geçerli `EventTargetArray` sınıfı deinitialize eder.

## <a name="eventtargetarrayaddtail"></a><a name="addtail"></a>EventTargetArray::AddTail

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
void AddTail(
   _In_ IUnknown* element
);
```

### <a name="parameters"></a>Parametreler

*Öğe*<br/>
Eklemek için olay işleyicisine işaretçi.

### <a name="remarks"></a>Açıklamalar

Belirtilen olay işleyicisini olay işleyicilerinin iç dizisinin sonuna ekler.

`AddTail()`yalnızca `EventSource` sınıf tarafından dahili olarak kullanılmak üzere tasarlanmıştır.

## <a name="eventtargetarraybegin"></a><a name="begin"></a>EventTargetArray::Başla

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
ComPtr<IUnknown>* Begin();
```

### <a name="return-value"></a>Dönüş Değeri

Olay işleyicileri iç dizisinde ilk öğenin adresi.

### <a name="remarks"></a>Açıklamalar

Olay işleyicileri iç dizisinde ilk öğenin adresini alır.

## <a name="eventtargetarrayend"></a><a name="end"></a>EventTargetArray::Bitiş

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
ComPtr<IUnknown>* End();
```

### <a name="return-value"></a>Dönüş Değeri

Olay işleyicileri iç dizisinde son öğenin adresi.

### <a name="remarks"></a>Açıklamalar

Olay işleyicileri iç dizisinde son öğenin adresini alır.

## <a name="eventtargetarrayeventtargetarray"></a><a name="eventtargetarray"></a>EventTargetArray::EventTargetArray

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
EventTargetArray(
   _Out_ HRESULT* hr,
   size_t items
);
```

### <a name="parameters"></a>Parametreler

*Hr*<br/>
Bu oluşturucu işlemden sonra, parametre *İk* dizi tahsisinin başarılı olup olmadığını veya başarısız olup olmadığını gösterir. Aşağıdaki liste *hr*için olası değerleri gösterir.

- S_OK<br/>
  Operasyon başarılı oldu.

- E_outofmemory<br/>
  Bellek dizi için tahsis edileemedi.

- S_false<br/>
  Parametre *öğeleri* sıfırdan küçük veya eşittir.

*Bileşen*<br/>
Ayrılacak dizi öğelerinin sayısı.

### <a name="remarks"></a>Açıklamalar

`EventTargetArray` sınıfının yeni bir örneğini başlatır.

`EventTargetArray`bir `EventSource` nesnede olay işleyicileri bir dizi tutmak için kullanılır.

## <a name="eventtargetarraylength"></a><a name="length"></a>EventTargetArray::Uzunluk

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
size_t Length();
```

### <a name="return-value"></a>Dönüş Değeri

Olay işleyicilerinin iç dizisindeki öğelerin geçerli sayısı.

### <a name="remarks"></a>Açıklamalar

Olay işleyicilerinin iç dizisindeki geçerli öğe sayısını alır.
