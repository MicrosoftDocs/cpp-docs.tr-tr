---
title: Etkinlik Sınıfı (WRL)
ms.date: 09/24/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Event
- corewrappers/Microsoft::WRL::Wrappers::Event::Event
- corewrappers/Microsoft::WRL::Wrappers::Event::operator=
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Event class
- Microsoft::WRL::Wrappers::Event::Event, constructor
- Microsoft::WRL::Wrappers::Event::operator= operator
ms.assetid: 55dfc9fc-62d4-4bb2-9d85-5b6dd88569e8
ms.openlocfilehash: 85b4c2d1f1a27e90a65e47aa749e079f4aa08739
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371528"
---
# <a name="event-class-wrl"></a>Etkinlik Sınıfı (WRL)

Bir olayı temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class Event : public HandleT<HandleTraits::EventTraits>;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Adı                   | Açıklama
---------------------- | ------------------------------------------------
[Etkinlik::Olay](#event) | `Event` sınıfının yeni bir örneğini başlatır.

### <a name="public-operators"></a>Ortak İşleçler

Adı                                 | Açıklama
------------------------------------ | ------------------------------------------------------------------------
[Olay::operator=](#operator-assign) | Belirtilen `Event` başvuruyu geçerli `Event` örneğe atar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HandleT`

`Event`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrappers.h

**Ad alanı:** Microsoft::WRL::Sarmalayıcılar

## <a name="eventevent"></a><a name="event"></a>Etkinlik::Olay

`Event` sınıfının yeni bir örneğini başlatır.

```cpp
explicit Event(
   HANDLE h = HandleT::Traits::GetInvalidValue()
);
WRL_NOTHROW Event(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>Parametreler

*H*<br/>
Bir olayı ele alın. Varsayılan olarak, *h* ' `nullptr`ye başharf.

## <a name="eventoperator"></a><a name="operator-assign"></a>Olay::operator=

Belirtilen `Event` başvuruyu geçerli `Event` örneğe atar.

```cpp
WRL_NOTHROW Event& operator=(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>Parametreler

*H*<br/>
Bir `Event` örneğin rvalue-başvurusu.

### <a name="return-value"></a>Dönüş Değeri

Geçerli örneğinbir `Event` işaretçisi.
