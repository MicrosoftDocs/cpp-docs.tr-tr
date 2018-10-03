---
title: Olay sınıfı (WRL) | Microsoft Docs
ms.custom: ''
ms.date: 09/24/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Event
- corewrappers/Microsoft::WRL::Wrappers::Event::Event
- corewrappers/Microsoft::WRL::Wrappers::Event::operator=
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Event class
- Microsoft::WRL::Wrappers::Event::Event, constructor
- Microsoft::WRL::Wrappers::Event::operator= operator
ms.assetid: 55dfc9fc-62d4-4bb2-9d85-5b6dd88569e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b28a6e9d30e7a31916582207901859045023ad66
ms.sourcegitcommit: d1527eb2d50156bf923f2a32ec3af9efc7fc4304
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48251190"
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
