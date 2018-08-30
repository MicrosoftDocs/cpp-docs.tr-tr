---
title: vprintf işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apilocation:
- msvcr110.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr80.dll
apitype: DLLExport
f1_keywords:
- vprintf
dev_langs:
- C++
helpviewer_keywords:
- vprintf function
- formatted text [C++]
ms.assetid: 02ac7c51-eab1-4bf0-bf4c-77065e3fa744
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 127cf8683d4d2627bdc19bef4a9ddfa93e3d7387
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43216940"
---
# <a name="vprintf-functions"></a>vprintf İşlevleri
Her biri `vprintf` işlevleri bir bağımsız değişken listesi için bir işaretçi alır sonra biçimlendirir ve verilen verileri belirli bir hedefe yazar. Parametre doğrulaması, mi işlevleri geniş olması veya tek baytlı karakter dizelerini, Çıkış hedefini ve biçim dizesindeki parametreleri kullanılan sırayı belirtme desteği işlevleri farklı.  
  
|||  
|-|-|  
|[_vcprintf, _vcwprintf](../c-runtime-library/reference/vcprintf-vcprintf-l-vcwprintf-vcwprintf-l.md)|[vfprintf, vfwprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|  
|[_vfprintf_p, _vfprintf_p_l, _vfwprintf_p, _vfwprintf_p_l](../c-runtime-library/reference/vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)|[vfprintf_s, _vfprintf_s_l, vfwprintf_s, _vfwprintf_s_l](../c-runtime-library/reference/vfprintf-s-vfprintf-s-l-vfwprintf-s-vfwprintf-s-l.md)|  
|[vprintf, vwprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)|[_vprintf_p, _vprintf_p_l, _vwprintf_p, _vwprintf_p_l](../c-runtime-library/reference/vprintf-p-vprintf-p-l-vwprintf-p-vwprintf-p-l.md)|  
|[vprintf_s, _vprintf_s_l, vwprintf_s, _vwprintf_s_l](../c-runtime-library/reference/vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md)|[vsprintf, vswprintf](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)|  
|[_vsprintf_p, _vsprintf_p_l, _vswprintf_p, _vswprintf_p_l](../c-runtime-library/reference/vsprintf-p-vsprintf-p-l-vswprintf-p-vswprintf-p-l.md)|[vsprintf_s, _vsprintf_s_l, vswprintf_s, _vswprintf_s_l](../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md)|  
|[_vscprintf, _vscprintf_l, _vscwprintf, _vscwprintf_l](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|[_vsnprintf, _vsnwprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md)|  
  
## <a name="remarks"></a>Açıklamalar  
 `vprintf` İşlevleri, aşağıdaki tabloda listelenen karşılık gelen işlevlerini benzerdir. Ancak, her `vprintf` işlevi karşılığı işlevlerin her biri bir bağımsız değişken listesini kabul eder ancak bir bağımsız değişken listesi için bir işaretçi kabul eder.  
  
 Bu işlevler hedefleri için çıktı verilerini aşağıdaki gibi biçimlendirin.  
  
|İşlev|Karşılık gelen işlevi|Çıktı hedefi|Parametre Doğrulama|Konumsal parametresi desteği|  
|--------------|--------------------------|------------------------|--------------------------|----------------------------------|  
|`_vcprintf`|[_cprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|konsolu|Null denetimi.|Yok|  
|`_vcwprintf`|[_cwprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|konsolu|Null denetimi.|Yok|  
|`vfprintf`|[fprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|*Akış*|Null denetimi.|Yok|  
|**vfprintf_p**|[fprintf_p](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|*Akış*|İçin null ve geçerli biçimini denetleyin.|Evet|  
|`vfprintf_s`|[fprintf_s](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|*Akış*|İçin null ve geçerli biçimini denetleyin.|Yok|  
|`vfwprintf`|[fwprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|*Akış*|Null denetimi.|Yok|  
|**vfwprintf_p**|[fwprintf_p](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|*Akış*|İçin null ve geçerli biçimini denetleyin.|Evet|  
|`vfwprintf_s`|[fwprintf_s](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|*Akış*|İçin null ve geçerli biçimini denetleyin.|Yok|  
|`vprintf`|[Printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|`Stdout`|Null denetimi.|Yok|  
|**vprintf_p**|[printf_p](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|`Stdout`|İçin null ve geçerli biçimini denetleyin.|Evet|  
|`vprintf_s`|[printf_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|`Stdout`|İçin null ve geçerli biçimini denetleyin.|Yok|  
|`vwprintf`|[wprintf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|`Stdout`|Null denetimi.|Yok|  
|**vwprintf_p**|[wprintf_p](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|`Stdout`|İçin null ve geçerli biçimini denetleyin.|Evet|  
|`vwprintf_s`|[wprintf_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|`Stdout`|İçin null ve geçerli biçimini denetleyin.|Yok|  
|**vsprintf**|[sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|bellek tarafından işaret edilen *arabelleği*|Null denetimi.|Yok|  
|**vsprintf_p**|[sprintf_p](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|bellek tarafından işaret edilen *arabelleği*|İçin null ve geçerli biçimini denetleyin.|Evet|  
|`vsprintf_s`|[sprintf_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|bellek tarafından işaret edilen *arabelleği*|İçin null ve geçerli biçimini denetleyin.|Yok|  
|`vswprintf`|[swprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|bellek tarafından işaret edilen *arabelleği*|Null denetimi.|Yok|  
|**vswprintf_p**|[swprintf_p](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|bellek tarafından işaret edilen *arabelleği*|İçin null ve geçerli biçimini denetleyin.|Evet|  
|`vswprintf_s`|[swprintf_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|bellek tarafından işaret edilen *arabelleği*|İçin null ve geçerli biçimini denetleyin.|Yok|  
|`_vscprintf`|[_vscprintf](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|bellek tarafından işaret edilen *arabelleği*|Null denetimi.|Yok|  
|`_vscwprintf`|[_vscwprintf](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|bellek tarafından işaret edilen *arabelleği*|Null denetimi.|Yok|  
|`_vsnprintf`|[_snprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|bellek tarafından işaret edilen *arabelleği*|Null denetimi.|Yok|  
|`_vsnwprintf`|[_snwprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|bellek tarafından işaret edilen *arabelleği*|Null denetimi.|Yok|  
  
 `argptr` Bağımsız değişken türüne sahip `va_list`, VARARG'LARDA tanımlanır. H ve STDARG. H `argptr` Değişkeni başlatılır, tarafından **va_start** ve sonraki tarafından yeniden `va_arg` çağırır; `argptr` işaret dönüştürülür ve karşılık gelen özelliklere göre çıkışı için iletilen bağımsız değişken listesinde başlangıcına *biçimi* bağımsız değişken. *Biçim* aynı forma ve işleve sahiptir *biçimi* için bağımsız değişken [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md). Bu işlevlerden hiçbiri çağırır `va_end`. Her daha eksiksiz bir açıklaması için `vprintf` işlev, yukarıdaki tabloda listelenen karşılık gelen işlevini açıklamasına bakın.  
  
 `_vsnprintf` farklıdır **vsprintf** Hayır yazar, birden fazla *sayısı* bayt *arabellek*.  
  
 Sahip bu işlevlerin sürümleri **w** içtakı adında olduğu geniş karakter sürümleri olmayan ilgili işlevlerle **w** infix; her birinde Bu geniş karakter işlevleri  *Arabellek* ve *biçimi* geniş karakterli dizelerdir. Aksi takdirde, her bir geniş karakter işlevi, kendi SBCS karşılığı çalışmasına aynı şekilde davranır.  
  
 Sahip bu işlevlerin sürümleri **_Yanları** ve **_p** birimlerdir daha güvenli sürümleri. Bu sürümler biçim dizeleri doğrulama ve (örneğin, geçersiz biçim karakterleri kullanılması durumunda) bir biçim dizesi düzgün biçimlendirilmemiş bir özel durum oluşturur.  
  
 Sahip bu işlevlerin sürümleri **_p** soneki Biçim dizesinde sağlanan bağımsız değişkenler yerine sırayı belirleme olanağı sağlar. Daha fazla bilgi için [printf_p konumsal parametreler](../c-runtime-library/printf-p-positional-parameters.md).  
  
 İçin **vsprintf**, `vswprintf`, `_vsnprintf` ve `_vsnwprintf`, kopyalama dizeler arasında çakışma davranışı tanımsız hale gelmesini oluşur.  
  
> [!IMPORTANT]
>  Emin *biçimi* kullanıcı tanımlı bir dize değil. Daha fazla bilgi için [arabellek taşmalarını](/windows/desktop/SecBP/avoiding-buffer-overruns). Bu işlevlerin güvenli sürümleri kullanıyorsanız (ya da **_Yanları** veya **_p** sonekleri), kullanıcı tarafından sağlanan dize içeriyorsa, bir kullanıcı tarafından sağlanan biçim dizesi geçersiz parametre özel durum tetikleyebilir geçersiz biçim karakterleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Stream g/ç](../c-runtime-library/stream-i-o.md)   
 [fprintf _fprintf_l, fwprintf, _fwprintf_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [Printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va_arg, va_copy, va_end, va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)