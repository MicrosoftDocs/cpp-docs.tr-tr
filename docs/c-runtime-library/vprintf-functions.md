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
ms.openlocfilehash: 2455655404bd61c220ebe4e3d018bc81204fa51e
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845373"
---
# <a name="vprintf-functions"></a>vprintf İşlevleri

İşlevlerin her biri `vprintf` bağımsız değişken listesi için bir işaretçi alır, sonra verili verileri biçimlendirir ve belirli bir hedefe yazar. İşlevler, işlevlerin geniş veya tek baytlık karakter dizeleri, çıkış hedefi ve parametrelerin biçim dizesinde kullanılacağı sırayı belirtme desteği gibi gerçekleştirilen parametre doğrulamasında farklılık gösterir.

[_vcprintf, _vcwprintf](../c-runtime-library/reference/vcprintf-vcprintf-l-vcwprintf-vcwprintf-l.md)\
[vfprintf, vfwprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)\
[_vfprintf_p, _vfprintf_p_l, _vfwprintf_p, _vfwprintf_p_l](../c-runtime-library/reference/vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)\
[vfprintf_s, _vfprintf_s_l, vfwprintf_s, _vfwprintf_s_l](../c-runtime-library/reference/vfprintf-s-vfprintf-s-l-vfwprintf-s-vfwprintf-s-l.md)\
[vprintf, öprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)\
[_vprintf_p, _vprintf_p_l, _vwprintf_p, _vwprintf_p_l](../c-runtime-library/reference/vprintf-p-vprintf-p-l-vwprintf-p-vwprintf-p-l.md)\
[vprintf_s, _vprintf_s_l, vwprintf_s, _vwprintf_s_l](../c-runtime-library/reference/vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md)\
[_vscprintf, _vscprintf_l, _vscwprintf, _vscwprintf_l](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)\
[_vsnprintf, _vsnwprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md) 
 [vsprıntf, vswprintf](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)\
[_vsprintf_p, _vsprintf_p_l, _vswprintf_p, _vswprintf_p_l](../c-runtime-library/reference/vsprintf-p-vsprintf-p-l-vswprintf-p-vswprintf-p-l.md)\
[vsprintf_s, _vsprintf_s_l, vswprintf_s, _vswprintf_s_l](../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md)

## <a name="remarks"></a>Açıklamalar

`vprintf`İşlevler, aşağıdaki tabloda listelendiği gibi karşılık gelen işlevlere benzerdir. Ancak her `vprintf` işlev bir bağımsız değişken listesi için bir işaretçi kabul eder, ancak her bir karşılık gelen işlevler bir bağımsız değişken listesini kabul eder.

Bu işlevler, hedeflere yönelik verileri aşağıdaki gibi biçimlendirir.

|İşlev|Karşılığı işlevi|Çıkış hedefi|Parametre Doğrulama|Konumsal parametre desteği|
|--------------|--------------------------|------------------------|--------------------------|----------------------------------|
|`_vcprintf`|[_cprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|console|Null denetimi yapın.|hayır|
|`_vcwprintf`|[_cwprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|console|Null denetimi yapın.|hayır|
|`vfprintf`|[fprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|*Akış*|Null denetimi yapın.|hayır|
|**vfprintf_p**|[fprintf_p](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|*Akış*|Null ve geçerli biçimi denetleyin.|evet|
|`vfprintf_s`|[fprintf_s](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|*Akış*|Null ve geçerli biçimi denetleyin.|hayır|
|`vfwprintf`|[fwprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|*Akış*|Null denetimi yapın.|hayır|
|**vfwprintf_p**|[fwprintf_p](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|*Akış*|Null ve geçerli biçimi denetleyin.|evet|
|`vfwprintf_s`|[fwprintf_s](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|*Akış*|Null ve geçerli biçimi denetleyin.|hayır|
|`vprintf`|[printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|`Stdout`|Null denetimi yapın.|hayır|
|**vprintf_p**|[printf_p](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|`Stdout`|Null ve geçerli biçimi denetleyin.|evet|
|`vprintf_s`|[printf_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|`Stdout`|Null ve geçerli biçimi denetleyin.|hayır|
|`vwprintf`|[wprintf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|`Stdout`|Null denetimi yapın.|hayır|
|**vwprintf_p**|[wprintf_p](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|`Stdout`|Null ve geçerli biçimi denetleyin.|evet|
|`vwprintf_s`|[wprintf_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|`Stdout`|Null ve geçerli biçimi denetleyin.|hayır|
|**vsprıntf**|[sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|*arabelleğe* göre işaret edilen bellek|Null denetimi yapın.|hayır|
|**vsprintf_p**|[sprintf_p](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|*arabelleğe* göre işaret edilen bellek|Null ve geçerli biçimi denetleyin.|evet|
|`vsprintf_s`|[sprintf_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|*arabelleğe* göre işaret edilen bellek|Null ve geçerli biçimi denetleyin.|hayır|
|`vswprintf`|[swprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|*arabelleğe* göre işaret edilen bellek|Null denetimi yapın.|hayır|
|**vswprintf_p**|[swprintf_p](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|*arabelleğe* göre işaret edilen bellek|Null ve geçerli biçimi denetleyin.|evet|
|`vswprintf_s`|[swprintf_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|*arabelleğe* göre işaret edilen bellek|Null ve geçerli biçimi denetleyin.|hayır|
|`_vscprintf`|[_vscprintf](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|*arabelleğe* göre işaret edilen bellek|Null denetimi yapın.|hayır|
|`_vscwprintf`|[_vscwprintf](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|*arabelleğe* göre işaret edilen bellek|Null denetimi yapın.|hayır|
|`_vsnprintf`|[_snprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|*arabelleğe* göre işaret edilen bellek|Null denetimi yapın.|hayır|
|`_vsnwprintf`|[_snwprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|*arabelleğe* göre işaret edilen bellek|Null denetimi yapın.|hayır|

`argptr`Bağımsız değişkeni `va_list` , VARARGS içinde tanımlanan, türündedir. H ve STDARG. Olsun. `argptr`Değişken **va_start** tarafından başlatılmalıdır ve sonraki çağrılar tarafından `va_arg` yeniden başlatılabilir; ardından, `argptr` *Biçim* bağımsız değişkeninde karşılık gelen belirtimlere göre, çıkış için dönüştürülen ve aktarılan bağımsız değişkenlerin listesinin başlangıcına işaret eder. *Biçim* , [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)için *Biçim* bağımsız değişkeniyle aynı form ve işleve sahiptir. Bu işlevlerden hiçbiri çağırmaktadır `va_end` . Her bir işlevin daha ayrıntılı bir açıklaması için `vprintf` , önceki tabloda listelenen karşılık gelen işlevinin açıklamasına bakın.

`_vsnprintf`, 10.000'den **INTF** öğesinden, *arabelleğe* *Count* bayttan fazlasını yazmadığından farklıdır.

Bu işlevlerin adı içindeki **w** /düzeltmesini içeren sürümleri, ilgili işlevlerin **w** ındüzeltmesini içermeyen geniş karakterli sürümleridir; Bu geniş karakter işlevlerinin her birinde, *arabellek* ve *Biçim* geniş karakterli dizelerdir. Aksi halde, her geniş karakter işlevi, SBCS karşılık gelen işleviyle aynı şekilde davranır.

**_S** ve **_p** son eklerine sahip bu işlevlerin sürümleri, daha güvenli sürümleridir. Bu sürümler biçim dizelerini doğrular ve biçim dizesi düzgün biçimlendirilmediyse (örneğin, geçersiz biçimlendirme karakterleri kullanılıyorsa) bir özel durum oluşturur.

**_P** sonekine sahip bu işlevlerin sürümleri, sağlanan bağımsız değişkenlerin biçim dizesinde yerine geçen sırayı belirtme olanağı sağlar. Daha fazla bilgi için bkz. [Printf_p Konumsal parametreler](../c-runtime-library/printf-p-positional-parameters.md).

**Vsprintf**için `vswprintf` `_vsnprintf` ve `_vsnwprintf` Çakışan dizeler arasında kopyalama gerçekleşirse, davranış tanımsızdır.

> [!IMPORTANT]
> *Biçimin* Kullanıcı tanımlı bir dize olmadığından emin olun. Daha fazla bilgi için bkz. [arabellek taşmalarını önleme](/windows/win32/SecBP/avoiding-buffer-overruns). Bu işlevlerin güvenli sürümlerini ( **_s** veya **_p** sonekleri) kullanıyorsanız, Kullanıcı tarafından sağlanan dize geçersiz biçimlendirme karakterleri içeriyorsa, Kullanıcı tarafından sağlanan bir biçim dizesi geçersiz bir parametre özel durumu tetikleyebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Akış G/Ç](../c-runtime-library/stream-i-o.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \_ _swprintf_l](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg, va_copy, va_end, va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)
