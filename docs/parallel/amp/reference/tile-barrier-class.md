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
ms.openlocfilehash: c00f1e41e70e723be185959eeff176390def7647
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374721"
---
# <a name="tile_barrier-class"></a>tile_barrier Sınıfı

İş parçacığı grubunda (döşeme) çalışan iş parçacıklarının yürütülmesini yöntemleri `wait` kullanarak eşitler. Yalnızca çalışma zamanı bu sınıfı anında kullanabilir.

## <a name="syntax"></a>Sözdizimi

```cpp
class tile_barrier;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[tile_barrier Yapıcı](#ctor)|`tile_barrier` sınıfının yeni bir örneğini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Bekle](#wait)|İş parçacığı grubundaki (döşeme) tüm iş parçacıklarının, döşemedeki tüm iş parçacıkları beklemeyi bitirene kadar yürütmeyi durdurmasını bildirir.|
|[wait_with_all_memory_fence](#wait_with_all_memory_fence)|Tüm bellek erişimleri tamamlanana ve döşemedeki tüm iş parçacıkları bu çağrıya ulaşana kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller.|
|[wait_with_global_memory_fence](#wait_with_global_memory_fence)|Tüm genel bellek erişimleri tamamlanana ve döşemedeki tüm iş parçacıkları bu çağrıya ulaşana kadar bir döşemedeki tüm iş parçacıklarının yürütülmesini engeller.|
|[wait_with_tile_static_memory_fence](#wait_with_tile_static_memory_fence)|Tüm `tile_static` bellek erişimleri tamamlanana ve döşemedeki tüm iş parçacıkları bu çağrıya ulaşana kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tile_barrier`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amp.h

**Ad alanı:** Eşzamanlılık

## <a name="tile_barrier-constructor"></a><a name="ctor"></a>tile_barrier Yapıcı

Varolan bir tanesini kopyalayarak sınıfın yeni bir örneğini başolarak adlandırır.

### <a name="syntax"></a>Sözdizimi

```cpp
tile_barrier(
    const tile_barrier& _Other ) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
Kopyalanması `tile_barrier` gereken nesne.

## <a name="wait"></a>Bekle

İş parçacığı grubundaki (döşeme) tüm iş parçacıklarının, döşemedeki tüm iş parçacıkları bekleme yi bitirene kadar yürütmeyi durdurmasını bildirir.

### <a name="syntax"></a>Sözdizimi

```cpp
void wait() const restrict(amp);
```

## <a name="wait_with_all_memory_fence"></a><a name="wait_with_all_memory_fence"></a>wait_with_all_memory_fence

Döşemedeki tüm iş parçacıkları bu çağrıya ulaşana kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller. Bu, tüm bellek erişimlerinin iş parçacığı döşemesindeki diğer iş parçacıkları tarafından görünür olmasını ve program sırasına göre yürütülmesini sağlar.

### <a name="syntax"></a>Sözdizimi

```cpp
void wait_with_all_memory_fence() const restrict(amp);
```

## <a name="a-namewait_with_global_memory_fence-wait_with_global_memory_fence"></a><a name="wait_with_global_memory_fence">wait_with_global_memory_fence

Döşemedeki tüm iş parçacıkları bu çağrıya ulaşana kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller. Bu, tüm genel bellek erişimlerinin iş parçacığı döşemesindeki diğer iş parçacıkları tarafından görünür olmasını ve program sırasına göre yürütülmesini sağlar.

### <a name="syntax"></a>Sözdizimi

```cpp
void wait_with_global_memory_fence() const  restrict(amp);
```

## <a name="a-namewait_with_tile_static_memory_fence-wait_with_tile_static_memory_fence"></a><a name="wait_with_tile_static_memory_fence">wait_with_tile_static_memory_fence

Döşemedeki tüm iş parçacıkları bu çağrıya ulaşana kadar döşemedeki tüm iş parçacıklarının yürütülmesini engeller. Bu, `tile_static` bellek erişimlerinin iş parçacığı döşemesindeki diğer iş parçacıkları tarafından görünür olmasını ve program sırasına göre yürütülmesini sağlar.

### <a name="syntax"></a>Sözdizimi

```cpp
void wait_with_tile_static_memory_fence() const restrict(amp);
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
