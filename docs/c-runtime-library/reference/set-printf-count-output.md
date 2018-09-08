---
title: _set_printf_count_output | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _set_printf_count_output
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
dev_langs:
- C++
helpviewer_keywords:
- '%n format'
- set_printf_count_output function
- _set_printf_count_output function
ms.assetid: d8259ec5-764e-42d0-9169-72172e95163b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 783225412b01430d1043dafd4761cb7432eaa1d7
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44108325"
---
# <a name="setprintfcountoutput"></a>_set_printf_count_output

Etkinleştirmek veya devre dışı desteği **%n** biçiminin [printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)-ailesi işlevleri.

## <a name="syntax"></a>Sözdizimi

```C
int _set_printf_count_output(
   int enable
);
```

### <a name="parameters"></a>Parametreler

*Etkinleştirme*<br/>
Etkinleştirmek için sıfır olmayan bir değer **%n** desteği devre dışı bırakmak için 0 **%n** destekler.

## <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri

Durumunu **%n** desteği bu işlevi çağırmadan önce: sıfır olmayan if **%n** desteği etkindir, 0 devre dışı bırakıldı.

## <a name="remarks"></a>Açıklamalar

Güvenlik nedenleriyle desteği **%n** biçim belirticisi varsayılan olarak devre dışıdır **printf** ve tüm çeşitlerinin. Varsa **%n** ile karşılaşılırsa bir **printf** biçim belirtimi, varsayılan davranışı açıklandığı gibi geçersiz parametre işleyicisini çağırır etmektir [Parameter Validation](../../c-runtime-library/parameter-validation.md). Çağırma **_set_printf_count_output** sıfır olmayan bir bağımsız değişkeni ile neden olacak **printf**-yorumlamak için ailesi işlevleri **%n** açıklandığı [biçimi Belirtim Sözdizimi: printf ve wprintf işlevleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_printf_count_output**|\<stdio.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>Ayrıca bkz.

[_get_printf_count_output](get-printf-count-output.md)<br/>
