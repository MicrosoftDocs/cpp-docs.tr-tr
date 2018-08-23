---
title: SyncLockWithStatusT sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockWithStatusT class
ms.assetid: 4832fd93-0ac8-4168-9404-b43fefea7476
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a0c53832acdd7a785ccc36941cd317a9d0705173
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42583632"
---
# <a name="synclockwithstatust-class"></a>SyncLockWithStatusT Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
   typename SyncTraits
>
class SyncLockWithStatusT : public SyncLockT<SyncTraits>;
```

### <a name="parameters"></a>Parametreler

*SyncTraits*  
Özel alan bir türü veya bir kaynağa ilişkin paylaşılan sahipliğiniz.

## <a name="remarks"></a>Açıklamalar

Özel alan türünü temsil eder ya da bir kaynak ilişkin paylaşılan sahipliğiniz.

**SyncLockWithStatusT** sınıfı uygulamak için kullanılan [Mutex](../windows/mutex-class1.md) ve [semafor](../windows/semaphore-class.md) sınıfları.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[SyncLockWithStatusT::SyncLockWithStatusT Oluşturucusu](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|Yeni bir örneğini başlatır **SyncLockWithStatusT** sınıfı.|

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[SyncLockWithStatusT::SyncLockWithStatusT Oluşturucusu](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|Yeni bir örneğini başlatır **SyncLockWithStatusT** sınıfı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[SyncLockWithStatusT::GetStatus Metodu](../windows/synclockwithstatust-getstatus-method.md)|Geçerli bekleme durumunu alır **SyncLockWithStatusT** nesne.|
|[SyncLockWithStatusT::IsLocked Metodu](../windows/synclockwithstatust-islocked-method.md)|Belirtir olup olmadığını geçerli **SyncLockWithStatusT** nesnesi bir kaynağa sahiptir; diğer bir deyişle, **SyncLockWithStatusT** nesnedir *kilitli*.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[SyncLockWithStatusT::status_ Veri Üyesi](../windows/synclockwithstatust-status-data-member.md)|Geçerli bir nesne üzerinde bir kilit işlemi temel sonra alttaki bekleme işleminin sonucu tutan **SyncLockWithStatusT** nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SyncLockT`

`SyncLockWithStatusT`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Wrappers::Details Ad Alanı](../windows/microsoft-wrl-wrappers-details-namespace.md)