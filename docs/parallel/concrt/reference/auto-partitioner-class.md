---
description: 'Hakkında daha fazla bilgi edinin: auto_partitioner Sınıfı'
title: auto_partitioner Sınıfı
ms.date: 11/04/2016
f1_keywords:
- auto_partitioner
- PPL/concurrency::auto_partitioner
- PPL/concurrency::auto_partitioner::auto_partitioner
helpviewer_keywords:
- auto_partitioner class
ms.assetid: 7cc08e5d-20b4-47a4-b4b5-c214a78f5a9e
ms.openlocfilehash: d8e099c7a3132ce89f81df65d7e18a5c6c673697
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172264"
---
# <a name="auto_partitioner-class"></a>auto_partitioner Sınıfı

`auto_partitioner`Sınıfı varsayılan yöntemi temsil eder `parallel_for` `parallel_for_each` ve `parallel_transform` üzerinde yineleme aralığını bölümlemek için kullanın. Bu bölümleme yöntemi, yük dengeleme için Aralık çalmasını ve yineleme başına iptali kullanır.

## <a name="syntax"></a>Syntax

```cpp
class auto_partitioner;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[auto_partitioner](#ctor)|Bir `auto_partitioner` nesnesi oluşturur.|
|[~ auto_partitioner yok edici](#dtor)|Bir nesneyi yok eder `auto_partitioner` .|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`auto_partitioner`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** PPL. h

**Ad alanı:** eşzamanlılık

## <a name="auto_partitioner"></a><a name="dtor"></a> ~ auto_partitioner

Bir nesneyi yok eder `auto_partitioner` .

```cpp
~auto_partitioner();
```

## <a name="auto_partitioner"></a><a name="ctor"></a> auto_partitioner

Bir `auto_partitioner` nesnesi oluşturur.

```cpp
auto_partitioner();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
