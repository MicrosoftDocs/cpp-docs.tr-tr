---
title: static_partitioner sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- static_partitioner
- PPL/concurrency::static_partitioner
- PPL/concurrency::static_partitioner::static_partitioner
dev_langs:
- C++
helpviewer_keywords:
- static_partitioner class
ms.assetid: 2b3dbdf0-6eb9-49f6-8639-03df1d974143
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de1b63cf24fbc84130302fcbae2cb965e8d00597
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376026"
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
|[~ static_partitioner yok Edicisi](#dtor)|Yok eder bir `static_partitioner` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`static_partitioner`

## <a name="requirements"></a>Gereksinimler

**Başlık:** ppl.h

**Namespace:** eşzamanlılık

##  <a name="dtor"></a> ~ static_partitioner

Yok eder bir `static_partitioner` nesne.

```
~static_partitioner();
```

##  <a name="ctor"></a> static_partitioner

Oluşturur bir `static_partitioner` nesne.

```
static_partitioner();
```

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
