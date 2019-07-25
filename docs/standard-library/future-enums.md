---
title: '&lt;gelecekteki&gt; numaralandırmalar'
ms.date: 11/04/2016
f1_keywords:
- future/std::future_errc
- future/std::future_status
- future/std::launch
ms.assetid: 8c675645-db47-4cab-bc0e-7b87f8a302df
ms.openlocfilehash: a5bcebd80b296a0b8416580aa03acc59ce3750cd
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448221"
---
# <a name="ltfuturegt-enums"></a>&lt;gelecekteki&gt; numaralandırmalar

||||
|-|-|-|
|[future_errc](#future_errc)|[future_status](#future_status)|[Man](#launch)|

## <a name="future_errc"></a>future_errc numaralandırması

[Future_error](../standard-library/future-error-class.md) sınıfı tarafından bildirilen tüm hatalar için simgesel adlar sağlar.

```cpp
class future_errc {
   broken_promise,
   future_already_retrieved,
   promise_already_satisfied,
   no_state
   };
```

## <a name="future_status"></a>future_status numaralandırması

, Zaman aşımına uğramayı bekleyen bir işlevin döndürebileceği nedenlerle sembolik adlar sağlar.

```cpp
enum future_status{
    ready,
    timeout,
    deferred
};
```

## <a name="launch"></a>başlatma numaralandırması

[Zaman uyumsuz](../standard-library/future-functions.md#async)şablon işlevi için olası modları açıklayan bir bit maskesi türünü temsil eder.

```cpp
class launch{
   async,
   deferred
   };
```

## <a name="see-also"></a>Ayrıca bkz.

[\<gelecekte >](../standard-library/future.md)
