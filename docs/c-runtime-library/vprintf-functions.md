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
ms.openlocfilehash: d63e5da79b0f78e701f3ababaf54bef41fbf88a1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418386"
---
# <a name="vprintf-functions"></a>vprintf İşlevleri
Her biri `vprintf` işlevleri bir bağımsız değişken listesi için bir işaretçi alır sonra biçimlendirir ve belirli bir hedefe verilen veri yazar. Parametre doğrulaması, olup işlevleri geniş olması veya tek baytlı karakter dizeleri, Çıkış hedefini ve parametreleri kullanılan sırası biçim dizesini belirtmek için destek işlevler farklı.  
  
|||  
|-|-|  
|[_vcprintf, _vcwprintf](../c-runtime-library/reference/vcprintf-vcprintf-l-vcwprintf-vcwprintf-l.md)|[vfprintf, vfwprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|  
|[_vfprintf_p, _vfprintf_p_l, _vfwprintf_p, _vfwprintf_p_l](../c-runtime-library/reference/vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)|[vfprintf_s, _vfprintf_s_l, vfwprintf_s, _vfwprintf_s_l](../c-runtime-library/reference/vfprintf-s-vfprintf-s-l-vfwprintf-s-vfwprintf-s-l.md)|  
|[vprintf, vwprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)|[_vprintf_p, _vprintf_p_l, _vwprintf_p, _vwprintf_p_l](../c-runtime-library/reference/vprintf-p-vprintf-p-l-vwprintf-p-vwprintf-p-l.md)|  
|[vprintf_s, _vprintf_s_l, vwprintf_s, _vwprintf_s_l](../c-runtime-library/reference/vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md)|[vsprintf, vswprintf](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)|  
|[_vsprintf_p, _vsprintf_p_l, _vswprintf_p, _vswprintf_p_l](../c-runtime-library/reference/vsprintf-p-vsprintf-p-l-vswprintf-p-vswprintf-p-l.md)|[vsprintf_s, _vsprintf_s_l, vswprintf_s, _vswprintf_s_l](../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md)|  
|[_vscprintf, _vscprintf_l, _vscwprintf, _vscwprintf_l](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|[_vsnprintf, _vsnwprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md)|  
  
## <a name="remarks"></a>Açıklamalar  
 `vprintf` İşlevleri, aşağıdaki tabloda listelendiği gibi karşılık gelen işlevleriyle benzerdir. Bununla birlikte, her `vprintf` işlevi karşılık gelen işlevlerin her biri bir bağımsız değişken listesi kabul eder ancak bir bağımsız değişken listesi için bir işaretçi kabul eder.  
  
 Bu işlevler hedeflere çıktı verilerini aşağıdaki gibi biçimlendirin.  
  
|İşlev|Karşılık gelen işlevi|Çıktı hedefi|Parametre Doğrulama|Konumsal parametre desteği|  
|--------------|--------------------------|------------------------|--------------------------|----------------------------------|  
|`_vcprintf`|[_cprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|konsolu|Null için denetleyin.|Yok|  
|`_vcwprintf`|[_cwprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|konsolu|Null için denetleyin.|Yok|  
|`vfprintf`|[fprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|*Akış*|Null için denetleyin.|Yok|  
|**vfprintf_p**|[fprintf_p](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|*Akış*|İçin null ve geçerli biçimini denetleyin.|Evet|  
|`vfprintf_s`|[fprintf_s](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|*Akış*|İçin null ve geçerli biçimini denetleyin.|Yok|  
|`vfwprintf`|[fwprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|*Akış*|Null için denetleyin.|Yok|  
|**vfwprintf_p**|[fwprintf_p](../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)|*Akış*|İçin null ve geçerli biçimini denetleyin.|Evet|  
|`vfwprintf_s`|[fwprintf_s](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|*Akış*|İçin null ve geçerli biçimini denetleyin.|Yok|  
|`vprintf`|[Printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|`Stdout`|Null için denetleyin.|Yok|  
|**vprintf_p**|[printf_p](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|`Stdout`|İçin null ve geçerli biçimini denetleyin.|Evet|  
|`vprintf_s`|[printf_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|`Stdout`|İçin null ve geçerli biçimini denetleyin.|Yok|  
|`vwprintf`|[wprintf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|`Stdout`|Null için denetleyin.|Yok|  
|**vwprintf_p**|[wprintf_p](../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)|`Stdout`|İçin null ve geçerli biçimini denetleyin.|Evet|  
|`vwprintf_s`|[wprintf_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|`Stdout`|İçin null ve geçerli biçimini denetleyin.|Yok|  
|**vsprintf**|[sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|tarafından için bellek işaret *arabellek*|Null için denetleyin.|Yok|  
|**vsprintf_p**|[sprintf_p](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|tarafından için bellek işaret *arabellek*|İçin null ve geçerli biçimini denetleyin.|Evet|  
|`vsprintf_s`|[sprintf_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|tarafından için bellek işaret *arabellek*|İçin null ve geçerli biçimini denetleyin.|Yok|  
|`vswprintf`|[swprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|tarafından için bellek işaret *arabellek*|Null için denetleyin.|Yok|  
|**vswprintf_p**|[swprintf_p](../c-runtime-library/reference/sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)|tarafından için bellek işaret *arabellek*|İçin null ve geçerli biçimini denetleyin.|Evet|  
|`vswprintf_s`|[swprintf_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|tarafından için bellek işaret *arabellek*|İçin null ve geçerli biçimini denetleyin.|Yok|  
|`_vscprintf`|[_vscprintf](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|tarafından için bellek işaret *arabellek*|Null için denetleyin.|Yok|  
|`_vscwprintf`|[_vscwprintf](../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)|tarafından için bellek işaret *arabellek*|Null için denetleyin.|Yok|  
|`_vsnprintf`|[_snprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|tarafından için bellek işaret *arabellek*|Null için denetleyin.|Yok|  
|`_vsnwprintf`|[_snwprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|tarafından için bellek işaret *arabellek*|Null için denetleyin.|Yok|  
  
 `argptr` Türüne sahip bağımsız değişken `va_list`, VARARGS tanımlanmış. H ve STDARG. H. `argptr` Değişkeni başlatıldı, tarafından **va_start,** ve sonraki tarafından yeniden `va_arg` çağırır; `argptr` işaret dönüştürülür ve karşılık gelen belirtimlerine uygun çıktı için iletilen bağımsız değişkenlerin listesini başlangıcına *biçimi* bağımsız değişkeni. *Biçim* aynı form ve olarak işlev *biçimi* bağımsız değişkeni için [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md). Bu işlevler hiçbiri çağırır `va_end`. Her daha eksiksiz bir açıklaması için `vprintf` işlev, yukarıdaki tabloda listelendiği gibi karşılık gelen işlevi açıklamasına bakın.  
  
 `_vsnprintf` farklı **vsprintf** Hayır yazar, birden fazla *sayısı* bayt *arabellek*.  
  
 Bu işlevleri sürümlerini **w** iç adı karşılık gelen işlevlerinin joker karakter sürümleri olan **w** infix; Bu joker karakter işlevlerin her  *Arabellek* ve *biçimi* joker karakter dizelerdir. Aksi takdirde, her joker karakter işlevi aynı kendi SBCS karşılık gelen çalışmasına şekilde davranır.  
  
 Bu işlevleri sürümlerini **_Yanları** ve **_p** birimlerdir daha güvenli sürümleri. Bu sürümleri biçim dizeleri doğrulama ve (örneğin, geçersiz biçimlendirme karakterlerini kullanılıyorsa) biçim dizesi doğru biçimlendirilmemiş bir özel durum oluşturur.  
  
 Bu işlevleri sürümlerini **_p** soneki Biçim dizesinde sağlanan bağımsız değişkenler yerine sırayı belirtmek için olanağı sağlar. Daha fazla bilgi için bkz: [printf_p konumsal parametreler](../c-runtime-library/printf-p-positional-parameters.md).  
  
 İçin **vsprintf**, `vswprintf`, `_vsnprintf` ve `_vsnwprintf`, kopyalama dizeleri arasında çakışma, davranışı tanımlı değil. oluşur.  
  
> [!IMPORTANT]
>  Emin *biçimi* kullanıcı tanımlı bir dize değil. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795). Bu işlevlerin güvenli sürümlerini kullanıyorsanız (ya da **_Yanları** veya **_p** sonekleri), kullanıcı tarafından sağlanan dize içeriyorsa, bir kullanıcı tarafından sağlanan biçim dizesi geçersiz parametre istisna tetikleyebilir Geçersiz biçimlendirme karakterlerini.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../c-runtime-library/stream-i-o.md)   
 [fprintf, _fprintf_l, fwprintf, _fwprintf_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [Printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va_arg, va_copy, va_end, va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)