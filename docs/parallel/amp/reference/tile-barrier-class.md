---
description: 'Hakkında daha fazla bilgi edinin: tile_barrier sınıfı'
title: tile_barrier Sınıfı
ms.date: 03/27/2019
f1_keywords:
- tile_barrier
- AMP/tile_barrier
- AMP/Concurrency::tile_barrier::tile_barrier::tile_barrier
- AMP/Concurrency::tile_barrier::tile_barrier::wait
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_all_memory_fence
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_global_memory_fence
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_tile_static_memory_fence
helpviewer_keywords:
- tile_barrier class
ms.assetid: b4ccdccb-0032-4e11-b7bd-dc9d43445dee
ms.openlocfilehash: b4fd1758f9786f4cbb78556daadb0801795ca9c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321714"
---
# <a name="tile_barrier-class"></a>tile_barrier Sınıfı

, İş parçacığı grubunda (kutucukta) çalışan iş parçacıklarının yürütülmesini yöntemler kullanarak eşitler `wait` . Yalnızca çalışma zamanı bu sınıfın örneğini oluşturabilir.

## <a name="syntax"></a>Syntax

```cpp
class tile_barrier;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[tile_barrier Oluşturucusu](#ctor)|`tile_barrier` sınıfının yeni bir örneğini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[bekleneceğini](#wait)|Kutucuktaki tüm iş parçacıklarının beklemeyi bitirene kadar iş parçacığı grubundaki (kutucuktaki) tüm iş parçacıklarının yürütmeyi durdurmasını söyler.|
|[wait_with_all_memory_fence](#wait_with_all_memory_fence)|Tüm bellek erişimleri tamamlanana ve döşemedeki tüm iş parçacıkları bu çağrıya ulaşana kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller.|
|[wait_with_global_memory_fence](#wait_with_global_memory_fence)|Tüm genel bellek erişimleri tamamlanana ve döşemedeki tüm iş parçacıkları bu çağrıya ulaşana kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller.|
|[wait_with_tile_static_memory_fence](#wait_with_tile_static_memory_fence)|Tüm `tile_static` bellek erişimleri tamamlanana ve döşemedeki tüm iş parçacıkları bu çağrıya ulaşana kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tile_barrier`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** amp. h

**Ad alanı:** Zamanlı

## <a name="tile_barrier-constructor"></a><a name="ctor"></a> tile_barrier Oluşturucusu

Mevcut bir tane kopyalayarak sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
tile_barrier(
    const tile_barrier& _Other ) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
`tile_barrier`Kopyalanacak nesne.

## <a name="wait"></a>bekleneceğini

Kutucuktaki tüm iş parçacıkları beklemeyi bitirene kadar iş parçacığı grubundaki (kutucuktaki) tüm iş parçacıklarını yürütmeyi durdurmasını söyler.

### <a name="syntax"></a>Syntax

```cpp
void wait() const restrict(amp);
```

## <a name="wait_with_all_memory_fence"></a><a name="wait_with_all_memory_fence"></a> wait_with_all_memory_fence

Bir kutucuktaki tüm iş parçacıkları bu çağrıya ulaşana kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller. Bu, tüm bellek erişimlerinin iş parçacığı döşemesindeki diğer iş parçacıkları tarafından görülebilir olmasını ve Program sırasıyla çalıştırılmasını sağlar.

### <a name="syntax"></a>Syntax

```cpp
void wait_with_all_memory_fence() const restrict(amp);
```

## <a name="a-namewait_with_global_memory_fence-wait_with_global_memory_fence"></a><a name="wait_with_global_memory_fence"> wait_with_global_memory_fence

Bir kutucuktaki tüm iş parçacıkları bu çağrıya ulaşana kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller. Bu, tüm genel bellek erişimlerinin iş parçacığı döşemesindeki diğer iş parçacıkları tarafından görülebilir olmasını ve Program sırasıyla çalıştırılmasını sağlar.

### <a name="syntax"></a>Syntax

```cpp
void wait_with_global_memory_fence() const  restrict(amp);
```

## <a name="a-namewait_with_tile_static_memory_fence-wait_with_tile_static_memory_fence"></a><a name="wait_with_tile_static_memory_fence"> wait_with_tile_static_memory_fence

Bir kutucuktaki tüm iş parçacıkları bu çağrıya ulaşana kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller. Bu `tile_static` , bellek erişimlerinin iş parçacığı döşemesindeki diğer iş parçacıkları tarafından görülebilir olmasını ve Program sırasıyla çalıştırılmasını sağlar.

### <a name="syntax"></a>Syntax

```cpp
void wait_with_tile_static_memory_fence() const restrict(amp);
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
