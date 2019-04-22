---
title: Olay sınıfı (WRL)
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
ms.openlocfilehash: 2d36b4fa3d1824f43e0cfafe55c439a6bdeccb6f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58787782"
---
# <a name="event-class-wrl"></a>Olay sınıfı (WRL)

Bir olayı temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class Event : public HandleT<HandleTraits::EventTraits>;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                   | Açıklama
---------------------- | ------------------------------------------------
[Event::Event](#event) | Yeni bir örneğini başlatır `Event` sınıfı.

### <a name="public-operators"></a>Ortak İşleçler

Ad                                 | Açıklama
------------------------------------ | ------------------------------------------------------------------------
[Event::operator =](#operator-assign) | Belirtilen atar `Event` geçerli başvuru `Event` örneği.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HandleT`

`Event`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="event"></a>Event::Event

Yeni bir örneğini başlatır `Event` sınıfı.

```cpp
explicit Event(
   HANDLE h = HandleT::Traits::GetInvalidValue()
);
WRL_NOTHROW Event(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
Bir olay tanıtıcısı olarak ekleyin. Varsayılan olarak, *h* değerine ayarlanır `nullptr`.

## <a name="operator-assign"></a>Event::operator =

Belirtilen atar `Event` geçerli başvuru `Event` örneği.

```cpp
WRL_NOTHROW Event& operator=(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
Bir rvalue başvurusuna bir `Event` örneği.

### <a name="return-value"></a>Dönüş Değeri

Geçerli bir işaretçi `Event` örneği.
