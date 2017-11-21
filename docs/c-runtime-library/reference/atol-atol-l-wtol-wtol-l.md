---
title: atol, _atol_l, _wtol, _wtol_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- atol
- _wtol_l
- _wtol
- _atol_l
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
- _atol_l
- _ttol_l
- _tstol_l
- _tstol
- _wtol
- _ttol
- _wtol_l
dev_langs: C++
helpviewer_keywords:
- tstol function
- atol function
- ttol function
- _atol_l function
- _tstol_l function
- string conversion, to integers
- _tstol function
- _ttol function
- _ttol_l function
- atol_l function
- wtol_l function
- _wtol_l function
- wtol function
- _wtol function
ms.assetid: cedfc21c-2d64-4e9c-bd04-bdf60b12db46
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4ef61564dcecabf25c0945f9774de8bc48de1447
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="atol-atoll-wtol-wtoll"></a>atol, _atol_l, _wtol, _wtol_l
Bir dize uzun bir tamsayıya dönüştürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
long atol(  
   const char *str   
);  
long _atol_l(  
   const char *str,  
   _locale_t locale  
);  
long _wtol(  
   const wchar_t *str   
);  
long _wtol_l(  
   const wchar_t *str,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `str`  
 Dönüştürülecek dizesi.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Her işlevi döndürür `long` değeri bir sayı olarak giriş karakter yorumlama tarafından üretilen. Dönüş değeri için 0 L mi `atol` giriş türü değerine döndürülemezse.  
  
 Taşma büyük pozitif tamsayı değer ile söz konusu olduğunda `atol` döndürür `LONG_MAX`; taşma büyük negatif tamsayı değer ile söz konusu olduğunda `LONG_MIN` döndürülür. Tüm aralık dışı durumlarda `errno` ayarlanır `ERANGE`. Geçirilen parametre ise `NULL`, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi `errno` için `EINVAL` ve 0 döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevlerin bir karakter dizesi uzun tamsayı değerine dönüştürür (`atol`).  
  
 Giriş dizesi belirtilen türde bir sayısal değer yorumlanan karakterden oluşan bir dizidir. İşlevi, giriş dizesi bir sayı bir parçası olarak tanıyamıyor ilk karakterinde okuma durdurur. Bu karakter olabilir `NULL` karakteri ('\0' veya '\0' L) dize sonlandırılıyor.  
  
 `str` Bağımsız değişkeni `atol` aşağıdaki biçime sahiptir:  
  
 [`whitespace`] [`sign`] [`digits`]]  
  
 A `whitespace` , göz ardı edilir; boşluk veya sekmesinde karakterlerden oluşur `sign` da artı (+) veya eksi (-); ve `digits` bir veya daha fazla basamakların.  
  
 `_wtol`aynıdır `atol` dışında uluslararası karakter dizesini alır.  
  
 Bu işlevleri sürümlerini `_l` soneki, geçerli yerel yerine geçirilen yerel ayar parametresi kullanmasını dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tstol`|`atol`|`atol`|`_wtol`|  
|`_ttol`|`atol`|`atol`|`_wtol`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordamları|Gerekli başlık|  
|--------------|---------------------|  
|`atol`|\<stdlib.h >|  
|`_atol_l`, `_wtol`, `_wtol_l`|\<stdlib.h > ve \<wchar.h >|  
  
## <a name="example"></a>Örnek  
 Bu program, dize olarak depolanan sayılar kullanarak sayısal değerleri nasıl dönüştürülebilir gösterir `atol` işlevi.  
  
```  
// crt_atol.c  
// This program shows how numbers stored as  
// strings can be converted to numeric values  
// using the atol functions.  
#include <stdlib.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( void )  
{  
    char    *str = NULL;  
    long    value = 0;  
  
    // An example of the atol function  
    // with leading and trailing white spaces.  
    str = "  -2309 ";  
    value = atol( str );  
    printf( "Function: atol( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the atol function   
    // with an arbitrary decimal point.  
    str = "314127.64";  
    value = atol( str );  
    printf( "Function: atol( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the atol function  
    // with an overflow condition occurring.  
    str = "3336402735171707160320";  
    value = atol( str );  
    printf( "Function: atol( \"%s\" ) = %d\n", str, value );  
    if (errno == ERANGE)  
    {  
       printf("Overflow condition occurred.\n");  
    }  
}  
```  
  
```Output  
Function: atol( "  -2309 " ) = -2309  
Function: atol( "314127.64" ) = 314127  
Function: atol( "3336402735171707160320" ) = 2147483647  
Overflow condition occurred.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [_fcvt](../../c-runtime-library/reference/fcvt.md)   
 [_gcvt](../../c-runtime-library/reference/gcvt.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l](../../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)