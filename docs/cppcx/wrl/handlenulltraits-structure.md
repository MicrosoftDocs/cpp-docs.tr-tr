---
description: 'Daha fazla bilgi edinin: Handlenullnitelikler yapısı'
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
ms.openlocfilehash: 14d5eaab36be24b5450b66c35c9cf5cbba39ea4d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229255"
---
# <a name="handlenulltraits-structure"></a>HANDLENullTraits Yapısı

Başlatılmamış tanıtıcının ortak özelliklerini tanımlar.

## <a name="syntax"></a>Syntax

```cpp
struct HANDLENullTraits;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

Ad   | Açıklama
------ | ---------------------
`Type` | TANıTıCı için eş anlamlı.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                  | Açıklama
----------------------------------------------------- | -----------------------------
[Handlenullnitelikler:: Close](#close)                     | Belirtilen tanıtıcıyı kapatır.
[Handlenullnitelikler:: GetInvalidValue](#getinvalidvalue) | Geçersiz bir tanıtıcıyı temsil eder.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HANDLENullTraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrapper. h

**Ad alanı:** Microsoft:: WRL:: sarmalayıcılar:: Handlenitelikler

## <a name="handlenulltraitsclose"></a><a name="close"></a> Handlenullnitelikler:: Close

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

## <a name="handlenulltraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a> Handlenullnitelikler:: GetInvalidValue

Geçersiz bir tanıtıcıyı temsil eder.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman döndürülür **`nullptr`** .
