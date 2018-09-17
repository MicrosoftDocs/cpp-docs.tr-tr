---
title: '&lt;Gelecekteki&gt; sabit listeleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- future/std::future_errc
- future/std::future_status
- future/std::launch
ms.assetid: 8c675645-db47-4cab-bc0e-7b87f8a302df
ms.openlocfilehash: 0056d54844e9396d517fd44c3649f1bc9605829b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700563"
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
