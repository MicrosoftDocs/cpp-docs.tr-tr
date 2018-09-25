---
title: MakeAllocator sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 09/21/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator
- implements/Microsoft::WRL::Details::MakeAllocator::Allocate
- implements/Microsoft::WRL::Details::MakeAllocator::Detach
- implements/Microsoft::WRL::Details::MakeAllocator::MakeAllocator
- implements/Microsoft::WRL::Details::MakeAllocator::~MakeAllocator
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::MakeAllocator class
- Microsoft::WRL::Details::MakeAllocator::Allocate method
- Microsoft::WRL::Details::MakeAllocator::Detach method
- Microsoft::WRL::Details::MakeAllocator::MakeAllocator, constructor
- Microsoft::WRL::Details::MakeAllocator::~MakeAllocator, destructor
ms.assetid: a1114615-abd7-4a56-9bc3-750c118f0fa1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6cb6574172747712fa2670b4444b17bec047a8cf
ms.sourcegitcommit: edb46b0239a0e616af4ec58906e12338c3e8d2c6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2018
ms.locfileid: "47169742"
---
# <a name="makeallocator-class"></a>MakeAllocator Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<
   typename T,
   bool hasWeakReferenceSupport =
         !__is_base_of(RuntimeClassFlags<InhibitWeakReference>, T)>
class MakeAllocator;

template<typename T>
class MakeAllocator<T, false>;

template<typename T>
class MakeAllocator<T, true>;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Tür adı.

*hasWeakReferenceSupport*<br/>
`true` zayıf başvurular destekleyen bir nesne için bellek ayırmak için; `false` zayıf başvuru desteği olmayan bir nesne için bellek ayrılamadı.

## <a name="remarks"></a>Açıklamalar

İle veya zayıf başvuru desteği olmayan bir etkinleştirilebilir sınıf için bellek ayırır.

Geçersiz kılma `MakeAllocator` bir kullanıcı tarafından tanımlanan bellek ayırma modeli uygulamak için sınıfı.

`MakeAllocator` genellikle bir nesne oluşturma sırasında oluşturursa bellek sızıntılarını önlemek için kullanılır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                                                  | Açıklama
----------------------------------------------------- | ----------------------------------------------------------------
[MakeAllocator::MakeAllocator](#makeallocator)        | Yeni bir örneğini başlatır `MakeAllocator` sınıfı.
[MakeAllocator:: ~ MakeAllocator](#tilde-makeallocator) | Geçerli örneğinin başlatmasını geri alır `MakeAllocator` sınıfı.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                 | Açıklama
------------------------------------ | -----------------------------------------------------------------------------------------------------------
[MakeAllocator::Allocate](#allocate) | Bellek ayırır ve geçerli ilişkilendirir `MakeAllocator` nesne.
[MakeAllocator::Detach](#detach)     | Tarafından ayrılan bellek ayırır [ayırma](#allocate) yöntemi geçerli `MakeAllocator` nesne.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`MakeAllocator`

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="allocate"></a>MakeAllocator::Allocate

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
__forceinline void* Allocate();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, ayrılan bellek; işaretçisi Aksi takdirde, `nullptr`.

### <a name="remarks"></a>Açıklamalar

Bellek ayırır ve geçerli ilişkilendirir `MakeAllocator` nesne.

Ayrılan bellek boyutu geçerli belirtilen tür boyutudur `MakeAllocator` şablon parametresi.

Yalnızca geçersiz kılmak bir geliştiricinin ihtiyaç duyduğu `Allocate()` farklı bellek ayırma modeli uygulamak için yöntemi.

## <a name="detach"></a>MakeAllocator::Detach

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
__forceinline void Detach();
```

### <a name="remarks"></a>Açıklamalar

Tarafından ayrılan bellek ayırır [ayırma](#allocate) yöntemi geçerli `MakeAllocator` nesne.

Eğer `Detach()`, tarafından sağlanan belleği silmekten sorumlu `Allocate` yöntemi.

## <a name="makeallocator"></a>MakeAllocator::MakeAllocator

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
MakeAllocator();
```

### <a name="remarks"></a>Açıklamalar

Yeni bir örneğini başlatır `MakeAllocator` sınıfı.

## <a name="tilde-makeallocator"></a>MakeAllocator:: ~ MakeAllocator

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

```cpp
~MakeAllocator();
```

### <a name="remarks"></a>Açıklamalar

Geçerli örneğinin başlatmasını geri alır `MakeAllocator` sınıfı.

Bu yok edici temel alınan ayrılmış bellek gerekirse da siler.
