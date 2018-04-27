---
title: _cprintf, _cprintf_l, _cwprintf, _cwprintf_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _cwprintf_l
- _cprintf_l
- _cwprintf
- _cprintf
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
- _cwprintf
- cwprintf
- tcprintf
- _tcprintf
- _cprintf
- cwprintf_l
- tcprintf_l
- _tcprintf_l
- cprintf_l
- _cprintf_l
- _cwprintf_l
dev_langs:
- C++
helpviewer_keywords:
- _cprintf_l function
- _cwprintf_l function
- cwprintf function
- cprintf_l function
- characters, printing to console
- printing characters to console
- _tcprintf_l function
- tcprintf function
- _tcprintf function
- tcprintf_l function
- _cwprintf function
- cwprintf_l function
- _cprintf function
ms.assetid: 67ffefd4-45b3-4be0-9833-d8d26ac7c4e2
caps.latest.revision: 34
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 99673b75a09147a1596f133720b640f6fa5138f1
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="cprintf-cprintfl-cwprintf-cwprintfl"></a>_cprintf, _cprintf_l, _cwprintf, _cwprintf_l

Biçimlendirir ve konsola yazdırır. Daha güvenli sürümlerinde kullanılabilir; bkz: [_cprintf_s, _cprintf_s_l, _cwprintf_s, _cwprintf_s_l](cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md).

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _cprintf(
   const char * format [, argument_list]
);
int _cprintf_l(
   const char * format,
   locale_t locale [, argument_list]
);
int _cwprintf(
   const wchar * format [, argument_list]
);
int _cwprintf_l(
   const wchar * format,
   locale_t locale [, argument_list]
);
```

### <a name="parameters"></a>Parametreler

*Biçimi*<br/>
Biçim denetimi dizesi.

*argument_list*<br/>
İsteğe bağlı parametreler için biçim dizesi.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Yazdırılan karakter sayısı.

## <a name="remarks"></a>Açıklamalar

Bu işlevler biçimlendirmek ve bir dizi karakter ve değerlerini doğrudan konsola yazdırma kullanarak **_putch** işlevi (**_putwch** için **_cwprintf**) çıkış karakter . Her bağımsız değişkeninde *argument_list* (varsa) dönüştürülür ve çıktı içinde karşılık gelen biçimi belirtimlerine göre *biçimi*. *Biçimi* bağımsız değişkeni kullanır [biçim belirtim Sözdizimi printf ve wprintf işlevleri için](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md). Farklı **fprintf**, **printf**, ve **sprintf** işlevleri, tipleri **_cprintf** ya da **_cwprintf**satır besleme karakterleri satır başı satır besleme (CR-LF) birleşimlerine çevirir çıkış.

Önemli bir fark olan **_cwprintf** Windows kullanıldığında Unicode karakterler görüntüler. Farklı **_cprintf**, **_cwprintf** geçerli konsol yerel ayarları kullanır.

Bu işlevleri sürümlerini **_l** soneki, geçerli yerel yerine geçirilen yerel ayar parametresi kullanmasını dışında aynıdır.

**_cprintf** doğrular *biçimi* parametresi. Varsa *biçimi* null işaretçi açıklandığı gibi geçersiz parametre işleyicisi işlevi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için ayarlar ve işlev dönüşleri -1 yürütülmesine izin veriliyorsa **errno** için **EINVAL**.

> [!IMPORTANT]
> Emin *biçimi* kullanıcı tanımlı bir dize değil.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcprintf**|**_cprintf**|**_cprintf**|**_cwprintf**|
|**_tcprintf_l**|**_cprintf_l**|**_cprintf_l**|**_cwprintf_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_cprintf**, **_cprintf_l**|\<conio.h >|
|**_cwprintf**, **_cwprintf_l**|\<conio.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_cprintf.c
// compile with: /c
// This program displays some variables to the console.

#include <conio.h>

int main( void )
{
    int         i = -16,
                h = 29;
    unsigned    u = 62511;
    char        c = 'A';
    char        s[] = "Test";

    // Note that console output does not translate \n as
    // standard output does. Use \r\n instead.
    //
    _cprintf( "%d  %.4x  %u  %c %s\r\n", i, h, u, c, s );
}
```

```Output
-16  001d  62511  A Test
```

## <a name="see-also"></a>Ayrıca bkz.

[Konsol ve bağlantı noktası g/ç](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_cscanf, _cscanf_l, _cwscanf, _cwscanf_l](cscanf-cscanf-l-cwscanf-cwscanf-l.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[vfprintf, _vfprintf_l, vfwprintf, _vfwprintf_l](vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)<br/>
[_cprintf_s, _cprintf_s_l, _cwprintf_s, _cwprintf_s_l](cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)<br/>
[_cprintf_p, _cprintf_p_l, _cwprintf_p, _cwprintf_p_l](cprintf-p-cprintf-p-l-cwprintf-p-cwprintf-p-l.md)<br/>
[Biçim Belirtim Sözdizimi: printf ve wprintf İşlevleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)<br/>
