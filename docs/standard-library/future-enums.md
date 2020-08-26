---
title: '&lt;gelecekteki &gt; numaralandırmalar'
ms.date: 11/04/2016
f1_keywords:
- future/std::future_errc
- future/std::future_status
- future/std::launch
ms.assetid: 8c675645-db47-4cab-bc0e-7b87f8a302df
ms.openlocfilehash: 45dc3277b3f14b7f9dbb043cf9db1f1865d4e4c9
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838028"
---
# <a name="ltfuturegt-enums"></a>&lt;gelecekteki &gt; numaralandırmalar

[future_errc](#future_errc)\
[future_status](#future_status)\
[Man](#launch)

## <a name="future_errc-enumeration"></a><a name="future_errc"></a> future_errc numaralandırması

[Future_error](../standard-library/future-error-class.md) sınıfı tarafından bildirilen tüm hatalara yönelik sembolik adlar sağlar.

```cpp
class future_errc {
   broken_promise,
   future_already_retrieved,
   promise_already_satisfied,
   no_state
   };
```

## <a name="future_status-enumeration"></a><a name="future_status"></a> future_status numaralandırması

, Zaman aşımına uğramayı bekleyen bir işlevin döndürebileceği nedenlerle sembolik adlar sağlar.

```cpp
enum future_status{
    ready,
    timeout,
    deferred
};
```

## <a name="launch-enumeration"></a><a name="launch"></a> başlatma numaralandırması

[Zaman uyumsuz](../standard-library/future-functions.md#async)şablon işlevi için olası modları açıklayan bir bit maskesi türünü temsil eder.

```cpp
class launch{
   async,
   deferred
   };
```

## <a name="see-also"></a>Ayrıca bkz.

[\<future>](../standard-library/future.md)
