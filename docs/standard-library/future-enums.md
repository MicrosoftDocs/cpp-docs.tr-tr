---
title: '&lt;Gelecekteki&gt; sabit listeleri'
ms.date: 11/04/2016
f1_keywords:
- future/std::future_errc
- future/std::future_status
- future/std::launch
ms.assetid: 8c675645-db47-4cab-bc0e-7b87f8a302df
ms.openlocfilehash: 1e487128d4af5c6f9b3f29f5c71e52f616e1807a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159528"
---
# <a name="ltfuturegt-enums"></a>&lt;Gelecekteki&gt; sabit listeleri

||||
|-|-|-|
|[future_errc](#future_errc)|[future_status](#future_status)|[başlatma](#launch)|

## <a name="future_errc"></a>  future_errc numaralandırması

Tüm tarafından bildirilen hataları için simgesel adlar sağlar [future_error](../standard-library/future-error-class.md) sınıfı.

```cpp
class future_errc {
   broken_promise,
   future_already_retrieved,
   promise_already_satisfied,
   no_state
   };
```

## <a name="future_status"></a>  future_status numaralandırması

Zamanlanmış bekleme işlevi döndürebilir nedenleri için simgesel adlar sağlar.

```cpp
enum future_status{
    ready,
    timeout,
    deferred
};
```

## <a name="launch"></a>  launch numaralandırması

Şablon işlevi için olası modları açıklar bir bit maskesi türünü temsil eden [zaman uyumsuz](../standard-library/future-functions.md#async).

```cpp
class launch{
   async,
   deferred
   };
```

## <a name="see-also"></a>Ayrıca bkz.

[\<gelecek >](../standard-library/future.md)<br/>
