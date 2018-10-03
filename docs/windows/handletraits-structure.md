---
title: HANDLETraits yapısı | Microsoft Docs
ms.custom: ''
ms.date: 09/27/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::GetInvalidValue
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits structure
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close method
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::GetInvalidValue method
ms.assetid: 22963e88-d857-4624-9182-7c986daff722
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 33181b2cf477c3f753eacf63110a426b36e62b31
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235275"
---
# <a name="handletraits-structure"></a>HANDLETraits Yapısı

Bir tanıtıcı genel özelliklerini tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
struct HANDLETraits;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

Ad   | Açıklama
------ | ---------------------
`Type` | İŞLEYİCİ için bir eşanlamlı.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                              | Açıklama
------------------------------------------------- | -----------------------------
[HANDLETraits::Close](#close)                     | Belirtilen tanıtıcı kapatır.
[Handletraits::getınvalidvalue](#getinvalidvalue) | Geçersiz bir tanıtıcı temsil eder.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HANDLETraits`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="close"></a>HANDLETraits::Close

Belirtilen tanıtıcı kapatır.

```cpp
inline static bool Close(
   _In_ Type h
);
```

### <a name="parameters"></a>Parametreler

*h*<br/>
Kapatmak için tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

`true` varsa işlemek *h* kapalı başarıyla; Aksi takdirde `false`.

## <a name="getinvalidvalue"></a>Handletraits::getınvalidvalue

Geçersiz bir tanıtıcı temsil eder.

```cpp
inline static HANDLE GetInvalidValue();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman INVALID_HANDLE_VALUE döndürür. (INVALID_HANDLE_VALUE Windows tarafından tanımlanır.)
