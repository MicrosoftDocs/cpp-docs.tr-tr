---
title: '&lt;Yeni&gt; tür tanımları'
ms.date: 11/04/2016
f1_keywords:
- new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
ms.openlocfilehash: 80123bc35422984ef92bdba6da45052d3461b1d7
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245147"
---
# <a name="ltnewgt-typedefs"></a>&lt;Yeni&gt; tür tanımları

## <a name="hardware_constructive_interference_size"></a> hardware_constructive_interference_size

```cpp
inline constexpr size_t hardware_constructive_interference_size = implementation-defined;
```

### <a name="remarks"></a>Açıklamalar

Zamana bağlı konumu ile eşzamanlı iş parçacığı tarafından erişilen iki nesneler tarafından kaplanan bitişik bellek boyutunu önerilen en yüksek sayıdır. En az tutulamaz `alignof(max_align_t)`.

### <a name="example"></a>Örnek

```cpp
struct together { 
    atomic<int> dog;
    int puppy;
};

struct kennel {
    // Other data members...
    alignas(sizeof(together)) together pack;
    // Other data members...
};

static_assert(sizeof(together) <= hardware_constructive_interference_size);
```

## <a name="hardware_destructive_interference_size"></a> hardware_destructive_interference_size

```cpp
inline constexpr size_t hardware_destructive_interference_size = implementation-defined;
```

### <a name="remarks"></a>Açıklamalar

Çekişme uygulama tarafından sunulan ek performans düşüşünü önlemek için iki eş zamanlı olarak erişilen nesneler arasındaki en az önerilen uzaklığı sayıdır. En az tutulamaz `alignof(max_align_t)`.

### <a name="example"></a>Örnek

```cpp
struct keep_apart {
    alignas(hardware_destructive_interference_size) atomic<int> cat;
    alignas(hardware_destructive_interference_size) atomic<int> dog;
};
```

## <a name="new_handler"></a> new_handler

Uygun bir işlev türü işaret yeni bir işleyici kullanın.

```cpp
typedef void (*new_handler)();
```

### <a name="remarks"></a>Açıklamalar

Bu tür bir işleyici işlevi çağıran **new işleci** veya `operator new[]` ne zaman bunlar olamaz karşılamak için ek depolama alanı istek.

### <a name="example"></a>Örnek

Bkz: [set_new_handler](../standard-library/new-functions.md#set_new_handler) bir örnek için `new_handler` dönüş değeri olarak.
