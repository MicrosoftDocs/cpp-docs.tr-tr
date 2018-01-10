---
title: _strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsnbcnt_l
- _mbsnccnt
- _wcsncnt
- _strncnt
- _mbsnccnt_l
- _mbsnbcnt
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbsnbcnt
- wcsncnt
- _tcsnbcnt
- _mbsnccnt
- _ftcsnbcnt
- mbsnbcnt
- strncnt
- mbsnbcnt_l
- mbsnccnt_l
- mbsnccnt
- _strncnt
- _wcsncnt
dev_langs: C++
helpviewer_keywords:
- _strncnt function
- _mbsnbcnt function
- _mbsnbcnt_l function
- _mbsnccnt_l function
- mbsnbcnt_l function
- mbsnbcnt function
- tcsnbcnt function
- mbsnccnt_l function
- strncnt function
- _tcsnbcnt function
- mbsnccnt function
- wcsncnt function
- _mbsnccnt function
- _wcsncnt function
ms.assetid: 2a022e9e-a307-4acb-a66b-e56e5357f848
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 27c2d107da6c937705cacac770a50d912cadda84
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="strncnt-wcsncnt-mbsnbcnt-mbsnbcntl-mbsnccnt-mbsnccntl"></a>_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l
Karakter veya belirtilen sayı bayt sayısını döndürür.  
  
> [!IMPORTANT]
>  `_mbsnbcnt`, `_mbsnbcnt_l`, `_mbsnccnt`, ve `_mbsnccnt_l` Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
size_t _strncnt(  
   const char *str,  
   size_t count  
);  
size_t _wcsncnt(  
   const wchar_t *str,  
   size_t count  
);  
size_t _mbsnbcnt(  
   const unsigned char *str,  
   size_t count   
);  
size_t _mbsnbcnt_l(  
   const unsigned char *str,  
   size_t count,  
   _locale_t locale  
);  
size_t _mbsnccnt(  
   const unsigned char *str,  
   size_t count  
);  
size_t _mbsnccnt_l(  
   const unsigned char *str,  
   size_t count,  
   _locale_t locale  
);  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `str`  
 İncelenmesi dizesi.  
  
 `count`  
 Karakter veya içinde incelenmesi bayt sayısını `str`.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_mbsnbcnt`ve `_mbsnbcnt_l` bulunan bayt sayısını döndürmek ilk `count` birden çok baytlı karakter sayısını `str`. `_mbsnccnt`ve `_mbsnccnt_l` bulunan karakter sayısını Döndür ilk `count` bayt sayısı `str`. Bir NULL karakter incelenmesi önce karşılaştı, `str` sahip tamamlandı, bunlar bayt veya önce NULL karakter bulundu karakter sayısını döndürür. Varsa `str` daha az oluşan `count` karakter veya bayt döndürmeleri karakter veya bayt sayısını dizesi içinde. Varsa `count` küçük sıfırdan, bunlar 0 döndürür. Önceki sürümlerde, bu işlevler bir dönüş değeri olan `int` yerine `size_t`.  
  
 `_strncnt`ilk karakter sayısını verir `count` tek baytlı dizesinin bayt `str`. `_wcsncnt`ilk karakter sayısını verir `count` geniş karakter dizesi geniş karakterler `str`.  
  
## <a name="remarks"></a>Açıklamalar  
 `_mbsnbcnt`ve `_mbsnbcnt_l` bulunan bayt sayısı ilk `count` birden çok baytlı karakter sayısını `str`. `_mbsnbcnt`ve `_mbsnbcnt_l` Değiştir `mtob` ve yerine kullanılmalıdır `mtob`.  
  
 `_mbsnccnt`ve `_mbsnccnt_l` bulunan karakterleri sayma ilk `count` bayt sayısı `str`. Varsa `_mbsnccnt` ve `_mbsnccnt_l` bir boş değer bir çift bayt karakter ikinci baytı karşılaşırsanız, ilk bayta kalan de NULL olarak kabul edilir ve döndürülen sayı değeri dahil edilmez. `_mbsnccnt`ve `_mbsnccnt_l` Değiştir `btom` ve yerine kullanılmalıdır `btom`.  
  
 Varsa `str` null işaretçinin veya `count` 0'dır, bu işlevler açıklandığı gibi geçersiz parametre işleyicisi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md), `errno` ayarlanır `EINVAL`, ve işlevi 0 değerini döndürür.  
  
 Çıkış değerini ayarı tarafından etkilenen `LC_CTYPE` yerel kategori ayarı; bkz: [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin sürümleri `_l` bu yerel ayara bağımlı davranış geçerli yerel kullanılmak soneki; sürümleriyle `_l` soneki, bunun yerine geçirilen yerel ayar parametresi kullanmasını dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Yordam|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|-------------|--------------------------------------|--------------------|-----------------------|  
|`_tcsnbcnt`|`_strncnt`|`_mbsnbcnt`|`_wcsncnt`|  
|`_tcsnccnt`|`_strncnt`|`_mbsnbcnt`|`n/a`|  
|`_wcsncnt`|`n/a`|`n/a`|`_mbsnbcnt`|  
|`_wcsncnt`|`n/a`|`n/a`|`_mbsnccnt`|  
|`n/a`|`n/a`|`_mbsnbcnt_l`|`_mbsnccnt_l`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_mbsnbcnt`|\<Mbstring.h >|  
|`_mbsnbcnt_l`|\<Mbstring.h >|  
|`_mbsnccnt`|\<Mbstring.h >|  
|`_mbsnccnt_l`|\<Mbstring.h >|  
|`_strncnt`|\<Tchar.h >|  
|`_wcsncnt`|\<Tchar.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_mbsnbcnt.c  
  
#include  <mbstring.h>  
#include  <stdio.h>  
  
int main( void )  
{  
   unsigned char str[] = "This is a multibyte-character string.";  
   unsigned int char_count, byte_count;  
   char_count = _mbsnccnt( str, 10 );  
   byte_count = _mbsnbcnt( str, 10 );  
   if ( byte_count - char_count )  
      printf( "The first 10 characters contain %d multibyte characters\n", char_count );  
   else  
      printf( "The first 10 characters are single-byte.\n");  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
The first 10 characters are single-byte.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [Çok baytlı karakter sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_mbsnbcat, _mbsnbcat_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)