---
description: 'Daha fazla bilgi edinin: &lt; Yeni &gt; tür tanımları'
title: '&lt;Yeni &gt; tür tanımları'
ms.date: 11/04/2016
f1_keywords:
- new/std::new_handler
ms.assetid: aef01de1-06b5-4b6c-aebc-2c9f423d7e47
ms.openlocfilehash: 0c8e73f10b8429d2c55805c017dded98843af9f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338157"
---
# <a name="ltnewgt-typedefs"></a>&lt;Yeni &gt; tür tanımları

## <a name="hardware_constructive_interference_size"></a><a name="hardware_constructive_interference_size"></a> hardware_constructive_interference_size

```cpp
inline constexpr size_t hardware_constructive_interference_size = implementation-defined;
```

### <a name="remarks"></a>Açıklamalar

Bu sayı, eş zamanlı iş parçacıkları tarafından zamana bağlı olarak erişilen iki nesne tarafından en fazla önerilen bitişik bellek boyutudur. En az olacaktır `alignof(max_align_t)` .

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

## <a name="hardware_destructive_interference_size"></a><a name="hardware_destructive_interference_size"></a> hardware_destructive_interference_size

```cpp
inline constexpr size_t hardware_destructive_interference_size = implementation-defined;
```

### <a name="remarks"></a>Açıklamalar

Bu sayı, uygulama tarafından tanıtılan çekişme nedeniyle ek performans düşüşünü önlemek için iki eşzamanlı olarak erişilen iki nesne arasında önerilen en düşük uzaklığa sahiptir. En az olacaktır `alignof(max_align_t)` .

### <a name="example"></a>Örnek

```cpp
struct keep_apart {
    alignas(hardware_destructive_interference_size) atomic<int> cat;
    alignas(hardware_destructive_interference_size) atomic<int> dog;
};
```

## <a name="new_handler"></a><a name="new_handler"></a> new_handler

Türü, yeni işleyici olarak kullanım için uygun bir işleve işaret eder.

```cpp
typedef void (*new_handler)();
```

### <a name="remarks"></a>Açıklamalar

Bu tür işleyici işlevi, **New işleci** veya `operator new[]` ek depolama için bir isteği karşılayamadığı zaman tarafından çağırılır.

### <a name="example"></a>Örnek

Dönüş değeri olarak kullanılan bir örnek için bkz. [set_new_handler](../standard-library/new-functions.md#set_new_handler) `new_handler` .
