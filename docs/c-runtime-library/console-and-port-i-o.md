---
title: Konsol ve Bağlantı Noktası G/Ç
ms.date: 11/04/2016
helpviewer_keywords:
- routines, console and port I/O
- routines
- ports, I/O routines
- I/O [CRT], console
- I/O [CRT], port
- I/O routines, console and port I/O
ms.assetid: 0eee1c92-9b3d-41e0-a43a-257e546eeec8
ms.openlocfilehash: 5b4dc2a081ea11bd84d932f55b5b247de81f296a
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443454"
---
# <a name="console-and-port-io"></a>Konsol ve Bağlantı Noktası G/Ç

Bu yordamlar, konsolunuza veya belirtilen bağlantı noktasında okur ve yazar. Konsol g/ç yordamları, akış g/ç veya alt düzey g/ç kitaplığı yordamları ile uyumlu değildir. G/ç gerçekleştirilmeden önce konsolun veya bağlantı noktasının açılması veya kapatılması gerekmez, bu nedenle bu kategoride açık veya kapalı bir yordam yoktur. Windows işletim sistemlerinde, bu işlevlerin çıktısı her zaman konsola yönlendirilir ve yeniden yönlendirilemez.

## <a name="console-and-port-io-routines"></a>Konsol ve bağlantı noktası g/ç yordamları

|Yordam|Kullanım|
|-------------|---------|
|[_cgets, _cgetws](../c-runtime-library/cgets-cgetws.md), [_cgets_s, _cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md)|Konsoldan dize oku|
|[_cprintf, _cwprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md), [_cprintf_s, _cprintf_s_l, _cwprintf_s, _cwprintf_s_l](../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)|Biçimli verileri konsola yaz|
|[_cputs](../c-runtime-library/reference/cputs-cputws.md)|Dizeyi konsola yaz|
|[_cscanf, _cwscanf](../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md), [_cscanf_s, _cscanf_s_l, _cwscanf_s, _cwscanf_s_l](../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)|Konsoldan biçimlendirilen verileri oku|
|[_getch, _getwch](../c-runtime-library/reference/getch-getwch.md)|Konsoldan karakter oku|
|[_getche, _getwche](../c-runtime-library/reference/getch-getwch.md)|Konsolundan karakter oku ve yankıyı|
|[_inp](../c-runtime-library/inp-inpw-inpd.md)|Belirtilen g/ç bağlantı noktasından bir bayt oku|
|[_inpd](../c-runtime-library/inp-inpw-inpd.md)|Belirtilen g/ç bağlantı noktasından çift sözcük oku|
|[_inpw](../c-runtime-library/inp-inpw-inpd.md)|Belirtilen g/ç bağlantı noktasından 2 baytlık kelimeyi oku|
|[_kbhit](../c-runtime-library/reference/kbhit.md)|Konsolda tuş vuruşunu denetle; konsolundan okumayı denemeden önce kullanın|
|[_outp](../c-runtime-library/outp-outpw-outpd.md)|Belirtilen g/ç bağlantı noktasına bir bayt yazın|
|[_outpd](../c-runtime-library/outp-outpw-outpd.md)|Belirtilen g/ç bağlantı noktasına çift sözcük yaz|
|[_outpw](../c-runtime-library/outp-outpw-outpd.md)|Kelimeyi belirtilen g/ç bağlantı noktasına yaz|
|[_putch, _putwch](../c-runtime-library/reference/putch-putwch.md)|Konsola karakter yaz|
|[_ungetch, _ungetwch](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)|Sonraki karakter okunabilmesi için konsoldan "geri al" son karakteri okundu|

## <a name="see-also"></a>Ayrıca bkz.

[Girdi ve Çıktı](../c-runtime-library/input-and-output.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
