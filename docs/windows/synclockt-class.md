---
title: SyncLockT sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT
dev_langs:
- C++
helpviewer_keywords:
- SyncLockT class
ms.assetid: a967f6f7-3555-43d1-b210-2bb65d63d15e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e8589c43d49709842a745464d2727860ccd2c1e2
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609683"
---
# <a name="synclockt-class"></a>SyncLockT Sınıfı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
   typename SyncTraits
>
class SyncLockT;
```

### <a name="parameters"></a>Parametreler

*SyncTraits*  
Bir kaynağın sahipliğini türü.

## <a name="remarks"></a>Açıklamalar

Özel alan türünü temsil eder ya da bir kaynak ilişkin paylaşılan sahipliğiniz.

**SyncLockT** sınıfı kullanılır, örneğin, uygulamak için [SRWLock](../windows/srwlock-class.md) sınıfı.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[SyncLockT::SyncLockT Oluşturucusu](../windows/synclockt-synclockt-constructor.md)|Yeni bir örneğini başlatır **SyncLockT** sınıfı.|
|[SyncLockT::~SyncLockT Yıkıcısı](../windows/synclockt-tilde-synclockt-destructor.md)|Örneği başlatılmasını geri alır **SyncLockT** sınıfı.|

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[SyncLockT::SyncLockT Oluşturucusu](../windows/synclockt-synclockt-constructor.md)|Yeni bir örneğini başlatır **SyncLockT** sınıfı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[SyncLockT::IsLocked Metodu](../windows/synclockt-islocked-method.md)|Belirtir olup olmadığını geçerli **SyncLockT** nesnesi bir kaynağa sahiptir; diğer bir deyişle, **SyncLockT** nesnedir *kilitli*.|
|[SyncLockT::Unlock Metodu](../windows/synclockt-unlock-method.md)|Serbest geçerli tarafından tutulan kaynak denetimi **SyncLockT** varsa, nesne.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[SyncLockT::sync_ Veri Üyesi](../windows/synclockt-sync-data-member.md)|Temel alınan kaynak tarafından temsil edilen tutar **SyncLockT** sınıfı.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SyncLockT`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Wrappers::Details Ad Alanı](../windows/microsoft-wrl-wrappers-details-namespace.md)  
[SRWLock Sınıfı](../windows/srwlock-class.md)