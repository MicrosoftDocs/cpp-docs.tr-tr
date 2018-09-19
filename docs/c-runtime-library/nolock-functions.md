---
title: _nolock işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- _nolock functions
- nolock functions
ms.assetid: 7d651d87-38d2-4303-9897-fdb5f7a3e899
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55141ac6b95a045bd248fbcb3008cde6cb4a70a4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023546"
---
# <a name="nolock-functions"></a>_nolock İşlevleri

Bu, herhangi bir kilitleme gerçekleştirmeyin işlevlerdir. Bunlar, en yüksek performansı ihtiyaç duyan kullanıcılar için sağlanır. Daha fazla bilgi için [birden çok iş parçacıklı kitaplık performansı](../c-runtime-library/multithreaded-libraries-performance.md).

_Nolock işlevleri, yalnızca programınız gerçekten tek iş parçacıklı olup olmadığını veya kendi kilitleme aşması durumunda kullanın.

## <a name="no-lock-routines"></a>Hiçbir kilidi rutinleri

[_fclose_nolock](../c-runtime-library/reference/fclose-nolock.md)

[_fflush_nolock](../c-runtime-library/reference/fflush-nolock.md)

[_fgetc_nolock, _fgetwc_nolock](../c-runtime-library/reference/fgetc-nolock-fgetwc-nolock.md)

[_fread_nolock](../c-runtime-library/reference/fread-nolock.md)

[_fseek_nolock, _fseeki64_nolock](../c-runtime-library/reference/fseek-nolock-fseeki64-nolock.md)

[_ftell_nolock, _ftelli64_nolock](../c-runtime-library/reference/ftell-nolock-ftelli64-nolock.md)

[_fwrite_nolock](../c-runtime-library/reference/fwrite-nolock.md)

[_getc_nolock, _getwc_nolock](../c-runtime-library/reference/getc-nolock-getwc-nolock.md)

[_getch_nolock, _getwch_nolock](../c-runtime-library/reference/getch-nolock-getwch-nolock.md)

[_getchar_nolock, _getwchar_nolock](../c-runtime-library/reference/getchar-nolock-getwchar-nolock.md)

[_getche_nolock, _getwche_nolock](../c-runtime-library/reference/getche-nolock-getwche-nolock.md)

[_getdcwd_nolock, _wgetdcwd_nolock](../c-runtime-library/reference/getdcwd-nolock-wgetdcwd-nolock.md)

[_putc_nolock, _putwc_nolock](../c-runtime-library/reference/putc-nolock-putwc-nolock.md)

[_putch_nolock, _putwch_nolock](../c-runtime-library/reference/putch-nolock-putwch-nolock.md)

[_putchar_nolock, _putwchar_nolock](../c-runtime-library/reference/putchar-nolock-putwchar-nolock.md)

[_ungetc_nolock, _ungetwc_nolock](../c-runtime-library/reference/ungetc-nolock-ungetwc-nolock.md)

[_ungetch_nolock, _ungetwch_nolock](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Girdi ve Çıktı](../c-runtime-library/input-and-output.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
