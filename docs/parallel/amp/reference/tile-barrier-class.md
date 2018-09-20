---
title: tile_barrier sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- tile_barrier
- AMP/tile_barrier
- AMP/Concurrency::tile_barrier::tile_barrier::tile_barrier
- AMP/Concurrency::tile_barrier::tile_barrier::wait
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_all_memory_fence
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_global_memory_fence
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_tile_static_memory_fence
dev_langs:
- C++
helpviewer_keywords:
- tile_barrier class
ms.assetid: b4ccdccb-0032-4e11-b7bd-dc9d43445dee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eab8fbba799c84fdc9246659b5880cdc9f266084
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46406983"
---
# <a name="tilebarrier-class"></a>tile_barrier Sınıfı

Kullanarak iş parçacığı grubunda (döşeme) çalışan iş parçacıklarının yürütülmesini eşitler `wait` yöntemleri. Yalnızca çalışma zamanı bu sınıfın örneğini oluşturabilir.

### <a name="syntax"></a>Sözdizimi

```
class tile_barrier;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[tile_barrier Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `tile_barrier` sınıfı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[bekleme](#wait)|Tüm iş parçacıkları iş parçacığı grubunda (döşeme) döşemedeki tüm iş parçacıkları beklemeyi bitirene kadar yürütmeyi durdurmasını söyler.|
|[wait_with_all_memory_fence](#wait_with_all_memory_fence)|Tüm bellek erişimleri tamamlanana kadar döşemedeki tüm iş parçacıklarının ve döşemedeki tüm iş parçacıklarının yürütülmesini engeller Bu çağrı sınırına.|
|[wait_with_global_memory_fence](#wait_with_global_memory_fence)|Tüm genel bellek erişimleri tamamlanana ve döşemedeki tüm iş parçacıkları bu çağrıya ulaşıncaya kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller.|
|[wait_with_tile_static_memory_fence](#wait_with_tile_static_memory_fence)|Tüm kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller `tile_static` bellek erişimleri tamamlanana ve döşemedeki tüm iş parçacıkları bu çağrıya ulaşıncaya.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tile_barrier`

## <a name="requirements"></a>Gereksinimler

**Başlık:** amp.h

**Namespace:** eşzamanlılık

## <a name="tile_barrier__ctor"></a>  tile_barrier Oluşturucusu

Mevcut bir kopyalayarak sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```
tile_barrier(
    const tile_barrier& _Other ) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Diğer*<br/>
`tile_barrier` Kopyalanacak nesne.

## <a name="wait"></a>  bekleme

Döşemedeki tüm iş parçacıkları beklemeyi bitirene kadar yürütmeyi durdurmak için iş parçacığı grubunda (döşeme) tüm iş parçacıklarının bildirir.

### <a name="syntax"></a>Sözdizimi

```
void wait() const restrict(amp);
```

## <a name="wait_with_all_memory_fence"></a>  wait_with_all_memory_fence

Döşemedeki tüm iş parçacıkları bu çağrıya ulaşıncaya kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller. Bu, tüm bellek erişimlerinin iş parçacığı döşemesindeki diğer iş parçacıkları tarafından ve program sırasıyla yürütülen sağlar.

### <a name="syntax"></a>Sözdizimi

```
void wait_with_all_memory_fence() const restrict(amp);
```

## <a name="wait_with_global_memory_fence"></a>  wait_with_global_memory_fence

Döşemedeki tüm iş parçacıkları bu çağrıya ulaşıncaya kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller. Bu, tüm genel bellek erişimlerinin iş parçacığı döşemesindeki diğer iş parçacıkları tarafından ve program sırasıyla yürütülen sağlar.

### <a name="syntax"></a>Sözdizimi

```
void wait_with_global_memory_fence() const  restrict(amp);
```

## <a name="wait_with_tile_static_memory_fence"></a>  wait_with_tile_static_memory_fence

Döşemedeki tüm iş parçacıkları bu çağrıya ulaşıncaya kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller. Bu, sağlar `tile_static` bellek erişimlerinin iş parçacığı döşemesindeki diğer iş parçacıkları tarafından ve program sırasıyla yürütülen.

### <a name="syntax"></a>Sözdizimi

```
void wait_with_tile_static_memory_fence() const restrict(amp);
```

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
