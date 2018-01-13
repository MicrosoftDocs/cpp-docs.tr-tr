---
title: wcsrtombs_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: wcsrtombs_s
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords: wcsrtombs_s
dev_langs: C++
helpviewer_keywords:
- string conversion, wide characters
- wcsrtombs_s function
- wide characters, strings
ms.assetid: 9dccb766-113c-44bb-9b04-07a634dddec8
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 025acdf18d0e5322ef43de800e3577233a93cb86
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="wcsrtombss"></a>wcsrtombs_s
Geniş karakter dizesi, birden çok baytlı karakter dizesi gösterimine dönüştürür. Bir sürümünü [wcsrtombs](../../c-runtime-library/reference/wcsrtombs.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t wcsrtombs_s(  
   size_t *pReturnValue,  
   char *mbstr,  
   size_t sizeInBytes,  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
);  
template <size_t size>  
errno_t wcsrtombs_s(  
   size_t *pReturnValue,  
   char (&mbstr)[size],  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  
 [out]`pReturnValue`  
 Dönüştürülen karakter sayısı.  
  
 [out]`mbstr`  
 Ortaya çıkan dönüştürülmüş birden çok baytlı karakter dizesi için bir arabellek adresi.  
  
 [out]`sizeInBytes`  
 Bayt cinsinden boyutu `mbstr` arabellek.  
  
 [in]`wcstr`  
 Dönüştürülecek geniş karakter dizesi noktalarına.  
  
 [in]`count`  
 Depolanmasına bayt sayısını `mbstr` arabellek veya [_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 [in]`mbstate`  
 Bir işaretçi bir `mbstate_t` dönüştürme durum nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sıfır başarılı olursa, hatasında bir hata kodu.  
  
|Hata durumu|Dönüş değeri ve`errno`|  
|---------------------|------------------------------|  
|`mbstr`olan `NULL` ve `sizeInBytes` > 0|`EINVAL`|  
|`wcstr`değil`NULL`|`EINVAL`|  
|Hedef arabellek dönüştürülmüş dizeyi içeren için çok küçük. (sürece `count` olan `_TRUNCATE`; açıklamalar aşağıya bakın)|`ERANGE`|  
  
 Bu koşulların herhangi biri meydana gelirse, geçersiz bir parametre özel durum açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md) . Devam etmek için yürütülmesine izin veriliyorsa, bir hata kodu işlevi döndürür ve ayarlar `errno` tabloda belirtildiği şekilde.  
  
## <a name="remarks"></a>Açıklamalar  
 `wcsrtombs_s` İşlevi dönüştürür gösterdiği geniş karakter dizesi `wcstr` gösterdiği arabellek depolanan birden çok baytlı karakterler içine `mbstr`, bulunan dönüştürme durumunu kullanarak `mbstate`. Bu koşullardan biri yerine getirilene kadar dönüştürme için her karakter devam eder:  
  
-   Null geniş karakter karşılaştı  
  
-   Dönüştürülemiyor geniş bir karakter ile karşılaşıldı  
  
-   Depolanan bayt sayısı `mbstr` arabellek eşittir `count`.  
  
 Hedef dize her zaman null (bile bir hata olması durumunda) sonlandırılır.  
  
 Varsa `count` özel değer [_TRUNCATE](../../c-runtime-library/truncate.md), ardından `wcsrtombs_s` dize olarak büyük dönüştürür hala null Sonlandırıcı yer bırakarak hedef arabelleğine sığacak.  
  
 Varsa `wcsrtombs_s` başarıyla kaynak dizesi dönüştürür dönüştürülen dizenin null Sonlandırıcı içine dahil bayt cinsinden boyutu koyar `*pReturnValue` (sağlanan `pReturnValue` değil `NULL`). Bu meydana olsa bile `mbstr` bağımsız değişkeni `NULL` ve gerekli arabellek boyutunu belirlemek için bir yol sağlar. Unutmayın `mbstr` olan `NULL`, `count` göz ardı edilir.  
  
 Varsa `wcsrtombs_s` birden çok baytlı karakter dönüştüremiyor geniş karakter karşılaştığında -1 koyar `*pReturnValue`, hedef arabelleği boş bir dize olarak ayarlar, ayarlar `errno` için `EILSEQ`ve döndürür `EILSEQ`.  
  
 Dizileri gösterdiği varsa `wcstr` ve `mbstr` üst üste, davranışını `wcsrtombs_s` tanımlanmadı. `wcsrtombs_s`Geçerli yerel LC_TYPE kategoriye göre etkilenir.  
  
> [!IMPORTANT]
>  Emin `wcstr` ve `mbstr` çakışmaması ve `count` doğru şekilde dönüştürmek için geniş karakter sayısını yansıtır.  
  
 `wcsrtombs_s` İşlevi farklı olarak [wcstombs_s, _wcstombs_s_l](../../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md) kendi restartability tarafından. Dönüştürme durumu depolanan `mbstate` sonraki çağrılar aynı ya da yeniden başlatılabilir diğer işlevleri için. Sonuçlar, yeniden başlatılabilir ve nonrestartable işlevleri kullanımını kullanırken tanımlanmamış. Örneğin, bir uygulama kullanırsınız `wcsrlen` yerine `wcslen`, bir sonraki çağrı, `wcsrtombs_s` yerine kullanıldı`wcstombs_s.`  
  
 C++'da, bu işlevler kullanılarak şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı arabellek uzunluğu otomatik olarak Infer (boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan) ve bunlar otomatik olarak yeni, güvenli dekiler ile daha eski, güvenli olmayan işlevleri değiştirebilirsiniz. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="exceptions"></a>Özel Durumlar  
 `wcsrtombs_s` İşlevi, geçerli iş parçacığının hiçbir işlev çağrıları sürece çoklu iş parçacığı güvenli olduğu `setlocale` bu işlev yürütülürken ve `mbstate` null.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_wcsrtombs_s.cpp  
//   
// This code example converts a wide  
// character string into a multibyte  
// character string.  
//  
  
#include <stdio.h>  
#include <memory.h>  
#include <wchar.h>  
#include <errno.h>  
  
#define MB_BUFFER_SIZE 100  
  
void main()  
{  
    const wchar_t   wcString[] =   
                    {L"Every good boy does fine."};  
    const wchar_t   *wcsIndirectString = wcString;  
    char            mbString[MB_BUFFER_SIZE];  
    size_t          countConverted;  
    errno_t         err;  
    mbstate_t       mbstate;  
  
    // Reset to initial shift state  
    ::memset((void*)&mbstate, 0, sizeof(mbstate));  
  
    err = wcsrtombs_s(&countConverted, mbString, MB_BUFFER_SIZE,  
                      &wcsIndirectString, MB_BUFFER_SIZE, &mbstate);  
    if (err == EILSEQ)  
    {  
        printf( "An encoding error was detected in the string.\n" );  
    }  
    else   
    {  
        printf( "The string was successfully converted.\n" );  
    }  
}  
```  
  
```Output  
The string was successfully converted.  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`wcsrtombs_s`|\<wchar.h >|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [Çok baytlı karakter sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb_s](../../c-runtime-library/reference/wcrtomb-s.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)