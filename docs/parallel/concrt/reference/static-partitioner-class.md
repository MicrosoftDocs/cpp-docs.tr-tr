---
description: 'Hakkında daha fazla bilgi edinin: static_partitioner sınıfı'
title: static_partitioner Sınıfı
ms.date: 11/04/2016
f1_keywords:
- static_partitioner
- PPL/concurrency::static_partitioner
- PPL/concurrency::static_partitioner::static_partitioner
helpviewer_keywords:
- static_partitioner class
ms.assetid: 2b3dbdf0-6eb9-49f6-8639-03df1d974143
ms.openlocfilehash: f75d2e620a66e0ed347d39d429f59e3e2715369a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188501"
---
# <a name="static_partitioner-class"></a>static_partitioner Sınıfı

`static_partitioner`Sınıfı, tarafından tarafından yineleyen aralığın statik bir bölümlemesini temsil eder `parallel_for` . Bölümleyici, temel alınan Scheduler 'da bulunan çalışanlar olduğundan, aralığı çok sayıda parçalara ayırır.

## <a name="syntax"></a>Syntax

```cpp
class static_partitioner;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[static_partitioner](#ctor)|Bir `static_partitioner` nesnesi oluşturur.|
|[~ static_partitioner yok edici](#dtor)|Bir nesneyi yok eder `static_partitioner` .|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`static_partitioner`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** PPL. h

**Ad alanı:** eşzamanlılık

## <a name="static_partitioner"></a><a name="dtor"></a> ~ static_partitioner

Bir nesneyi yok eder `static_partitioner` .

```cpp
~static_partitioner();
```

## <a name="static_partitioner"></a><a name="ctor"></a> static_partitioner

Bir `static_partitioner` nesnesi oluşturur.

```cpp
static_partitioner();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
