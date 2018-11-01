---
title: EOF, WEOF
ms.date: 11/04/2016
f1_keywords:
- EOF
helpviewer_keywords:
- EOF function
- WEOF function
- end of file
ms.assetid: a7150563-cdae-4cdf-9798-ad509990e505
ms.openlocfilehash: 9317fdad16121374b31e0862f3326f4150c71579
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667395"
---
# <a name="eof-weof"></a>EOF, WEOF

## <a name="syntax"></a>Sözdizimi

```

#include <stdio.h>
```

## <a name="remarks"></a>Açıklamalar

EOF bir g/ç yordam tarafından döndürülen zaman son dosya (veya bazı durumlarda, bir hata) karşılaşıldı.

WEOF türünün dönüş değerini verir **wint_t**geniş bir akışın sonuna sinyali veya bir hata durumu bildirmek için kullanılır.

## <a name="see-also"></a>Ayrıca Bkz.

[putc, putwc](../c-runtime-library/reference/putc-putwc.md)<br/>
[ungetc, ungetwc](../c-runtime-library/reference/ungetc-ungetwc.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[fflush](../c-runtime-library/reference/fflush.md)<br/>
[fclose, _fcloseall](../c-runtime-library/reference/fclose-fcloseall.md)<br/>
[_ungetch, _ungetwch, _ungetch_nolock, _ungetwch_nolock](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)<br/>
[_putch, _putwch](../c-runtime-library/reference/putch-putwch.md)<br/>
[isascii, __isascii, iswascii](../c-runtime-library/reference/isascii-isascii-iswascii.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)