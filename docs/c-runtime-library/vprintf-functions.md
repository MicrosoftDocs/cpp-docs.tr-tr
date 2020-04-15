---
title: vprintf İşlevleri
ms.date: 11/04/2016
api_location:
- msvcr110.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr80.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- vprintf
helpviewer_keywords:
- vprintf function
- formatted text [C++]
ms.assetid: 02ac7c51-eab1-4bf0-bf4c-77065e3fa744
ms.openlocfilehash: db4927e983a27110e587dacd9acf909f0c735b87
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365671"
---
# <a name="vprintf-functions"></a>vprintf İşlevleri

`vprintf` İşlevlerin her biri bir bağımsız değişken listesine bir işaretçi alır, ardından belirli bir hedefe verilen verileri biçimlendirin ve yazar. İşlevler geniş veya tek bayt karakter dizeleri, çıkış hedefi ve biçim dizesinde parametrelerin hangi sırayı kullanılacağını belirtmek için destek alıp almadığı, gerçekleştirilen parametre doğrulamasında farklılık gösterir.

|||
|-|-|
|[_vcprintf, _vcwprintf](../c-runtime-library/reference/vcprintf-vcprintf-l-vcwprintf-vcwprintf-l.md)|[vfprintf, vfwprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|
|[_vfprintf_p, _vfprintf_p_l, _vfwprintf_p, _vfwprintf_p_l](../c-runtime-library/reference/vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)|[vfprintf_s, _vfprintf_s_l, vfwprintf_s, _vfwprintf_s_l](../c-runtime-library/reference/vfprintf-s-vfprintf-s-l-vfwprintf-s-vfwprintf-s-l.md)|
|[vprintf, vwprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)|[_vprintf_p, _vprintf_p_l, _vwprintf_p, _vwprintf_p_l](../c-runtime-library/reference/vprintf-p-vprintf-p-l-vwprintf-p-vwprintf-p-l.md)|
|[vprintf_s, _vprintf_s_l, vwprintf_s, _vwprintf_s_l](../c-runtime-library/reference/vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md)|[vsprintf, vswprintf](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)|
|[_vsprintf_p, _vsprintf_p_l, _vswprintf_p, _vswprintf_p_l](../c-runtime-library/reference/vsprintf-p-vsprintf-p-l-vswprintf-p-vswprintf-p-l.md)|[vsprintf_s, _vsprintf_s_l, vswprintf_s, _vswprintf_s_l](../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md)|
|[_vscprintf, _vscprintf_l, _vscwprintf, _vscwprintf_l](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|[_vsnprintf, _vsnwprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md)|

## <a name="remarks"></a>Açıklamalar

İşlevler, `vprintf` aşağıdaki tabloda listelenen muadili işlevlere benzer. Ancak, `vprintf` her işlev bir bağımsız değişken listesi için işaretçi kabul ederken, karşıt işlevlerin her biri bir bağımsız değişken listesi kabul eder.

Bu işlevler, çıkış için verileri hedeflere aşağıdaki gibi biçimlendirin.

|İşlev|Muadili fonksiyon|Çıkış hedefi|Parametre Doğrulama|Konumsal Parametre Desteği|
|--------------|--------------------------|------------------------|--------------------------|----------------------------------|
|`_vcprintf`|[_cprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|console|Null'u kontrol et.|hayır|
|`_vcwprintf`|[_cwprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|console|Null'u kontrol et.|hayır|
|`vfprintf`|[Fprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|*Akış*|Null'u kontrol et.|hayır|
|**vfprintf_p**|[fprintf_p](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|*Akış*|Null ve geçerli biçimi denetleyin.|evet|
|`vfprintf_s`|[fprintf_s](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|*Akış*|Null ve geçerli biçimi denetleyin.|hayır|
|`vfwprintf`|[fwprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|*Akış*|Null'u kontrol et.|hayır|
|**vfwprintf_p**|[fwprintf_p](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|*Akış*|Null ve geçerli biçimi denetleyin.|evet|
|`vfwprintf_s`|[fwprintf_s](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|*Akış*|Null ve geçerli biçimi denetleyin.|hayır|
|`vprintf`|[Printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|`Stdout`|Null'u kontrol et.|hayır|
|**vprintf_p**|[printf_p](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|`Stdout`|Null ve geçerli biçimi denetleyin.|evet|
|`vprintf_s`|[Printf_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|`Stdout`|Null ve geçerli biçimi denetleyin.|hayır|
|`vwprintf`|[Wprintf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|`Stdout`|Null'u kontrol et.|hayır|
|**vwprintf_p**|[wprintf_p](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|`Stdout`|Null ve geçerli biçimi denetleyin.|evet|
|`vwprintf_s`|[wprintf_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|`Stdout`|Null ve geçerli biçimi denetleyin.|hayır|
|**vsprintf**|[Sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|*arabellek* tarafından işaret edilen bellek|Null'u kontrol et.|hayır|
|**vsprintf_p**|[sprintf_p](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|*arabellek* tarafından işaret edilen bellek|Null ve geçerli biçimi denetleyin.|evet|
|`vsprintf_s`|[Sprintf_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|*arabellek* tarafından işaret edilen bellek|Null ve geçerli biçimi denetleyin.|hayır|
|`vswprintf`|[swprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|*arabellek* tarafından işaret edilen bellek|Null'u kontrol et.|hayır|
|**vswprintf_p**|[swprintf_p](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|*arabellek* tarafından işaret edilen bellek|Null ve geçerli biçimi denetleyin.|evet|
|`vswprintf_s`|[swprintf_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|*arabellek* tarafından işaret edilen bellek|Null ve geçerli biçimi denetleyin.|hayır|
|`_vscprintf`|[_vscprintf](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|*arabellek* tarafından işaret edilen bellek|Null'u kontrol et.|hayır|
|`_vscwprintf`|[_vscwprintf](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|*arabellek* tarafından işaret edilen bellek|Null'u kontrol et.|hayır|
|`_vsnprintf`|[_snprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|*arabellek* tarafından işaret edilen bellek|Null'u kontrol et.|hayır|
|`_vsnwprintf`|[_snwprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|*arabellek* tarafından işaret edilen bellek|Null'u kontrol et.|hayır|

Bağımsız `argptr` değişken, `va_list`VARARGS'da tanımlanan türü vardır. H ve STDARG. H. Değişken **va_start** tarafından başharfe alınmalıdır ve sonraki `va_arg` çağrılar tarafından yeniden başlatılması gerekebilir; `argptr` `argptr` sonra, biçim bağımsız *değişkenindeki* ilgili belirtimlere göre dönüştürülen ve çıktı için aktarılan bağımsız değişkenler listesinin başına işaret eder. *format* [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)için biçim bağımsız *değişkeni* ile aynı biçim ve işleve sahiptir. Bu işlevlerin hiçbiri `va_end`çağırır. Her `vprintf` işlevin daha eksiksiz bir açıklaması için, önceki tabloda listelenen muadili işlevinin açıklamasına bakın.

`_vsnprintf`arabellek için *sayma* bayt daha fazla yazar bu *buffer* **vsprintf** farklıdır.

Bu işlevlerin adı w **infix** ile sürümleri **w** infix olmadan ilgili işlevlerin geniş karakter sürümleri; bu geniş karakterli işlevlerin her birinde, *arabellek* ve *biçim* geniş karakterdizeleridir. Aksi takdirde, her geniş karakterli işlev, SBCS muadili işleviyle aynı şekilde çalışır.

Bu işlevlerin **_s** ve **_p** sonekli sürümleri daha güvenli sürümlerdir. Bu sürümler biçim dizeleri doğrular ve biçim dizesi iyi oluşturulmazsa (örneğin, geçersiz biçimlendirme karakterleri kullanılıyorsa) bir özel durum oluşturur.

Bu işlevlerin **_p** soneki olan sürümleri, sağlanan bağımsız değişkenlerin biçim dizesinde değiştirildiği sırayı belirtme olanağı sağlar. Daha fazla bilgi için [printf_p Konumsal Parametrelere](../c-runtime-library/printf-p-positional-parameters.md)bakın.

**vsprintf**için `vswprintf` `_vsnprintf` , `_vsnwprintf`ve , kopyalama çakışan dizeleri arasında oluşursa, davranış tanımsız.

> [!IMPORTANT]
> *Biçimin* kullanıcı tanımlı bir dize olmadığından emin olun. Daha fazla bilgi için [bkz.](/windows/win32/SecBP/avoiding-buffer-overruns) Bu işlevlerin **(_s** veya **_p** soneklerinin güvenli sürümlerini kullanıyorsanız), kullanıcı tarafından sağlanan bir biçim dizesi geçersiz biçimlendirme karakterleri içeriyorsa geçersiz bir parametre özel durumu tetikleyebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Akış I/O](../c-runtime-library/stream-i-o.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, \__swprintf_l, _swprintf_l](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg, va_copy, va_end, va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)
