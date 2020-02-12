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
ms.openlocfilehash: 503f36b90c5eb3319f9aa2d56528172ffa95bb11
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142507"
---
# <a name="simple_partitioner-class"></a>simple_partitioner Sınıfı

`simple_partitioner` sınıfı, `parallel_for`tarafından yineleyen aralığın statik bir bölümlemesini temsil eder. Bölümleyici, aralığı parçalara böler, her öbek en az öbek boyutu tarafından belirtilen yineleme sayısına sahiptir.

## <a name="syntax"></a>Sözdizimi

```cpp
class simple_partitioner;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[simple_partitioner](#ctor)|`simple_partitioner` nesnesi oluşturur.|
|[~ simple_partitioner yok edici](#dtor)|`simple_partitioner` nesnesini yok eder.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`simple_partitioner`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** PPL. h

**Ad alanı:** eşzamanlılık

## <a name="dtor"></a>~ simple_partitioner

`simple_partitioner` nesnesini yok eder.

```cpp
~simple_partitioner();
```

## <a name="ctor"></a>simple_partitioner

`simple_partitioner` nesnesi oluşturur.

```cpp
explicit simple_partitioner(_Size_type _Chunk_size);
```

### <a name="parameters"></a>Parametreler

*_Chunk_size*<br/>
En küçük bölüm boyutu.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
