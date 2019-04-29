---
title: Konsol ve Bağlantı Noktası G/Ç
ms.date: 11/04/2016
f1_keywords:
- c.io
helpviewer_keywords:
- routines, console and port I/O
- routines
- ports, I/O routines
- I/O [CRT], console
- I/O [CRT], port
- I/O routines, console and port I/O
ms.assetid: 0eee1c92-9b3d-41e0-a43a-257e546eeec8
ms.openlocfilehash: 55f97a70f2ce12f6363d234e9bbc9384d7ee9fe1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62344674"
---
# <a name="console-and-port-io"></a>Konsol ve Bağlantı Noktası G/Ç

Bu yordamların okuma ve yazma konsolunuzdaki veya belirtilen bağlantı noktası. Konsol g/ç yordamları akış g/ç veya düşük düzey g/ç kitaplık yordamları ile uyumlu değildir. Açılacak veya g/ç işlemi yapılmadan önce bu kategoride hiçbir açma veya kapatma yordamları için kapalı konsolu veya bağlantı noktası yok. Windows işletim sistemlerinde çıktısı bu işlevler, her zaman konsola yönlendirilir ve yönlendirilemiyor.

## <a name="console-and-port-io-routines"></a>Konsol ve bağlantı noktası g/ç yordamları

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-------------|---------|
|[_cgets, _cgetws](../c-runtime-library/cgets-cgetws.md), [_cgets_s, _cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md)|Konsoldan okunan dizisi|
|[_cprintf, _cwprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md), [_cprintf_s, _cprintf_s_l, _cwprintf_s, _cwprintf_s_l](../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)|Konsola biçimlendirilmiş veri yazma|
|[_cputs](../c-runtime-library/reference/cputs-cputws.md)|Dize konsola yazma|
|[_cscanf, _cwscanf](../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md), [_cscanf_s, _cscanf_s_l, _cwscanf_s, _cwscanf_s_l](../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)|Biçimlendirilmiş verileri konsoldan okuma|
|[_getch, _getwch](../c-runtime-library/reference/getch-getwch.md)|Konsoldan okuma karakteri|
|[_getche, _getwche](../c-runtime-library/reference/getch-getwch.md)|Karakter konsoldan okunan ve onu echo|
|[_inp](../c-runtime-library/inp-inpw-inpd.md)|Belirtilen g/ç bağlantı noktasından okunan bayt|
|[_inpd](../c-runtime-library/inp-inpw-inpd.md)|Belirtilen g/ç bağlantı noktasından çift sözcük okuyun|
|[_inpw](../c-runtime-library/inp-inpw-inpd.md)|Belirtilen g/ç bağlantı noktasından 2 baytlık sözcüğü okuma|
|[_kbhit](../c-runtime-library/reference/kbhit.md)|Konsolunda tuş vuruşu denetle; konsoldan okunan için denemeden önce kullanın|
|[_outp](../c-runtime-library/outp-outpw-outpd.md)|Belirtilen g/ç bağlantı noktasına bayt yazma|
|[_outpd](../c-runtime-library/outp-outpw-outpd.md)|Belirtilen g/ç bağlantı noktasına çift sözcük yazma|
|[_outpw](../c-runtime-library/outp-outpw-outpd.md)|Belirtilen g/ç bağlantı noktasına Word yazma|
|[_putch, _putwch](../c-runtime-library/reference/putch-putwch.md)|Karakter konsola yazma|
|[_ungetch, _ungetwch](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)|"Okuma sonraki karakter olacak şekilde konsoldan okunan son karakteri unget"|

## <a name="see-also"></a>Ayrıca bkz.

[Girdi ve Çıktı](../c-runtime-library/input-and-output.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
