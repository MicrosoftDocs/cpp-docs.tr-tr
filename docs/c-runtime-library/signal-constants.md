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
ms.openlocfilehash: e9953e967d1c94ae56dfc1063fb0deafa342631c
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57738722"
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

## <a name="see-also"></a>Ayrıca bkz.

[signal](../c-runtime-library/reference/signal.md)<br/>
[raise](../c-runtime-library/reference/raise.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)
