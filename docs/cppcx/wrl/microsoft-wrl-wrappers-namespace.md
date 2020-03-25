---
title: Microsoft::WRL::Wrappers Ad Alanı
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers
helpviewer_keywords:
- Wrappers namespace
ms.assetid: 36ac38c7-1fc3-42da-a879-5c68661dc9e1
ms.openlocfilehash: ece26b3f9928d44a593de830cf8a25c57e4c2d89
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213752"
---
# <a name="microsoftwrlwrappers-namespace"></a>Microsoft::WRL::Wrappers Ad Alanı

Nesnelerin, dizelerin ve tanıtıcıların ömür yönetimini kolaylaştıran kaynak alımı başlatma (SII) sarmalayıcı türlerini tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
namespace Microsoft::WRL::Wrappers;
```

## <a name="members"></a>Üyeler

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`FileHandle`|`HandleT<HandleTraits::FileHandleTraits>`|

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[CriticalSection Sınıfı](criticalsection-class.md)|Kritik bir bölüm nesnesini temsil eder.|
|[Event Sınıfı (WRL)](event-class-wrl.md)|Bir olayı temsil eder.|
|[HandleT Sınıfı](handlet-class.md)|Bir nesneye olan tanıtıcıyı temsil eder.|
|[HString Sınıfı](hstring-class.md)|HSTRıNG tutamaçlarını işlemek için destek sağlar.|
|[HStringReference Sınıfı](hstringreference-class.md)|Varolan bir dizeden oluşturulan bir HSTRıNG temsil eder.|
|[Mutex sınıfı](mutex-class.md)|Paylaşılan bir kaynağı özel olarak denetleyen bir eşitleme nesnesini temsil eder.|
|[RoInitializeWrapper Sınıfı](roinitializewrapper-class.md)|Windows Çalışma Zamanı başlatır.|
|[Semafor Sınıfı](semaphore-class.md)|Sınırlı sayıda kullanıcıyı destekleyebilen, paylaşılan bir kaynağı denetleyen bir eşitleme nesnesini temsil eder.|
|[SRWLock Sınıfı](srwlock-class.md)|İnce bir okuyucu/yazıcı kilidini temsil eder.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrapper. h

**Ad alanı:** Microsoft:: WRL:: sarmalayıcılar

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)
