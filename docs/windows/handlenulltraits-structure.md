---
title: HANDLENullTraits yapısı | Microsoft Docs
ms.custom: ''
ms.date: 09/27/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::GetInvalidValue
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::Close method
- Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::GetInvalidValue method
ms.assetid: 88a29a14-c516-40cb-a0ca-ee897a668623
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1060d28e35a52e2a8c5c550664d36d8272628526
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49161742"
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
