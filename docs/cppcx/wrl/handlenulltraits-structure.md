---
title: HANDLENullTraits Yapısı
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::GetInvalidValue
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::Close method
- Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::GetInvalidValue method
ms.assetid: 88a29a14-c516-40cb-a0ca-ee897a668623
ms.openlocfilehash: 41e06cc50f36a077a34d992c416a543e5bf9b593
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371471"
---
# <a name="handlenulltraits-structure"></a>HANDLENullTraits Yapısı

Başharfe getirilmemiş bir tutamacın ortak özelliklerini tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
struct HANDLENullTraits;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

Adı   | Açıklama
------ | ---------------------
`Type` | HANDLE ile eş anlamlıdır.

### <a name="public-methods"></a>Ortak Yöntemler

Adı                                                  | Açıklama
----------------------------------------------------- | -----------------------------
[HANDLENullTraits::Kapat](#close)                     | Belirtilen tutamacı kapatır.
[HANDLENullTraits::GetInvalidValue](#getinvalidvalue) | Geçersiz bir tutamacı temsil eder.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HANDLENullTraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrappers.h

**Ad alanı:** Microsoft::WRL::Sarmalayıcılar::HandleTraits

## <a name="handlenulltraitsclose"></a><a name="close"></a>HANDLENullTraits::Kapat

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

## <a name="handlenulltraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a>HANDLENullTraits::GetInvalidValue

Geçersiz bir tutamacı temsil eder.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman `nullptr` döndürür.
