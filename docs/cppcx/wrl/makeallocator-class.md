---
description: 'Daha fazla bilgi edinin: Makeayırıcı sınıfı'
title: MakeAllocator Sınıfı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator
- implements/Microsoft::WRL::Details::MakeAllocator::Allocate
- implements/Microsoft::WRL::Details::MakeAllocator::Detach
- implements/Microsoft::WRL::Details::MakeAllocator::MakeAllocator
- implements/Microsoft::WRL::Details::MakeAllocator::~MakeAllocator
helpviewer_keywords:
- Microsoft::WRL::Details::MakeAllocator class
- Microsoft::WRL::Details::MakeAllocator::Allocate method
- Microsoft::WRL::Details::MakeAllocator::Detach method
- Microsoft::WRL::Details::MakeAllocator::MakeAllocator, constructor
- Microsoft::WRL::Details::MakeAllocator::~MakeAllocator, destructor
ms.assetid: a1114615-abd7-4a56-9bc3-750c118f0fa1
ms.openlocfilehash: c4e550dec37096a5ff6a41eccd4eb41968721a7d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344529"
---
# <a name="makeallocator-class"></a>MakeAllocator Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<
    typename T,
    bool hasWeakReferenceSupport =
          !__is_base_of(RuntimeClassFlags<InhibitWeakReference>,
                        T)
>
class MakeAllocator;

template<typename T>
class MakeAllocator<T, false>;

template<typename T>
class MakeAllocator<T, true>;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Bir tür adı.

*hasWeakReferenceSupport*<br/>
**`true`** zayıf başvuruları destekleyen bir nesne için bellek ayırmak üzere; **`false`** zayıf başvuruları desteklemeyen bir nesne için bellek ayırmak için.

## <a name="remarks"></a>Açıklamalar

Zayıf başvuru desteği olan veya olmayan bir etkinleştirilebilir sınıfı için bellek ayırır.

`MakeAllocator`Kullanıcı tanımlı bir bellek ayırma modeli uygulamak için sınıfını geçersiz kılın.

`MakeAllocator` Genellikle, oluşturma sırasında bir nesne oluşturduğunda bellek sızıntılarını engellemek için kullanılır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                                  | Açıklama
----------------------------------------------------- | ----------------------------------------------------------------
[Makeayırıcı:: Makeayırıcı](#makeallocator)        | `MakeAllocator` sınıfının yeni bir örneğini başlatır.
[Makeayırıcı:: ~ Makeayırıcı](#tilde-makeallocator) | Sınıfın geçerli örneğini kaldırır `MakeAllocator` .

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                 | Açıklama
------------------------------------ | -----------------------------------------------------------------------------------------------------------
[Makeayırıcı:: allocate](#allocate) | Belleği ayırır ve geçerli `MakeAllocator` nesneyle ilişkilendirir.
[Makeayırıcı::D etach](#detach)     | Geçerli nesneden [ayırma](#allocate) yöntemiyle ayrılan belleği ilişkilendirir `MakeAllocator` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`MakeAllocator`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** uygular. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="makeallocatorallocate"></a><a name="allocate"></a> Makeayırıcı:: allocate

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
__forceinline void* Allocate();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ayrılan belleğe yönelik bir işaretçi; Aksi takdirde, **`nullptr`** .

### <a name="remarks"></a>Açıklamalar

Belleği ayırır ve geçerli `MakeAllocator` nesneyle ilişkilendirir.

Ayrılan belleğin boyutu, geçerli şablon parametresi tarafından belirtilen türün boyutudur `MakeAllocator` .

Bir geliştiricinin yalnızca `Allocate()` farklı bir bellek ayırma modeli uygulamak için yöntemini geçersiz kılması gerekir.

## <a name="makeallocatordetach"></a><a name="detach"></a> Makeayırıcı::D etach

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
__forceinline void Detach();
```

### <a name="remarks"></a>Açıklamalar

Geçerli nesneden [ayırma](#allocate) yöntemiyle ayrılan belleği ilişkilendirir `MakeAllocator` .

`Detach()`' İ çağırdığınızda, yöntemi tarafından belirtilen belleği silmekten siz sorumlusunuz `Allocate` .

## <a name="makeallocatormakeallocator"></a><a name="makeallocator"></a> Makeayırıcı:: Makeayırıcı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
MakeAllocator();
```

### <a name="remarks"></a>Açıklamalar

`MakeAllocator` sınıfının yeni bir örneğini başlatır.

## <a name="makeallocatormakeallocator"></a><a name="tilde-makeallocator"></a> Makeayırıcı:: ~ Makeayırıcı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
~MakeAllocator();
```

### <a name="remarks"></a>Açıklamalar

Sınıfın geçerli örneğini kaldırır `MakeAllocator` .

Bu yıkıcı Ayrıca, gerekirse temeldeki ayrılmış belleği da siler.
