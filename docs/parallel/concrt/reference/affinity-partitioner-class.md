---
title: affinity_partitioner Sınıfı
ms.date: 11/04/2016
f1_keywords:
- affinity_partitioner
- PPL/concurrency::affinity_partitioner
- PPL/concurrency::affinity_partitioner::affinity_partitioner
helpviewer_keywords:
- affinity_partitioner class
ms.assetid: 31bf7bb1-bd01-491c-9760-d9d60edfccad
ms.openlocfilehash: 0ae6bbee49d1b8873190a7054e55f65b40b31b13
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142882"
---
# <a name="affinity_partitioner-class"></a>affinity_partitioner Sınıfı

`affinity_partitioner` sınıfı `static_partitioner` sınıfına benzerdir, ancak alt aralıkları çalışan iş parçacıklarıyla eşleme seçeneği tarafından önbellek benzeşimini geliştirir. Bir döngü aynı veri kümesi üzerinde yeniden yürütüldüğünde ve veriler önbelleğe sığıyorsa performansı önemli ölçüde iyileştirebilir. Aynı `affinity_partitioner` nesnesinin, veri konumundan faydalanmak için belirli bir veri kümesi üzerinde yürütülen paralel bir döngünün sonraki yinelemeleriyle birlikte kullanılması gerektiğini unutmayın.

## <a name="syntax"></a>Sözdizimi

```cpp
class affinity_partitioner;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[affinity_partitioner](#ctor)|`affinity_partitioner` nesnesi oluşturur.|
|[~ affinity_partitioner yok edici](#dtor)|`affinity_partitioner` nesnesini yok eder.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`affinity_partitioner`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** PPL. h

**Ad alanı:** eşzamanlılık

## <a name="dtor"></a>~ affinity_partitioner

`affinity_partitioner` nesnesini yok eder.

```cpp
~affinity_partitioner();
```

## <a name="ctor"></a>affinity_partitioner

`affinity_partitioner` nesnesi oluşturur.

```cpp
affinity_partitioner();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
