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
ms.openlocfilehash: 5120e3c53dc00ba9d5c3a4218efe1dcfb8f92e28
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57287654"
---
# <a name="staticpartitioner-class"></a>static_partitioner Sınıfı

`static_partitioner` Sınıfı temsil eder bir statik tarafından üzerinden yinelenir aralık bölümleme `parallel_for`. Bölümleyici aralığı çalışanları underyling Zamanlayıcı kullanılabilir olduğu kadar çok öbeklere böler.

## <a name="syntax"></a>Sözdizimi

```
class static_partitioner;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[static_partitioner](#ctor)|Oluşturur bir `static_partitioner` nesne.|
|[~static_partitioner Destructor](#dtor)|Yok eder bir `static_partitioner` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`static_partitioner`

## <a name="requirements"></a>Gereksinimler

**Başlık:** ppl.h

**Namespace:** eşzamanlılık

##  <a name="dtor"></a> ~static_partitioner

Yok eder bir `static_partitioner` nesne.

```
~static_partitioner();
```

##  <a name="ctor"></a> static_partitioner

Oluşturur bir `static_partitioner` nesne.

```
static_partitioner();
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
