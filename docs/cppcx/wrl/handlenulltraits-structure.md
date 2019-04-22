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
ms.openlocfilehash: d70425f414b998eb67e3937c2c126dd3eda0c00d
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58787615"
---
# <a name="handlenulltraits-structure"></a>HANDLENullTraits Yapısı

Başlatılmamış bir tanıtıcı genel özelliklerini tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
struct HANDLENullTraits;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

Ad   | Açıklama
------ | ---------------------
`Type` | İŞLEYİCİ için bir eşanlamlı.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                  | Açıklama
----------------------------------------------------- | -----------------------------
[HANDLENullTraits::Close](#close)                     | Belirtilen tanıtıcı kapatır.
[Handlenulltraits::getınvalidvalue](#getinvalidvalue) | Geçersiz bir tanıtıcı temsil eder.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HANDLENullTraits`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="close"></a>HANDLENullTraits::Close

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

**doğru** , tanıtıcı *h* kapalı başarıyla; Aksi takdirde **false**.

## <a name="getinvalidvalue"></a>Handlenulltraits::getınvalidvalue

Geçersiz bir tanıtıcı temsil eder.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman döndürür `nullptr`.
