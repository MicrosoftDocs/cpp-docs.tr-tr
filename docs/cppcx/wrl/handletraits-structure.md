---
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
ms.openlocfilehash: 604098cd3289722767117910d6e44e272dcb8b77
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371443"
---
# <a name="handletraits-structure"></a>HANDLETraits Yapısı

Bir tutamacın ortak özelliklerini tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
struct HANDLETraits;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

Adı   | Açıklama
------ | ---------------------
`Type` | HANDLE ile eş anlamlıdır.

### <a name="public-methods"></a>Ortak Yöntemler

Adı                                              | Açıklama
------------------------------------------------- | -----------------------------
[HANDLETraits::Kapat](#close)                     | Belirtilen tutamacı kapatır.
[HANDLETraits::GetInvalidValue](#getinvalidvalue) | Geçersiz bir tutamacı temsil eder.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HANDLETraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrappers.h

**Ad alanı:** Microsoft::WRL::Sarmalayıcılar::HandleTraits

## <a name="handletraitsclose"></a><a name="close"></a>HANDLETraits::Kapat

Belirtilen tutamacı kapatır.

```cpp
inline static bool Close(
   _In_ Type h
);
```

### <a name="parameters"></a>Parametreler

*H*<br/>
Kapama kıyı.

### <a name="return-value"></a>Dönüş Değeri

*h* kolu başarıyla kapalı ise **doğru;** aksi takdirde, **yanlış**.

## <a name="handletraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a>HANDLETraits::GetInvalidValue

Geçersiz bir tutamacı temsil eder.

```cpp
inline static HANDLE GetInvalidValue();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman INVALID_HANDLE_VALUE döner. (INVALID_HANDLE_VALUE Windows tarafından tanımlanır.)
