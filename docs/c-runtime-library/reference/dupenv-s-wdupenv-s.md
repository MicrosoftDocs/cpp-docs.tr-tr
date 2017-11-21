---
title: _dupenv_s, _wdupenv_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _dupenv_s
- _wdupenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- tdupenv_s
- _dupenv_s
- wdupenv_s
- dupenv_s
- _tdupenv_s
- _wdupenv_s
dev_langs: C++
helpviewer_keywords:
- _dupenv_s function
- _tdupenv_s function
- _wdupenv_s function
- environment variables
- wdupenv_s function
- dupenv_s function
- tdupenv_s function
ms.assetid: b729ecc2-a31d-4ccf-92a7-5accedb8f8c8
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c42da9004dc5ea63179d94a36335db3932f5d23b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="dupenvs-wdupenvs"></a>_dupenv_s, _wdupenv_s
Geçerli ortamından bir değer alır.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t _dupenv_s(  
   char **buffer,  
   size_t *numberOfElements,  
   const char *varname  
);  
errno_t _wdupenv_s(  
   wchar_t **buffer,  
   size_t *numberOfElements,  
   const wchar_t *varname  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `buffer`  
 Değişken değeri depolamak için bir arabellek.  
  
 `numberOfElements`  
 Boyutunu `buffer`.  
  
 `varname`  
 Ortam değişkeni adı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı, başarısız olduğunda bir hata kodu sıfır.  
  
 Bu işlevleri parametrelerini doğrulayın; varsa `buffer` veya `varname` olan `NULL`, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, İşlevler kümesi `errno` için `EINVAL` ve geri dönüp `EINVAL`.  
  
 Bu işlevler için yeterli bellek ayıramıyor varsa, bunlar ayarlamak `buffer` için `NULL` ve `numberOfElements` 0 ve return `ENOMEM`.  
  
## <a name="remarks"></a>Açıklamalar  
 `_dupenv_s` İşlevi için ortam değişkenleri listesi arar `varname`. Değişkeni bulunursa, `_dupenv_s` bir arabellek ayırır ve değişkenin değeri arabelleğe kopyalar. İçinde arabellek adresi ve uzunluğu döndürülen `buffer` ve `numberOfElements`. Arabellek kendisini ayırma tarafından `_dupenv_s` daha uygun bir alternatif sağlayan [getenv_s, _wgetenv_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md).  
  
> [!NOTE]
>  Çağırarak belleği boşaltmak için arama programın sorumluluğu olan [ücretsiz](../../c-runtime-library/reference/free.md).  
  
 Değişken, ardından bulunmazsa `buffer` ayarlanır `NULL`, `numberOfElements` 0 olarak ayarlanır ve bu durum bir hata durumu olarak değerlendirilir değil çünkü dönüş değeri 0'dır.  
  
 Arabellek boyutu değil ilgileniyorsanız geçirebilirsiniz `NULL` için `numberOfElements`.  
  
 `_dupenv_s`Windows işletim sisteminde büyük küçük harfe duyarlı değildir. `_dupenv_s`genel değişkeni tarafından işaret ortam kopyasını kullanan `_environ` ortama erişmek için. Açıklamalar bkz [getenv_s, _wgetenv_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md) bir irdelemesi `_environ`.  
  
 Değer `buffer` ortam değişkeninin değeri; bir kopyası değiştirmeye ortam üzerinde hiçbir etkisi vardır. Kullanım [_putenv_s, _wputenv_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md) bir ortam değişkeninin değerini değiştirmek için işlevi.  
  
 `_wdupenv_s`bir joker karakter sürümü `_dupenv_s`; bağımsız değişkenleri `_wdupenv_s` joker karakter dizelerdir. `_wenviron` Genel değişkeni, bir joker karakter sürümü `_environ`. Açıklamalar bkz [getenv_s, _wgetenv_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md) hakkında daha fazla bilgi için `_wenviron`.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tdupenv_s`|`_dupenv_s`|`_dupenv_s`|`_wdupenv_s`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_dupenv_s`|\<stdlib.h >|  
|`_wdupenv_s`|\<stdlib.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_dupenv_s.c  
#include  <stdlib.h>  
  
int main( void )  
{  
   char *pValue;  
   size_t len;  
   errno_t err = _dupenv_s( &pValue, &len, "pathext" );  
   if ( err ) return -1;  
   printf( "pathext = %s\n", pValue );  
   free( pValue );  
   err = _dupenv_s( &pValue, &len, "nonexistentvariable" );  
   if ( err ) return -1;  
   printf( "nonexistentvariable = %s\n", pValue );  
   free( pValue ); // It's OK to call free with NULL  
}  
```  
  
## <a name="sample-output"></a>Örnek Çıktı  
  
```  
pathext = .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.pl  
nonexistentvariable = (null)  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Süreç ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)   
 [Ortam sabitleri](../../c-runtime-library/environmental-constants.md)   
 [_dupenv_s_dbg, _wdupenv_s_dbg](../../c-runtime-library/reference/dupenv-s-dbg-wdupenv-s-dbg.md)   
 [getenv_s, _wgetenv_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md)   
 [_putenv_s, _wputenv_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md)