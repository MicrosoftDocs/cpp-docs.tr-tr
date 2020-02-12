---
title: static_partitioner Sınıfı
ms.date: 11/04/2016
f1_keywords:
- static_partitioner
- PPL/concurrency::static_partitioner
- PPL/concurrency::static_partitioner::static_partitioner
helpviewer_keywords:
- static_partitioner class
ms.assetid: 2b3dbdf0-6eb9-49f6-8639-03df1d974143
ms.openlocfilehash: 7a58daa27bc7a2f51f78a3068a2f152979ffdd72
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142687"
---
# <a name="static_partitioner-class"></a>static_partitioner Sınıfı

`static_partitioner` sınıfı, `parallel_for`tarafından yineleyen aralığın statik bir bölümlemesini temsil eder. Bölümleyici, temel alınan Scheduler 'da bulunan çalışanlar olduğundan, aralığı çok sayıda parçalara ayırır.

## <a name="syntax"></a>Sözdizimi

```cpp
class static_partitioner;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[static_partitioner](#ctor)|`static_partitioner` nesnesi oluşturur.|
|[~ static_partitioner yok edici](#dtor)|`static_partitioner` nesnesini yok eder.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`static_partitioner`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** PPL. h

**Ad alanı:** eşzamanlılık

## <a name="dtor"></a>~ static_partitioner

`static_partitioner` nesnesini yok eder.

```cpp
~static_partitioner();
```

## <a name="ctor"></a>static_partitioner

`static_partitioner` nesnesi oluşturur.

```cpp
static_partitioner();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
