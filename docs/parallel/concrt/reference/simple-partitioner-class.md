---
title: simple_partitioner Sınıfı
ms.date: 11/04/2016
f1_keywords:
- simple_partitioner
- PPL/concurrency::simple_partitioner
- PPL/concurrency::simple_partitioner::simple_partitioner
helpviewer_keywords:
- simple_partitioner class
ms.assetid: d7e997af-54d1-43f5-abe0-def72df6edb3
ms.openlocfilehash: 372773926903da32f1690904b34cd143a04940dd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62337251"
---
# <a name="simplepartitioner-class"></a>simple_partitioner Sınıfı

`simple_partitioner` Sınıfı temsil eder bir statik tarafından üzerinden yinelenir aralık bölümleme `parallel_for`. Her öbek öbek boyutu tarafından belirtilen yineleme sayısını en az sahip olacak şekilde bölümleyici aralığı öbeklere böler.

## <a name="syntax"></a>Sözdizimi

```
class simple_partitioner;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[simple_partitioner](#ctor)|Oluşturur bir `simple_partitioner` nesne.|
|[~ simple_partitioner yok Edicisi](#dtor)|Yok eder bir `simple_partitioner` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`simple_partitioner`

## <a name="requirements"></a>Gereksinimler

**Başlık:** ppl.h

**Namespace:** eşzamanlılık

##  <a name="dtor"></a> ~ simple_partitioner

Yok eder bir `simple_partitioner` nesne.

```
~simple_partitioner();
```

##  <a name="ctor"></a> simple_partitioner

Oluşturur bir `simple_partitioner` nesne.

```
explicit simple_partitioner(_Size_type _Chunk_size);
```

### <a name="parameters"></a>Parametreler

*_Chunk_size*<br/>
En düşük bölüm boyutu.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
