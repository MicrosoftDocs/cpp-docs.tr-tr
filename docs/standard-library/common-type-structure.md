---
title: common_type Yapısı
ms.date: 11/04/2016
f1_keywords:
- chrono/std::common_type
ms.assetid: 2b42722c-c3dc-4d62-8613-0271e52b6f00
ms.openlocfilehash: 4d2f1fe6ebf5b8f35f65fb9b551e6e7d473615a4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50435340"
---
# <a name="commontype-structure"></a>common_type Yapısı

Şablon sınıfı uzmanlıklarını tanımlar [common_type](../standard-library/common-type-class.md) örneklemeleri için [süresi](../standard-library/duration-class.md) ve [time_point](../standard-library/time-point-class.md).

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Rep1, class Period1,
    class Rep2, class Period2>
struct common_type
<chrono::duration<Rep1, Period1>,
chrono::duration<Rep2, Period2>>;

template <class Clock,
    class Duration1, class Duration2>
struct common_type
<chrono::time_point<Clock, Duration1>,
chrono::time_point<Clock, Duration2>>;
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<chrono >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<chrono >](../standard-library/chrono.md)<br/>
