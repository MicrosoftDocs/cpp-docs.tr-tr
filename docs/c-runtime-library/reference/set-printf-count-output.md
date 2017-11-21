---
title: _set_printf_count_output | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _set_printf_count_output
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- set_printf_count_output
- _set_printf_count_output
dev_langs: C++
helpviewer_keywords:
- '%n format'
- set_printf_count_output function
- _set_printf_count_output function
ms.assetid: d8259ec5-764e-42d0-9169-72172e95163b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8229146184b4d4d0cfbccd60f6c4209356db5f8f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="setprintfcountoutput"></a>_set_printf_count_output
Etkinleştirmek veya devre dışı desteği `%n` biçiminin [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)-ailesi işlevleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _set_printf_count_output(  
   int enable  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `enable`  
 Etkinleştirmek için sıfır olmayan bir değer `%n` desteği, devre dışı bırakmak için 0 `%n` destekler.  
  
## <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri  
 Durumu `%n` destek bu işlevi çağrılmadan önce: sıfır olursa `%n` desteği etkindir, onu devre dışı bırakılmışsa 0.  
  
## <a name="remarks"></a>Açıklamalar  
 Güvenlik nedenleriyle desteği `%n` biçim belirticisi varsayılan olarak devre dışıdır `printf` ve tüm türevleri. Varsa `%n` olarak karşılaşılan bir `printf` biçim belirtimi, varsayılan davranış olduğu açıklandığı gibi geçersiz parametre işleyicisi çağrılacak [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Çağırma `_set_printf_count_output` sıfır olmayan bağımsız değişkeniyle neden olacak `printf`-yorumlamaya ailesi işlevleri `%n` açıklandığı gibi [biçim belirtim Sözdizimi: printf ve wprintf işlevleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_set_printf_count_output`|\<stdio.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```C  
// crt_set_printf_count_output.c  
#include <stdio.h>  
  
int main()  
{  
   int e;  
   int i;  
   e = _set_printf_count_output( 1 );  
   printf( "%%n support was %sabled.\n",  
        e ? "en" : "dis" );  
   printf( "%%n support is now %sabled.\n",  
        _get_printf_count_output() ? "en" : "dis" );  
   printf( "12345%n6789\n", &i ); // %n format should set i to 5  
   printf( "i = %d\n", i );  
}  
```  
  
```Output  
%n support was disabled.  
%n support is now enabled.  
123456789  
i = 5  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_get_printf_count_output](../../c-runtime-library/reference/get-printf-count-output.md)