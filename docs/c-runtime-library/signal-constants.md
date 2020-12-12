---
description: 'Daha fazla bilgi edinin: sinyal sabitleri'
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
ms.openlocfilehash: 57615e3a694ae24c0bfefe42b6a8ddd1de2a55ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277004"
---
# <a name="signal-constants"></a>sinyal Sabitleri

## <a name="syntax"></a>Syntax

```
#include <signal.h>
```

## <a name="remarks"></a>Açıklamalar

`sig`Bağımsız değişken aşağıda listelenen bildirim sabitlerinden biri olmalıdır (sinyal içinde tanımlanmıştır). H).

|Sabit|Açıklama|
|-|-|
|SıGABRT|Olağan dışı sonlandırma. Varsayılan eylem, çağıran programı çıkış kodu 3 ile sonlandırır.  |
|SIGABRT_COMPAT|SIGABRT ile aynı. Diğer platformlarla uyumluluk için.  |
|SıGFPE|Taşma, sıfıra bölme veya geçersiz işlem gibi kayan nokta hatası. Varsayılan eylem, çağıran programı sonlandırır.  |
|SıGıLL|Geçersiz yönerge. Varsayılan eylem, çağıran programı sonlandırır.  |
|SıGıNT|CTRL + C kesme. Varsayılan eylem, çağıran programı çıkış kodu 3 ile sonlandırır.  |
|SıGSEGV|Geçersiz depolama erişimi. Varsayılan eylem, çağıran programı sonlandırır.  |
|SıGTERM|Programa sonlandırma isteği gönderildi. Varsayılan eylem, çağıran programı çıkış kodu 3 ile sonlandırır.  |
|SIG_ERR|Bir hatayı gösteren bir sinyalin dönüş türü oluştu.  |

## <a name="see-also"></a>Ayrıca bkz.

[sinyal](../c-runtime-library/reference/signal.md)<br/>
[tetikle](../c-runtime-library/reference/raise.md)<br/>
[Global sabitler](../c-runtime-library/global-constants.md)
