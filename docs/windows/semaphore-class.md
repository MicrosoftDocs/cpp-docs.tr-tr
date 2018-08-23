---
title: Semafor sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore
dev_langs:
- C++
helpviewer_keywords:
- Semaphore class
ms.assetid: ded53526-17b4-4381-9c60-ea5e77363db6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bb0b3d5dff91bcb1fb1688c7b1a9314fe7ebf00c
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598421"
---
# <a name="semaphore-class"></a>Semafor Sınıfı

Sınırlı sayıda kullanıcıları destekleyen bir paylaşılan kaynak denetleyen bir eşitleme nesnesi temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class Semaphore : public HandleT<HandleTraits::SemaphoreTraits>
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`SyncLock`|Zaman uyumlu kilitleri destekleyen bir sınıf için bir eşanlamlı.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Semaphore::Semaphore Oluşturucusu](../windows/semaphore-semaphore-constructor.md)|Yeni bir örneğini başlatır **semafor** sınıfı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[InvokeHelper::Invoke Metodu](../windows/invokehelper-invoke-method.md)|İmzası olan, belirtilen sayıda bağımsız değişken içeren olay işleyicisini çağırır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Semaphore::Lock Metodu](../windows/semaphore-lock-method.md)|Geçerli nesne ya da belirtilen işleyici ile ilişkili nesne kadar bekler sinyal verilmiş duruma dönmesine ya da belirtilen zaman aşımı aralığı geçti.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[Semaphore::operator= İşleci](../windows/semaphore-operator-assign-operator.md)|Belirtilen tanıtıcıdan taşır bir **semafor** geçerli nesneye **semafor** nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Semaphore`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Wrappers Ad Alanı](../windows/microsoft-wrl-wrappers-namespace.md)