---
description: 'Daha fazla bilgi edinin: Handlenitelikleri yapısı'
title: HANDLETraits Yapısı
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::GetInvalidValue
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits structure
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close method
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::GetInvalidValue method
ms.assetid: 22963e88-d857-4624-9182-7c986daff722
ms.openlocfilehash: c3eef03c724b1ba868ba67ed251acdb310d8b66f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250029"
---
# <a name="handletraits-structure"></a>HANDLETraits Yapısı

Bir tanıtıcının ortak özelliklerini tanımlar.

## <a name="syntax"></a>Syntax

```cpp
struct HANDLETraits;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

Ad   | Açıklama
------ | ---------------------
`Type` | TANıTıCı için eş anlamlı.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                              | Açıklama
------------------------------------------------- | -----------------------------
[Handlenitelikler:: Close](#close)                     | Belirtilen tanıtıcıyı kapatır.
[Handlenitelikleri:: GetInvalidValue](#getinvalidvalue) | Geçersiz bir tanıtıcıyı temsil eder.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HANDLETraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrapper. h

**Ad alanı:** Microsoft:: WRL:: sarmalayıcılar:: Handlenitelikler

## <a name="handletraitsclose"></a><a name="close"></a> Handlenitelikler:: Close

Belirtilen tanıtıcıyı kapatır.

```cpp
inline static bool Close(
   _In_ Type h
);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
Kapatılacak tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

**`true`** tanıtıcı *h* başarıyla kapatılırsa Aksi takdirde, **`false`** .

## <a name="handletraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a> Handlenitelikleri:: GetInvalidValue

Geçersiz bir tanıtıcıyı temsil eder.

```cpp
inline static HANDLE GetInvalidValue();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman INVALID_HANDLE_VALUE döndürür. (INVALID_HANDLE_VALUE, Windows tarafından tanımlanır.)
