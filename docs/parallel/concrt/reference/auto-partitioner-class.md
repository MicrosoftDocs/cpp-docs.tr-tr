---
title: auto_partitioner Sınıfı
ms.date: 11/04/2016
f1_keywords:
- auto_partitioner
- PPL/concurrency::auto_partitioner
- PPL/concurrency::auto_partitioner::auto_partitioner
helpviewer_keywords:
- auto_partitioner class
ms.assetid: 7cc08e5d-20b4-47a4-b4b5-c214a78f5a9e
ms.openlocfilehash: 4d1d8f19069412240de8e9d69cdcfb34618f2796
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142861"
---
# <a name="auto_partitioner-class"></a>auto_partitioner Sınıfı

`auto_partitioner` sınıfı varsayılan yöntemi temsil eder `parallel_for`, `parallel_for_each` ve `parallel_transform` üzerinde yineleme aralığını bölümlemek için kullanılır. Bu bölümleme yöntemi, yük dengeleme için Aralık çalmasını ve yineleme başına iptali kullanır.

## <a name="syntax"></a>Sözdizimi

```cpp
class auto_partitioner;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[auto_partitioner](#ctor)|`auto_partitioner` nesnesi oluşturur.|
|[~ auto_partitioner yok edici](#dtor)|`auto_partitioner` nesnesini yok eder.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`auto_partitioner`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** PPL. h

**Ad alanı:** eşzamanlılık

## <a name="dtor"></a>~ auto_partitioner

`auto_partitioner` nesnesini yok eder.

```cpp
~auto_partitioner();
```

## <a name="ctor"></a>auto_partitioner

`auto_partitioner` nesnesi oluşturur.

```cpp
auto_partitioner();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
