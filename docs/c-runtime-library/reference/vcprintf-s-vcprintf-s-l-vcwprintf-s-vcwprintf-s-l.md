---
title: _vcprintf_s, _vcprintf_s_l, _vcwprintf_s, _vcwprintf_s_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _vcprintf_s
- _vcprintf_s_l
- _vcwprintf_s
- _vcwprintf_s_l
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
apitype: DLLExport
f1_keywords:
- vcprintf_s
- vcwprintf_s_l
- _vcwprintf_s
- _vcwprintf_s_l
- _vcprintf_s_l
- _vtcprintf_s
- vcwprintf_s
- vcprintf_s_l
- _vcprintf_s
dev_langs:
- C++
helpviewer_keywords:
- _vtcprintf_s_l function
- _vcwprintf_s_l function
- _vtcprintf_s function
- vtcprintf_s_l function
- vcprintf_s_l function
- _vcprintf_s function
- _vcwprintf_s function
- vcwprintf_s_l function
- vcwprintf_s function
- vcprintf_s function
- _vcprintf_s_l function
- vtcprintf_s function
- formatted text [C++]
ms.assetid: 5a46d45a-30db-45df-9850-455cbdac5636
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 35f0ff7a77da54515e879315843cd6544d27194b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="vcprintfs-vcprintfsl-vcwprintfs-vcwprintfsl"></a>_vcprintf_s, _vcprintf_s_l, _vcwprintf_s, _vcwprintf_s_l
Yazma bağımsız değişkenlerinin listesi için bir işaretçi kullanılarak konsola çıktı biçimlendirilmiş. Bu sürümleri [_vcprintf, _vcprintf_l, _vcwprintf, _vcwprintf_l](../../c-runtime-library/reference/vcprintf-vcprintf-l-vcwprintf-vcwprintf-l.md) açıklandığı gibi güvenlik geliştirmeleri sahip [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _vcprintf(  
   const char* format,  
   va_list argptr  
);  
int _vcprintf(  
   const char* format,  
   locale_t locale,  
   va_list argptr  
);  
int _vcwprintf_s(  
   const wchar_t* format,  
   va_list argptr  
);  
int _vcwprintf_s_l(  
   const wchar_t* format,  
   locale_t locale,  
   va_list argptr  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `format`  
 Biçim belirtimi.  
  
 `argptr`  
 Bağımsız değişken listesiyle işaretçi.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
 Daha fazla bilgi için bkz: [biçim belirtim Sözdizimi: printf ve wprintf işlevleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yazılan karakter sayısını veya bir çıktı hatası oluşursa negatif bir değer.  
  
 Bu işlevlerin daha az güvenli sürümleri gibi `format` null işaretçi açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Ayrıca, bu işlevler, daha az güvenli sürümlerinden farklı olarak, `format` geçerli bir biçim belirtmiyor geçersiz parametre özel durum oluşturulur. Devam etmek için bu işlevler dönüş bir hata kodu ve kümesi yürütülmesine izin veriliyorsa `errno` bu hata kodu. Varsayılan hata kodu `EINVAL` daha belirli bir değerin geçerli olmadığında.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevlerin her biri bir bağımsız değişken listesi için bir işaretçi alır ve ardından biçimlendirir ve verilen veri konsola yazar. `_vcwprintf_s` joker karakter sürümü `_vcprintf_s`. Bağımsız değişken olarak bir joker karakter dizesi sürer.  
  
 Bu işlevleri sürümlerini `_l` soneki, bunların yerine geçerli yerel geçirilen yerel ayar parametresi kullanmasını dışında aynıdır.  
  
> [!IMPORTANT]
>  Emin `format` kullanıcı tanımlı bir dize değil. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_vtcprintf_s`|`_vcprintf_s`|`_vcprintf_s`|`_vcwprintf_s`|  
|`_vtcprintf_s_l`|`_vcprintf_s_l`|`_vcprintf_s_l`|`_vcwprintf_s_l`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|----------------------|  
|`_vcprintf_s`, `_vcprintf_s_l`|\<conio.h > ve \<stdarg.h >|\<varargs.h>*|  
|`_vcwprintf_s`, `_vcwprintf_s_l`|\<conio.h > veya \<wchar.h >, ve \<stdarg.h >|\<varargs.h>*|  
  
 \* UNIX V uyumluluk için gereklidir.  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_vcprintf_s.cpp  
#include <conio.h>  
#include <stdarg.h>  
  
// An error formatting function used to print to the console.  
int eprintf_s(const char* format, ...)  
{  
  va_list args;  
  va_start(args, format);  
  int result = _vcprintf_s(format, args);  
  va_end(args);  
  return result;
}  
  
int main()  
{  
   eprintf_s("  (%d:%d): Error %s%d : %s\n", 10, 23, "C", 2111,  
           "<some error text>");  
   eprintf_s("  (Related to symbol '%s' defined on line %d).\n",  
           "<symbol>", 5 );  
}  
```  
  
```Output  
(10,23): Error C2111 : <some error text>  
  (Related to symbol '<symbol>' defined on line 5).  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [vprintf işlevleri](../../c-runtime-library/vprintf-functions.md)   
 [_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [fprintf, _fprintf_l, fwprintf, _fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [Printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va_arg, va_copy, va_end, va_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)