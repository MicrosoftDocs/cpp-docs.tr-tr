---
title: Mutex ssınıfı1 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex
dev_langs:
- C++
helpviewer_keywords:
- Mutex class
ms.assetid: 682a0963-721c-46a2-8871-000e9997505b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b20c270f7848a346d717357f474d89e37ea117a4
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600034"
---
# <a name="mutex-class1"></a>Mutex ssınıfı1

Paylaşılan bir kaynağa özel olarak denetleyen bir eşitleme nesnesi temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class Mutex : public HandleT<HandleTraits::MutexTraits>
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`SyncLock`|Zaman uyumlu kilitleri destekleyen bir sınıf için bir eşanlamlı.|

### <a name="public-constructor"></a>Genel oluşturucu

|Ad|Açıklama|
|----------|-----------------|
|[Mutex::Mutex Oluşturucusu](../windows/mutex-mutex-constructor.md)|Yeni bir örneğini başlatır **Mutex** sınıfı.|

### <a name="public-members"></a>Ortak üyeler

|Ad|Açıklama|
|----------|-----------------|
|[Mutex::Lock Metodu](../windows/mutex-lock-method.md)|Geçerli nesne kadar bekler veya **Mutex** belirtilen tanıtıcısı, mutex veya belirtilen zaman aşımı aralığı geçtikten yayınlar ilişkili nesne.|

### <a name="public-operator"></a>Genel işleç

|Ad|Açıklama|
|----------|-----------------|
|[Mutex::operator= İşleci](../windows/mutex-operator-assign-operator.md)|Atar (taşıma) belirtilen **Mutex** geçerli nesneye **Mutex** nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Mutex`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Wrappers Ad Alanı](../windows/microsoft-wrl-wrappers-namespace.md)