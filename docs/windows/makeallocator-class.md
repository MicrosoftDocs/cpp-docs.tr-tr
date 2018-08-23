---
title: MakeAllocator sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator
dev_langs:
- C++
helpviewer_keywords:
- MakeAllocator class
ms.assetid: a1114615-abd7-4a56-9bc3-750c118f0fa1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e27be8eaddfc22474f15d7f9358050273252bf8a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610330"
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

*T*  
Tür adı.

*hasWeakReferenceSupport*  
**doğru** zayıf başvurular; destekleyen bir nesne için bellek ayrılamadı **false** zayıf başvuru desteği olmayan bir nesne için bellek ayrılamadı.

## <a name="remarks"></a>Açıklamalar

İle veya zayıf başvuru desteği olmayan bir etkinleştirilebilir sınıf için bellek ayırır.

Geçersiz kılma **MakeAllocator** bir kullanıcı tarafından tanımlanan bellek ayırma modeli uygulamak için sınıfı.

**MakeAllocator** genellikle bir nesne oluşturma sırasında oluşturursa bellek sızıntılarını önlemek için kullanılır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[MakeAllocator::MakeAllocator Oluşturucusu](../windows/makeallocator-makeallocator-constructor.md)|Yeni bir örneğini başlatır **MakeAllocator** sınıfı.|
|[MakeAllocator::~MakeAllocator Yıkıcısı](../windows/makeallocator-tilde-makeallocator-destructor.md)|Geçerli örneğinin başlatmasını geri alır **MakeAllocator** sınıfı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[MakeAllocator::Allocate Metodu](../windows/makeallocator-allocate-method.md)|Bellek ayırır ve geçerli ilişkilendirir **MakeAllocator** nesne.|
|[MakeAllocator::Detach Metodu](../windows/makeallocator-detach-method.md)|Tarafından ayrılan bellek ayırır [ayırma](../windows/makeallocator-allocate-method.md) yöntemi geçerli **MakeAllocator** nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`MakeAllocator`

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)