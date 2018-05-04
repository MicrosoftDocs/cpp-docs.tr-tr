---
title: Konsol ve bağlantı noktası g/ç | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.io
dev_langs:
- C++
helpviewer_keywords:
- routines, console and port I/O
- routines
- ports, I/O routines
- I/O [CRT], console
- I/O [CRT], port
- I/O routines, console and port I/O
ms.assetid: 0eee1c92-9b3d-41e0-a43a-257e546eeec8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e4d46582266234b4208a768fc7b2045af824349
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="console-and-port-io"></a>Konsol ve Bağlantı Noktası G/Ç

Bu yordamlar, okuma ve konsolunuza veya belirtilen bağlantı noktası üzerinde yazma. Konsol g/ç yordamları akış g/ç veya düşük düzey g/ç kitaplık yordamları ile uyumlu değildir. Açılacak veya g/ç gerçekleştirilmeden önce bu kategorideki hiçbir Aç veya kapat yordamları için kapalı konsol veya bağlantı noktası yok. Windows işletim sistemlerinde, bu işlevler çıktısını konsola her zaman yönlendirilir ve yönlendirilemez.

## <a name="console-and-port-io-routines"></a>Konsol ve bağlantı noktası g/ç yordamları

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-------------|---------|
|[_cgets, _cgetws](../c-runtime-library/cgets-cgetws.md), [_cgets_s, _cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md)|Dize konsolundan okuma|
|[_cprintf, _cwprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md), [_cprintf_s, _cprintf_s_l, _cwprintf_s, _cwprintf_s_l](../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)|Biçimlendirilmiş verileri konsola yazma|
|[_cputs](../c-runtime-library/reference/cputs-cputws.md)|Dize konsola yazma|
|[_cscanf, _cwscanf](../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md), [_cscanf_s, _cscanf_s_l, _cwscanf_s, _cwscanf_s_l](../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)|Konsolundan veri okuma biçimlendirilmiş|
|[_getch, _getwch](../c-runtime-library/reference/getch-getwch.md)|Konsolundan karakter okuma|
|[_getche, _getwche](../c-runtime-library/reference/getch-getwch.md)|Konsolundan karakter okuma ve onu echo|
|[_inp](../c-runtime-library/inp-inpw-inpd.md)|Belirtilen g/ç bağlantı noktasından bir bayt okuma|
|[_inpd](../c-runtime-library/inp-inpw-inpd.md)|Belirtilen g/ç bağlantı noktasından çift word okuma|
|[_inpw](../c-runtime-library/inp-inpw-inpd.md)|2-bayt word belirtilen g/ç bağlantı noktasından okuma|
|[_kbhit](../c-runtime-library/reference/kbhit.md)|Konsolunda tuş vuruşu denetleyin; konsolundan okumak için denemeden önce kullanın|
|[_outp](../c-runtime-library/outp-outpw-outpd.md)|Belirtilen g/ç bağlantı noktasına bir bayt yazma|
|[_outpd](../c-runtime-library/outp-outpw-outpd.md)|Belirtilen g/ç bağlantı noktasına çift word yazma|
|[_outpw](../c-runtime-library/outp-outpw-outpd.md)|Belirtilen g/ç bağlantı noktasına Word yazma|
|[_putch, _putwch](../c-runtime-library/reference/putch-putwch.md)|Karakter konsola yazma|
|[_ungetch, _ungetwch](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)|Okuma sonraki karakter olacak şekilde konsolundan okuma "Unget" son karakter|

## <a name="see-also"></a>Ayrıca Bkz.

[Girdi ve Çıktı](../c-runtime-library/input-and-output.md)<br/>
 [Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>