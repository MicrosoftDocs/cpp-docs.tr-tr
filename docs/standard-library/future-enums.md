---
title: '&lt;Gelecekteki&gt; numaralandırmaları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- future/std::future_errc
- future/std::future_status
- future/std::launch
ms.assetid: 8c675645-db47-4cab-bc0e-7b87f8a302df
ms.openlocfilehash: 6e228eb538a0d281dff8066390b0c6dd2e7ea4d8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="ltfuturegt-enums"></a>&lt;Gelecekteki&gt; numaralandırmaları

||||
|-|-|-|
|[future_errc](#future_errc)|[future_status](#future_status)|[başlatma](#launch)|

## <a name="future_errc"></a>  future_errc numaralandırması

Sağladığı tüm tarafından bildirilen hataları için simgesel adları [future_error](../standard-library/future-error-class.md) sınıfı.

sınıf future_errc {broken_promise, future_already_retrieved, promise_already_satisfied, no_state};

## <a name="future_status"></a>  future_status numaralandırması

Zamanlanmış bekleme işlevi döndürebilir nedeniyle simgesel adları sağlar.

```cpp
enum future_status{    ready,
    timeout,
 deferred};
```

## <a name="launch"></a>  launch numaralandırması

Şablon işlevi için olası modları tanımlayan bir bit maskesi türünü temsil eden [zaman uyumsuz](../standard-library/future-functions.md#async).

sınıf başlatma {ertelenmiş zaman uyumsuz,};

## <a name="see-also"></a>Ayrıca bkz.

[\<sonraki >](../standard-library/future.md)<br/>
