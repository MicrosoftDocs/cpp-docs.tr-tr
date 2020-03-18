---
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
ms.openlocfilehash: 757309a10da3e6d1c9c053430cce2cf603380b1f
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79422285"
---
# <a name="tile_barrier-class"></a>tile_barrier Sınıfı

`wait` yöntemleri kullanarak iş parçacığı grubunda (kutucukta) çalışan iş parçacıklarının yürütülmesini eşitler. Yalnızca çalışma zamanı bu sınıfın örneğini oluşturabilir.

## <a name="syntax"></a>Sözdizimi

```cpp
class tile_barrier;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Name|Açıklama|
|----------|-----------------|
|[tile_barrier Oluşturucusu](#ctor)|`tile_barrier` sınıfının yeni bir örneğini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Name|Açıklama|
|----------|-----------------|
|[bekleneceğini](#wait)|Kutucuktaki tüm iş parçacıklarının beklemeyi bitirene kadar iş parçacığı grubundaki (kutucuktaki) tüm iş parçacıklarının yürütmeyi durdurmasını söyler.|
|[wait_with_all_memory_fence](#wait_with_all_memory_fence)|Tüm bellek erişimleri tamamlanana ve döşemedeki tüm iş parçacıkları bu çağrıya ulaşana kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller.|
|[wait_with_global_memory_fence](#wait_with_global_memory_fence)|Tüm genel bellek erişimleri tamamlanana ve döşemedeki tüm iş parçacıkları bu çağrıya ulaşana kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller.|
|[wait_with_tile_static_memory_fence](#wait_with_tile_static_memory_fence)|Tüm `tile_static` bellek erişimleri tamamlanana ve kutucuktaki tüm iş parçacıklarının bu çağrıya ulaştığı sürece bir kutucuktaki tüm iş parçacıklarının yürütülmesini engeller.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tile_barrier`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** amp. h

**Ad alanı:** Zamanlı

## <a name="ctor"></a>tile_barrier Oluşturucusu

Mevcut bir tane kopyalayarak sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
tile_barrier(
    const tile_barrier& _Other ) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
Kopyalanacak `tile_barrier` nesnesi.

## <a name="wait"></a>bekleneceğini

Kutucuktaki tüm iş parçacıkları beklemeyi bitirene kadar iş parçacığı grubundaki (kutucuktaki) tüm iş parçacıklarını yürütmeyi durdurmasını söyler.

### <a name="syntax"></a>Sözdizimi

```cpp
void wait() const restrict(amp);
```

## <a name="wait_with_all_memory_fence"></a>wait_with_all_memory_fence

Bir kutucuktaki tüm iş parçacıkları bu çağrıya ulaşana kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller. Bu, tüm bellek erişimlerinin iş parçacığı döşemesindeki diğer iş parçacıkları tarafından görülebilir olmasını ve Program sırasıyla çalıştırılmasını sağlar.

### <a name="syntax"></a>Sözdizimi

```cpp
void wait_with_all_memory_fence() const restrict(amp);
```

## <a name="a-namewait_with_global_memory_fence-wait_with_global_memory_fence"></a><a name="wait_with_global_memory_fence"> wait_with_global_memory_fence

Bir kutucuktaki tüm iş parçacıkları bu çağrıya ulaşana kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller. Bu, tüm genel bellek erişimlerinin iş parçacığı döşemesindeki diğer iş parçacıkları tarafından görülebilir olmasını ve Program sırasıyla çalıştırılmasını sağlar.

### <a name="syntax"></a>Sözdizimi

```cpp
void wait_with_global_memory_fence() const  restrict(amp);
```

## <a name="a-namewait_with_tile_static_memory_fence-wait_with_tile_static_memory_fence"></a><a name="wait_with_tile_static_memory_fence"> wait_with_tile_static_memory_fence

Bir kutucuktaki tüm iş parçacıkları bu çağrıya ulaşana kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller. Böylece, `tile_static` belleği erişimleri iş parçacığı kutucuğunda diğer iş parçacıkları tarafından görülebilir ve Program sırasıyla yürütülür.

### <a name="syntax"></a>Sözdizimi

```cpp
void wait_with_tile_static_memory_fence() const restrict(amp);
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
