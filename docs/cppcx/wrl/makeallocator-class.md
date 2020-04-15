---
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
ms.openlocfilehash: dc0d83f2550646572a4eff2bec7850037c6dbf6a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371330"
---
# <a name="makeallocator-class"></a>MakeAllocator Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

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
zayıf başvuruları destekleyen bir nesne için bellek ayırmak için **doğru;** zayıf başvuruları desteklemeyen bir nesne için bellek ayırmak için **yanlış.**

## <a name="remarks"></a>Açıklamalar

Zayıf başvuru desteği olan veya olmayan bir eyleme geçilebilir sınıf için bellek ayırır.

Kullanıcı tanımlı bellek ayırma modeli uygulamak için `MakeAllocator` sınıfı geçersiz kılın.

`MakeAllocator`genellikle bir nesne inşaat sırasında atar bellek sızıntıları önlemek için kullanılır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Adı                                                  | Açıklama
----------------------------------------------------- | ----------------------------------------------------------------
[MakeAllocator::MakeAllocator](#makeallocator)        | `MakeAllocator` sınıfının yeni bir örneğini başlatır.
[MakeAllocator::~MakeAllocator](#tilde-makeallocator) | Sınıfın geçerli örneğini `MakeAllocator` deinitialize eder.

### <a name="public-methods"></a>Ortak Yöntemler

Adı                                 | Açıklama
------------------------------------ | -----------------------------------------------------------------------------------------------------------
[MakeAllocator::Ayırma](#allocate) | Belleği ayırır ve geçerli `MakeAllocator` nesneyle ilişkilendirer.
[MakeAllocator::Detach](#detach)     | Geçerli `MakeAllocator` nesneden [Ayırma](#allocate) yöntemi tarafından ayrılan belleği ayırın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`MakeAllocator`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** implements.h

**Ad alanı:** Microsoft::WRL::D etails

## <a name="makeallocatorallocate"></a><a name="allocate"></a>MakeAllocator::Ayırma

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
__forceinline void* Allocate();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ayrılan belleğe işaretçi; aksi `nullptr`takdirde, .

### <a name="remarks"></a>Açıklamalar

Belleği ayırır ve geçerli `MakeAllocator` nesneyle ilişkilendirer.

Ayrılan belleğin boyutu, geçerli `MakeAllocator` şablon parametresi tarafından belirtilen türboyutudur.

Bir geliştiricinin farklı bir `Allocate()` bellek ayırma modeli uygulamak için yalnızca yöntemi geçersiz kılması gerekir.

## <a name="makeallocatordetach"></a><a name="detach"></a>MakeAllocator::Detach

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
__forceinline void Detach();
```

### <a name="remarks"></a>Açıklamalar

Geçerli `MakeAllocator` nesneden [Ayırma](#allocate) yöntemi tarafından ayrılan belleği ayırın.

Ararsanız, `Detach()` `Allocate` yöntem tarafından sağlanan belleği silmekten siz sorumlusunuz.

## <a name="makeallocatormakeallocator"></a><a name="makeallocator"></a>MakeAllocator::MakeAllocator

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
MakeAllocator();
```

### <a name="remarks"></a>Açıklamalar

`MakeAllocator` sınıfının yeni bir örneğini başlatır.

## <a name="makeallocatormakeallocator"></a><a name="tilde-makeallocator"></a>MakeAllocator::~MakeAllocator

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılması amaçlanmamıştır.

```cpp
~MakeAllocator();
```

### <a name="remarks"></a>Açıklamalar

Sınıfın geçerli örneğini `MakeAllocator` deinitialize eder.

Bu yıkıcı, gerekirse temel ayrılan belleği de siler.
