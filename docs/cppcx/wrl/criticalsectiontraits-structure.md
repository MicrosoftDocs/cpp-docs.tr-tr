---
description: 'Daha fazla bilgi edinin: Kritikbölünitelikleri yapısı'
title: CriticalSectionTraits Yapısı
ms.date: 09/26/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock method
ms.assetid: c515a1b5-4eb0-40bc-9035-c4d9352c9de7
ms.openlocfilehash: 20e4b7dd47acf6f632c888c9bfdedeb3f4e60270
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272948"
---
# <a name="criticalsectiontraits-structure"></a>CriticalSectionTraits Yapısı

Bir nesneyi, `CriticalSection` kritik bir bölümü serbest bırakmak için geçersiz bir kritik bölümü ya da bir işlevi destekleyecek şekilde özelleştirir.

## <a name="syntax"></a>Syntax

```
struct CriticalSectionTraits;
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

Ad   | Açıklama
------ | -----------------------------------------------------------------------------------------------------------------
`Type` | **`typedef`** Kritik bir bölüme yönelik bir işaretçi tanımlayan bir. `Type` olarak tanımlanır `typedef CRITICAL_SECTION* Type;` .

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                                       | Açıklama
---------------------------------------------------------- | -----------------
[Kritikbölünitelikleri:: GetInvalidValue](#getinvalidvalue) | Şablonu `CriticalSection` her zaman geçersiz olacak şekilde özelleştirilmiş bir şablon.
[Kritiksectionnitelikler:: unlock](#unlock)                   | Bir `CriticalSection` şablonu, belirtilen kritik bölüm nesnesinin sahipliğini serbest bırakma desteği sağlayacak şekilde özelleştirilmiş hale getirir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CriticalSectionTraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrapper. h

**Ad alanı:** Microsoft:: WRL:: sarmalayıcılar:: Handlenitelikler

## <a name="criticalsectiontraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a> Kritikbölünitelikleri:: GetInvalidValue

Şablonu `CriticalSection` her zaman geçersiz olacak şekilde özelleştirilmiş bir şablon.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman geçersiz bir kritik bölüme bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

`Type`Değiştirici olarak tanımlanır `typedef CRITICAL_SECTION* Type;` .

## <a name="criticalsectiontraitsunlock"></a><a name="unlock"></a> Kritiksectionnitelikler:: unlock

Bir `CriticalSection` şablonu, belirtilen kritik bölüm nesnesinin sahipliğini serbest bırakma desteği sağlayacak şekilde özelleştirilmiş hale getirir.

```cpp
inline static void Unlock(
   _In_ Type cs
);
```

### <a name="parameters"></a>Parametreler

*'ye*<br/>
Kritik bölüm nesnesi işaretçisi.

### <a name="remarks"></a>Açıklamalar

`Type`Değiştirici olarak tanımlanır `typedef CRITICAL_SECTION* Type;` .

Daha fazla bilgi için Windows API belgelerinin **eşitleme işlevleri** bölümünde **LeaveCriticalSection işlevi** bölümüne bakın.
