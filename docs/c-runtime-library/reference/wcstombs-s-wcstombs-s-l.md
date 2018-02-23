---
title: wcstombs_s, _wcstombs_s_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _wcstombs_s_l
- wcstombs_s
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
f1_keywords:
- wcstombs_s
- _wcstombs_s_l
dev_langs:
- C++
helpviewer_keywords:
- wcstombs_s function
- string conversion, wide characters
- wide characters, converting
- _wcstombs_s_l function
- wcstombs_s_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 105f2d33-221a-4f6d-864c-23c1865c42af
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 863f6dc5b1c7a41145607e8f8ba83466324dac07
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="wcstombss-wcstombssl"></a>wcstombs_s, _wcstombs_s_l

Geniş bir karakter dizisi birden çok baytlı karakterler karşılık gelen bir dizi dönüştürür. Bir sürümünü [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t wcstombs_s(  
   size_t *pReturnValue,  
   char *mbstr,  
   size_t sizeInBytes,  
   const wchar_t *wcstr,  
   size_t count   
);  

errno_t _wcstombs_s_l(  
   size_t *pReturnValue,  
   char *mbstr,  
   size_t sizeInBytes,  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
);  

template <size_t size>  
errno_t wcstombs_s(  
   size_t *pReturnValue,  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count   
); // C++ only  

template <size_t size>  
errno_t _wcstombs_s_l(  
   size_t *pReturnValue,  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  

[out] *pReturnValue*  
Dönüştürülen karakter sayısı.  
  
[out] *mbstr*  
Ortaya çıkan dönüştürülmüş birden çok baytlı karakter dizesi için bir arabellek adresi.  
  
[in] *sizeInBytes*  
Bayt cinsinden boyutu *mbstr* arabellek.  
  
[in] *wcstr*  
Dönüştürülecek geniş karakter dizesi noktalarına.  
  
[in] *sayısı*  
Depolamak için bayt sayısını *mbstr* sonlandırma null karakteri içermeyen arabellek veya [_TRUNCATE](../../c-runtime-library/truncate.md).  
  
[in] *yerel ayar*  
Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  

Sıfır başarılı olursa, hatasında bir hata kodu.  
  
|Hata durumu|Dönüş değeri ve `errno`|  
|---------------------|------------------------------|  
|*mbstr* olan `NULL` ve *sizeInBytes* > 0|`EINVAL`|  
|*wcstr* olduğu `NULL`|`EINVAL`|  
|Hedef arabellek dönüştürülmüş dizeyi içeren için çok küçük. (sürece *sayısı* olan `_TRUNCATE`; açıklamalar aşağıya bakın)|`ERANGE`|  
  
Bu koşulların herhangi biri meydana gelirse, geçersiz bir parametre özel durum açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md) . Devam etmek için yürütülmesine izin veriliyorsa, bir hata kodu işlevi döndürür ve ayarlar `errno` tabloda belirtildiği şekilde.  
  
## <a name="remarks"></a>Açıklamalar  

`wcstombs_s` İşlevi dönüştürür gösterdiği geniş karakter dizesi *wcstr* gösterdiği arabellek depolanan birden çok baytlı karakterler içine *mbstr*. Bu koşullardan biri yerine getirilene kadar dönüştürme için her karakter devam eder:  
  
-   Null geniş karakter karşılaştı  
  
-   Dönüştürülemiyor geniş bir karakter ile karşılaşıldı  
  
-   Depolanan bayt sayısı *mbstr* arabellek eşittir *sayısı*.  
  
Hedef dize her zaman null (bile bir hata olması durumunda) sonlandırılır.  
  
Varsa *sayısı* özel değer [_TRUNCATE](../../c-runtime-library/truncate.md), ardından `wcstombs_s` dize olarak büyük dönüştürür hala null Sonlandırıcı yer bırakarak hedef arabelleğine sığacak. Dize kesilir dönüş değeri varsa, `STRUNCATE`, ve Dönüştürme başarılı olarak kabul edilir.  
  
Varsa `wcstombs_s` başarıyla kaynak dizesi dönüştürür dönüştürülen dizenin null Sonlandırıcı içine dahil bayt cinsinden boyutu koyar `*pReturnValue` (sağlanan *pReturnValue* değil `NULL`). Bu meydana olsa bile *mbstr* bağımsız değişkeni `NULL` ve gerekli arabellek boyutunu belirlemek için bir yol sağlar. Unutmayın *mbstr* olan `NULL`, *sayısı* göz ardı edilir.  
  
Varsa `wcstombs_s` birden çok baytlı karakter dönüştüremiyor geniş karakter karşılaştığında 0 koyar `*pReturnValue`, hedef arabelleği boş bir dize olarak ayarlar, ayarlar `errno` için `EILSEQ`ve döndürür `EILSEQ`.  
  
Dizileri gösterdiği varsa *wcstr* ve *mbstr* üst üste, davranışını `wcstombs_s` tanımlanmadı.  
  
> [!IMPORTANT]
>  Emin *wcstr* ve *mbstr* çakışmaması ve *sayısı* doğru şekilde dönüştürmek için geniş karakter sayısını yansıtır.  
  
`wcstombs_s` Geçerli yerel ayar için tüm yerel ayara bağımlı davranışı kullanır; `_wcstombs_s_l` aynıdır `wcstombs` yerine geçirilen yerel ayar kullanır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
C++'da, bu işlevler kullanılarak şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı arabellek uzunluğu otomatik olarak Infer (boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan) ve bunlar otomatik olarak yeni, güvenli dekiler ile daha eski, güvenli olmayan işlevleri değiştirebilirsiniz. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`wcstombs_s`|\<stdlib.h>|  
  
Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  

Bu programın davranışını gösterilmektedir `wcstombs_s` işlevi.  
  
```C  
// crt_wcstombs_s.c  
// This example converts a wide character  
// string to a multibyte character string.  
#include <stdio.h>  
#include <stdlib.h>  
#include <assert.h>  
  
#define BUFFER_SIZE 100  
  
int main( void )  
{  
    size_t   i;  
    char      *pMBBuffer = (char *)malloc( BUFFER_SIZE );  
    wchar_t*pWCBuffer = L"Hello, world.";  
  
    printf( "Convert wide-character string:\n" );  
  
    // Conversion  
    wcstombs_s(&i, pMBBuffer, (size_t)BUFFER_SIZE,   
               pWCBuffer, (size_t)BUFFER_SIZE );  
  
    // Output  
    printf("   Characters converted: %u\n", i);  
    printf("    Multibyte character: %s\n\n",  
     pMBBuffer );  
  
    // Free multibyte character buffer  
    if (pMBBuffer)  
    {  
    free(pMBBuffer);  
    }  
}  
```  
  
```Output  
Convert wide-character string:  
   Characters converted: 14  
    Multibyte character: Hello, world.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
[Yerel ayar](../../c-runtime-library/locale.md)   
[_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
[mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
[mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
[wctomb_s, _wctomb_s_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)   
[WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)