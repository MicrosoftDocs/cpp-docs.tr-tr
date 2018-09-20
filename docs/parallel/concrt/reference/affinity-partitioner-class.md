---
title: affinity_partitioner sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- affinity_partitioner
- PPL/concurrency::affinity_partitioner
- PPL/concurrency::affinity_partitioner::affinity_partitioner
dev_langs:
- C++
helpviewer_keywords:
- affinity_partitioner class
ms.assetid: 31bf7bb1-bd01-491c-9760-d9d60edfccad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9b1254b316a52bd3e61b3cafd81ba2e89ee88b62
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444651"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
