---
description: 'Hakkında daha fazla bilgi edinin: affinity_partitioner sınıfı'
title: affinity_partitioner Sınıfı
ms.date: 11/04/2016
f1_keywords:
- affinity_partitioner
- PPL/concurrency::affinity_partitioner
- PPL/concurrency::affinity_partitioner::affinity_partitioner
helpviewer_keywords:
- affinity_partitioner class
ms.assetid: 31bf7bb1-bd01-491c-9760-d9d60edfccad
ms.openlocfilehash: 44aa693d5007507e33f062a673713d1ddbda3172
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172329"
---
# <a name="affinity_partitioner-class"></a>affinity_partitioner Sınıfı

`affinity_partitioner`Sınıfı, `static_partitioner` sınıfa benzerdir, ancak alt aralıkları çalışan iş parçacıklarıyla eşleme seçeneği tarafından önbellek benzeşimini geliştirir. Bir döngü aynı veri kümesi üzerinde yeniden yürütüldüğünde ve veriler önbelleğe sığıyorsa performansı önemli ölçüde iyileştirebilir. Aynı `affinity_partitioner` nesne, veri konumundan faydalanmak için belirli bir veri kümesi üzerinde yürütülen paralel bir döngünün sonraki yinelemeleriyle birlikte kullanılmalıdır.

## <a name="syntax"></a>Syntax

```cpp
class affinity_partitioner;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[affinity_partitioner](#ctor)|Bir `affinity_partitioner` nesnesi oluşturur.|
|[~ affinity_partitioner yok edici](#dtor)|Bir nesneyi yok eder `affinity_partitioner` .|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`affinity_partitioner`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** PPL. h

**Ad alanı:** eşzamanlılık

## <a name="affinity_partitioner"></a><a name="dtor"></a> ~ affinity_partitioner

Bir nesneyi yok eder `affinity_partitioner` .

```cpp
~affinity_partitioner();
```

## <a name="affinity_partitioner"></a><a name="ctor"></a> affinity_partitioner

Bir `affinity_partitioner` nesnesi oluşturur.

```cpp
affinity_partitioner();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
