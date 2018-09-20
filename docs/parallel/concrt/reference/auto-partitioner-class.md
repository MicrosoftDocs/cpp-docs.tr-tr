---
title: auto_partitioner sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- auto_partitioner
- PPL/concurrency::auto_partitioner
- PPL/concurrency::auto_partitioner::auto_partitioner
dev_langs:
- C++
helpviewer_keywords:
- auto_partitioner class
ms.assetid: 7cc08e5d-20b4-47a4-b4b5-c214a78f5a9e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a2bb62d76733e77c2528a80dfc4e9ef358878895
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425417"
---
# <a name="autopartitioner-class"></a>auto_partitioner Sınıfı

`auto_partitioner` Sınıfı temsil eder, varsayılan yöntemi `parallel_for`, `parallel_for_each` ve `parallel_transform` yinelenir üzerinden aralık bölümleme için kullanın. Employes bölümleme bu yöntemi Yük Dengeleme için çalma aralığı yanı sıra başına-iptal yineleyin.

## <a name="syntax"></a>Sözdizimi

```
class auto_partitioner;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[auto_partitioner](#ctor)|Oluşturur bir `auto_partitioner` nesne.|
|[~ auto_partitioner yok Edicisi](#dtor)|Yok eder bir `auto_partitioner` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`auto_partitioner`

## <a name="requirements"></a>Gereksinimler

**Başlık:** ppl.h

**Namespace:** eşzamanlılık

##  <a name="dtor"></a> ~ auto_partitioner

Yok eder bir `auto_partitioner` nesne.

```
~auto_partitioner();
```

##  <a name="ctor"></a> auto_partitioner

Oluşturur bir `auto_partitioner` nesne.

```
auto_partitioner();
```

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
