---
title: strftime, wcsftime, _strftime_l, _wcsftime_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- strftime
- _wcsftime_l
- _strftime_l
- wcsftime
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tcsftime
- strftime
- wcsftime
dev_langs: C++
helpviewer_keywords:
- _strftime_l function
- strftime function
- tcsftime function
- _wcsftime_l function
- wcsftime function
- _tcsftime function
- time strings
ms.assetid: 6330ff20-4729-4c4a-82af-932915d893ea
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 785ad16e8f86f74252c4391044d2def96091fe61
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="strftime-wcsftime-strftimel-wcsftimel"></a>strftime, wcsftime, _strftime_l, _wcsftime_l
Bir saat dizesi biçimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
size_t strftime(  
   char *strDest,  
   size_t maxsize,  
   const char *format,  
   const struct tm *timeptr   
);  
size_t _strftime_l(  
   char *strDest,  
   size_t maxsize,  
   const char *format,  
   const struct tm *timeptr,  
   _locale_t locale  
);  
size_t wcsftime(  
   wchar_t *strDest,  
   size_t maxsize,  
   const wchar_t *format,  
   const struct tm *timeptr   
);  
size_t _wcsftime_l(  
   wchar_t *strDest,  
   size_t maxsize,  
   const wchar_t *format,  
   const struct tm *timeptr,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `strDest`  
 Çıkış dizesi.  
  
 `maxsize`  
 Boyutunu `strDest` karakter cinsinden arabellek (`char` veya `wchart_t`).  
  
 `format`  
 Biçim denetimi dizesi.  
  
 `timeptr`  
 `tm`veri yapısı.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `strftime`sıraya alınan karakterlerin sayısını döndürür `strDest` ve `wcsftime` karşılık gelen geniş karakter sayısını verir.  
  
 Sonlandırma null gibi karakterler toplam sayısı ise birden fazla `maxsize`, her iki `strftime` ve `wcsftime` 0 ve içeriğini döndürmek `strDest` belirsiz olduğundan.  
  
 Karakter sayısını `strDest` değişmez değer karakter sayısına eşittir `format` eklenebilir herhangi bir karakteri yanı sıra `format` biçimlendirme kodları aracılığıyla. Bir dizenin sonlandırma null dönüş değeri sayılmaz.  
  
## <a name="remarks"></a>Açıklamalar  
 `strftime` Ve `wcsftime` işlevleri biçimi `tm` saat değerinde `timeptr` sağlanan göre `format` bağımsız değişkeni ve deposu sonuç arabelleği `strDest`. En fazla `maxsize` karakter dizesini yerleştirilir. Alanları açıklaması `timeptr` yapısı için bkz: [asctime](../../c-runtime-library/reference/asctime-wasctime.md). `wcsftime`joker karakter eşdeğerdir `strftime`; dize işaretçisi bağımsız değişkeni bir joker karakter dizesi işaret eder. Bu işlevler aynı şekilde aksi davranır.  
  
> [!NOTE]
>  Visual C++ 2005 önce sürümlerde belgelere açıklanan `format` parametresinin `wcsftime` veri türüne sahip olarak `const wchar_t *`, ancak gerçek uygulanması `format` veri türü `const char *`. Uygulaması `format` veri türü, geçerli ve önceki belgeleri, diğer bir deyişle, yansıtacak şekilde güncelleştirildi `const wchar_t *`.  
  
 Bu işlev parametrelerini doğrular. Varsa `strDest`, `format`, veya `timeptr` null işaretçinin veya `tm` veri yapısı tarafından ele `timeptr` (örneğin, tarih veya saat dışında aralık değerleri içeriyorsa), geçersiz veya `format` dize Geçersiz bir biçimlendirme kodu içeren açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için 0 işlevi döndürür ve kümelerini yürütülmesine izin veriliyorsa `errno` için `EINVAL`.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsftime`|`strftime`|`strftime`|`wcsftime`|  
  
 `format` Bağımsız değişkeni oluşan bir veya daha fazla kodları; içinde `printf`, biçimlendirme kodları yüzde işaretiyle öncesinde (`%`). İle başlamayan karakter `%` için değişmeden kopyalanır `strDest`. `LC_TIME` Geçerli yerel ayar kategorisi etkiler çıktı biçimlendirmesi `strftime`. (Daha fazla bilgi için `LC_TIME`, bkz: [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).) Olmadan çalışır `_l` sonekini kullan ayarlanmış yerel ayar. Bu işlevleri sürümlerini `_l` yerel bir parametre olarak geçirmesine ve ayarlanmış yerine kullanan dışında sonek aynı yerel ayar. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
 Biçimlendirme kodları için `strftime` aşağıda listelenmiştir:  
  
 `%a`  
 Kısaltılmış haftanın günü adı  
  
 `%A`  
 Tam haftanın günü adı  
  
 `%b`  
 Kısaltılmış ay adı  
  
 `%B`  
 Tam ay adı  
  
 `%c`  
 Yerel ayarlar için uygun tarih ve saat gösterimi  
  
 `%d`  
 Ondalık sayı (01-31) olarak ayın günü  
  
 `%H`  
 24 saat biçiminde saat (00 - 23)  
  
 `%I`  
 Saat 12 saat biçiminde (01-12)  
  
 `%j`  
 Ondalık sayı (001-366) olarak yılın günü  
  
 `%m`  
 Ondalık sayı (01-12) olarak ay  
  
 `%M`  
 Ondalık sayı olarak dakika (00 - 59)  
  
 `%p`  
 Geçerli yerel dakikaları. 12 saatlik göstergesi  
  
 `%S`  
 Ondalık sayı olarak ikinci (00 - 59)  
  
 `%U`  
 Pazar haftanın ilk günü olarak ondalık bir sayı olarak yılın haftası (00 - 53)  
  
 `%w`  
 Haftanın günü ondalık bir sayı olarak (0 - 6; Pazar 0'dır)  
  
 `%W`  
 Pazartesi haftanın ilk günü olarak ile ondalık bir sayı olarak yılın haftası (00 - 53)  
  
 `%x`  
 Geçerli yerel ayar için tarih gösterimi  
  
 `%X`  
 Geçerli yerel saat gösterimi  
  
 `%y`  
 Ondalık sayı olarak century olmadan yıl (00 - 99)  
  
 `%Y`  
 Ondalık sayı olarak century yıl  
  
 `%z, %Z`  
 Saat dilimi adı ya da kayıt defteri ayarlarına bağlı olarak, saat dilimi kısaltması; saat dilimi bilinmiyorsa herhangi bir karakter  
  
 `%%`  
 Yüzde işareti  
  
 Olarak `printf` işlevi `#` bayrağını herhangi bir biçimlendirme kodu önek. Bu durumda, biçim kodu anlamını şu şekilde değiştirilir.  
  
|Biçim Kodu|Açıklama|  
|-----------------|-------------|  
|`%#a, %#A, %#b, %#B, %#p, %#X, %#z, %#Z, %#%`|`#`Bayrak göz ardı edilir.|  
|`%#c`|Uzun tarih ve saat gösterimi, geçerli yerel ayar için uygun. Örneğin: "Salı, 14 Mart 1995, 12:41:29".|  
|`%#x`|Uzun tarih gösterimi, geçerli yerel ayar için uygun. Örneğin: "Salı, 14 Mart 1995".|  
|`%#d, %#H, %#I, %#j, %#m, %#M, %#S, %#U, %#w, %#W, %#y, %#Y`|Baştaki sıfırlar (varsa) kaldırın.|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`strftime`|\<time.h >|  
|`wcsftime`|\<time.h > veya \<wchar.h >|  
|`_strftime_l`|\<time.h >|  
|`_wcsftime_l`|\<time.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [zaman](../../c-runtime-library/reference/time-time32-time64.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [Zaman Yönetimi](../../c-runtime-library/time-management.md)   
 [Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcoll işlevleri](../../c-runtime-library/strcoll-functions.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)