---
description: 'Daha fazla bilgi edinin: Event Class (WRL)'
title: Event sınıfı (WRL)
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
ms.openlocfilehash: e3a61a40d1160830df80a7e0650e60fbf803e3d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272831"
---
# <a name="event-class-wrl"></a>Event sınıfı (WRL)

Bir olayı temsil eder.

## <a name="syntax"></a>Syntax

```cpp
class Event : public HandleT<HandleTraits::EventTraits>;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                   | Açıklama
---------------------- | ------------------------------------------------
[Event:: Event](#event) | `Event` sınıfının yeni bir örneğini başlatır.

### <a name="public-operators"></a>Ortak İşleçler

Ad                                 | Açıklama
------------------------------------ | ------------------------------------------------------------------------
[Event:: operator =](#operator-assign) | Belirtilen `Event` başvuruyu geçerli `Event` örneğe atar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HandleT`

`Event`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrapper. h

**Ad alanı:** Microsoft:: WRL:: sarmalayıcılar

## <a name="eventevent"></a><a name="event"></a> Event:: Event

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

*h*<br/>
Bir olayı işleyin. Varsayılan olarak, *h* olarak başlatılır **`nullptr`** .

## <a name="eventoperator"></a><a name="operator-assign"></a> Event:: operator =

Belirtilen `Event` başvuruyu geçerli `Event` örneğe atar.

```cpp
WRL_NOTHROW Event& operator=(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
Bir örneğe rvalue başvurusu `Event` .

### <a name="return-value"></a>Dönüş Değeri

Geçerli örneğe yönelik bir işaretçi `Event` .
