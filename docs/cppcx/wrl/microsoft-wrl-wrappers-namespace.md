---
description: 'Hakkında daha fazla bilgi edinin: Microsoft:: WRL:: sarmalayıcılar ad alanı'
title: Microsoft::WRL::Wrappers Ad Alanı
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers
helpviewer_keywords:
- Wrappers namespace
ms.assetid: 36ac38c7-1fc3-42da-a879-5c68661dc9e1
ms.openlocfilehash: 603fa14b0e43f481b1afe56d98e355d328f284fe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209405"
---
# <a name="microsoftwrlwrappers-namespace"></a>Microsoft::WRL::Wrappers Ad Alanı

Nesnelerin, dizelerin ve tanıtıcıların ömür yönetimini kolaylaştıran kaynak alımı başlatma (SII) sarmalayıcı türlerini tanımlar.

## <a name="syntax"></a>Syntax

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
|[Kritiksection sınıfı](criticalsection-class.md)|Kritik bir bölüm nesnesini temsil eder.|
|[Event sınıfı (WRL)](event-class-wrl.md)|Bir olayı temsil eder.|
|[HandleT Sınıfı](handlet-class.md)|Bir nesneye olan tanıtıcıyı temsil eder.|
|[HString sınıfı](hstring-class.md)|HSTRıNG tutamaçlarını işlemek için destek sağlar.|
|[HStringReference sınıfı](hstringreference-class.md)|Varolan bir dizeden oluşturulan bir HSTRıNG temsil eder.|
|[Mutex sınıfı](mutex-class.md)|Paylaşılan bir kaynağı özel olarak denetleyen bir eşitleme nesnesini temsil eder.|
|[RoInitializeWrapper sınıfı](roinitializewrapper-class.md)|Windows Çalışma Zamanı başlatır.|
|[Semafor sınıfı](semaphore-class.md)|Sınırlı sayıda kullanıcıyı destekleyebilen, paylaşılan bir kaynağı denetleyen bir eşitleme nesnesini temsil eder.|
|[SRWLock sınıfı](srwlock-class.md)|İnce bir okuyucu/yazıcı kilidini temsil eder.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrapper. h

**Ad alanı:** Microsoft:: WRL:: sarmalayıcılar

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL ad alanı](microsoft-wrl-namespace.md)
