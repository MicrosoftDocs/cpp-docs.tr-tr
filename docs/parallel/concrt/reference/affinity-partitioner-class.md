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
ms.openlocfilehash: dac25755c388e5297ce671da09b7938f09f1ef03
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62337667"
---
# <a name="affinitypartitioner-class"></a>affinity_partitioner Sınıfı

`affinity_partitioner` Sınıfı benzer `static_partitioner` sınıfı, ancak alt aralıklara çalışan iş parçacıkları için eşleme dilediği tarafından önbellek benzeşim artırır. Bir döngü, aynı veri kümesi üzerinde yeniden çalıştırılır ve veri önbellekte en uygun, performansı önemli ölçüde artırabilir. Unutmayın aynı `affinity_partitioner` nesnesi, bir özel veri yerel veri konumu yararlanmak için küme üzerinde çalıştırılan paralel bir döngüden sonraki yinelemeleri ile kullanılmalıdır.

## <a name="syntax"></a>Sözdizimi

```
class affinity_partitioner;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[affinity_partitioner](#ctor)|Oluşturur bir `affinity_partitioner` nesne.|
|[~ affinity_partitioner yok Edicisi](#dtor)|Yok eder bir `affinity_partitioner` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`affinity_partitioner`

## <a name="requirements"></a>Gereksinimler

**Başlık:** ppl.h

**Namespace:** eşzamanlılık

##  <a name="dtor"></a> ~ affinity_partitioner

Yok eder bir `affinity_partitioner` nesne.

```
~affinity_partitioner();
```

##  <a name="ctor"></a> affinity_partitioner

Oluşturur bir `affinity_partitioner` nesne.

```
affinity_partitioner();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
