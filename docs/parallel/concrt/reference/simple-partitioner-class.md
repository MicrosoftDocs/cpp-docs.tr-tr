---
description: 'Hakkında daha fazla bilgi edinin: simple_partitioner sınıfı'
title: simple_partitioner Sınıfı
ms.date: 11/04/2016
f1_keywords:
- simple_partitioner
- PPL/concurrency::simple_partitioner
- PPL/concurrency::simple_partitioner::simple_partitioner
helpviewer_keywords:
- simple_partitioner class
ms.assetid: d7e997af-54d1-43f5-abe0-def72df6edb3
ms.openlocfilehash: 76dcac6d7fc2dce5b69d0a9dbefaf01420f8bcde
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188696"
---
# <a name="simple_partitioner-class"></a>simple_partitioner Sınıfı

`simple_partitioner`Sınıfı, tarafından tarafından yineleyen aralığın statik bir bölümlemesini temsil eder `parallel_for` . Bölümleyici, aralığı parçalara böler, her öbek en az öbek boyutu tarafından belirtilen yineleme sayısına sahiptir.

## <a name="syntax"></a>Syntax

```cpp
class simple_partitioner;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[simple_partitioner](#ctor)|Bir `simple_partitioner` nesnesi oluşturur.|
|[~ simple_partitioner yok edici](#dtor)|Bir nesneyi yok eder `simple_partitioner` .|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`simple_partitioner`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** PPL. h

**Ad alanı:** eşzamanlılık

## <a name="simple_partitioner"></a><a name="dtor"></a> ~ simple_partitioner

Bir nesneyi yok eder `simple_partitioner` .

```cpp
~simple_partitioner();
```

## <a name="simple_partitioner"></a><a name="ctor"></a> simple_partitioner

Bir `simple_partitioner` nesnesi oluşturur.

```cpp
explicit simple_partitioner(_Size_type _Chunk_size);
```

### <a name="parameters"></a>Parametreler

*_Chunk_size*<br/>
En küçük bölüm boyutu.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)
