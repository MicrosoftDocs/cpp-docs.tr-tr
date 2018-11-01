---
title: sinyal Sabitleri
ms.date: 11/04/2016
f1_keywords:
- SIGTERM
- SIGFPE
- SIGABRT
- SIGILL
- SIGINT
- SIGSEGV
helpviewer_keywords:
- SIGTERM constant
- SIGABRT constant
- SIGSEGV constant
- SIGFPE constant
- SIGINT constant
- signal constants
- SIGILL constant
ms.assetid: a3b39281-dae7-4e44-8d68-e6a610c669dd
ms.openlocfilehash: 1046a12fa0f250b348e6ff171c8865e3eb5ff4b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482681"
---
# <a name="signal-constants"></a>sinyal Sabitleri

## <a name="syntax"></a>Sözdizimi

```
#include <signal.h>
```

## <a name="remarks"></a>Açıklamalar

`sig` Bağımsız değişken bildirim Sabitleri (tanımlandığı SİNYAL. listelenen biri olması gerekir H).

|||
|-|-|
|SIGABRT|Olağan dışı sonlandırma. Varsayılan eylem çağıran programı çıkış kodu 3 ile sonlandırır.  |
|SIGABRT_COMPAT|SIGABRT ile aynıdır. Diğer platformlar ile uyumluluk için.  |
|SIGFPE|Taşma, sıfır veya geçersiz işlem bölme gibi kayan nokta hatası. Varsayılan eylem çağırma programını sonlandırır.  |
|SIGILL|Geçersiz yönerge. Varsayılan eylem çağırma programını sonlandırır.  |
|SIGINT|CTRL + C kesme. Varsayılan eylem çağıran programı çıkış kodu 3 ile sonlandırır.  |
|SIGSEGV|Geçersiz depo erişimi. Varsayılan eylem çağırma programını sonlandırır.  |
|SIGTERM|Programa gönderilen sonlandırma isteği. Varsayılan eylem çağıran programı çıkış kodu 3 ile sonlandırır.  |
|SIG_ERR|Bir dönüş türü sinyalinden belirten bir hata oluştu.  |

## <a name="see-also"></a>Ayrıca Bkz.

[signal](../c-runtime-library/reference/signal.md)<br/>
[raise](../c-runtime-library/reference/raise.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)