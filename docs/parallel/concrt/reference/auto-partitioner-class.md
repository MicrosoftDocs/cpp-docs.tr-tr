---
title: auto_partitioner Sınıfı
ms.date: 11/04/2016
f1_keywords:
- auto_partitioner
- PPL/concurrency::auto_partitioner
- PPL/concurrency::auto_partitioner::auto_partitioner
helpviewer_keywords:
- auto_partitioner class
ms.assetid: 7cc08e5d-20b4-47a4-b4b5-c214a78f5a9e
ms.openlocfilehash: 2d8bbb8e8af17dd19953487c47e5fd40343fe349
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57264826"
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
|[~auto_partitioner Destructor](#dtor)|Yok eder bir `auto_partitioner` nesne.|

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

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
