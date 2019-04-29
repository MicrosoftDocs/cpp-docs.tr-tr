---
title: _cprintf_p, _cprintf_p_l, _cwprintf_p, _cwprintf_p_l
ms.date: 11/04/2016
apiname:
- _cprintf_p_l
- _cwprintf_p_l
- _cwprintf_p
- _cprintf_p
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
- cprintf_p
- cwprintf_p
- tcprintf_p
- _cwprintf_p_l
- _cprintf_p
- csprintf_p_l
- _cprintf_p_l
- _cwprintf_p
- _tcprintf_p
- cprintf_p_l
helpviewer_keywords:
- _cwprintf_p_l function
- cwprintf_p function
- tcprintf_p_l function
- cprintf_p_l function
- _tcprintf_p function
- _tcprintf_p_l function
- _cprintf_p function
- _cprintf_p_l function
- cwprintf_p_l function
- _cwprintf_p function
- tcprintf_p function
- cprintf_p function
ms.assetid: 1f82fd7d-13c8-4c4a-a3e4-db0df3873564
ms.openlocfilehash: ef4ac6a89749c2784e4935fcf83810e81b61ae11
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62348296"
---
# <a name="cprintfp-cprintfpl-cwprintfp-cwprintfpl"></a>_cprintf_p, _cprintf_p_l, _cwprintf_p, _cwprintf_p_l

Biçimlendirir ve konsola yazdırır ve biçim dizesindeki konum parametrelerini destekler.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _cprintf_p(
   const char * format [,
   argument] ...
);
int _cprintf_p_l(
   const char * format,
   locale_t locale [,
   argument] ...
);
int _cwprintf_p(
   const wchar * format [,
   argument] ...
);
int _cwprintf_p_l(
   const wchar * format,
   locale_t locale [,
   argument] ...
);
```

### <a name="parameters"></a>Parametreler

*Biçim*<br/>
Biçim denetimi dizesi.

*Bağımsız değişken*<br/>
İsteğe bağlı parametreler.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Yazdırılan karakter veya bir hata oluştuğunda negatif bir değer sayısı.

## <a name="remarks"></a>Açıklamalar

Bu işlevler biçimlendirmek ve bir dizi karakter ve değerlerini doğrudan konsola yazdırma kullanarak **_putch** ve **_putwch** işlevleri için çıkış karakteri. Her *bağımsız değişken* (varsa) dönüştürülür ve karşılık gelen kapsamındaki biçim belirtimine göre çıkışı *biçimi*. Biçim aynı form ve işleve sahip *biçimi* parametresi için [printf_p](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md) işlevi. Arasındaki fark **_cprintf_p** ve **cprintf_s** olan **_cprintf_p** bağımsız değişkenleri olan sırasını belirtmeye izin veren konum parametrelerini desteklemesidir Biçim dizesindeki kullanılır. Daha fazla bilgi için [printf_p konumsal parametreler](../../c-runtime-library/printf-p-positional-parameters.md).

Farklı **fprintf_p**, **printf_p**, ve **sprintf_p** işlevlerinin **_cprintf_p** ya da **_cwprintf_p** satır besleme karakterlerini satır başı satır besleme (CR-LF) birleşimlerine çevirir çıkış. Önemli bir ayrımdır olan **_cwprintf_p** Windows NT'de kullanıldığı zaman Unicode karakterleri görüntüler. Farklı **_cprintf_p**, **_cwprintf_p** geçerli konsol yerel ayarlarını kullanır.

Sahip bu işlevlerin sürümleri **_l** sonekine, geçerli yerel ayarı yerine iletilen yerel ayar parametresini kullanmalarıdır.

> [!IMPORTANT]
> Emin *biçimi* kullanıcı tanımlı bir dize değil.

Ayrıca, ister **_cprintf_s** ve **_cwprintf_s**, giriş işaretleyicisini ve biçim dizesini doğrularlar. Varsa *biçimi* veya *bağımsız değişken* olan **NULL**, veya biçimi dizesi geçersiz biçim karakterleri içeriyorsa, bu işlevler olarak geçersiz parametre işleyicisini çağırır. açıklanan [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevler -1 döndürür ve **errno** için **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcprintf_p**|**_cprintf_p**|**_cprintf_p**|**_cwprintf_p**|
|**_tcprintf_p_l**|**_cprintf_p_l**|**_cprintf_p_l**|**_cwprintf_p_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_cprintf_p**, **_cprintf_p_l**|\<conio.h >|
|**_cwprintf_p**, **_cwprintf_p_l**|\<conio.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_cprintf_p.c
// This program displays some variables to the console
// using the _cprintf_p function.

#include <conio.h>

int main( void )
{
    int         i = -16,
                h = 29;
    unsigned    u = 62511;
    char        c = 'A';
    char        s[] = "Test";

    // Note that console output does not translate
    // \n as standard output does. Use \r\n instead.
    _cprintf_p( "%2$d  %1$.4x  %3$u  %4$c %5$s\r\n",
                h, i, u, c, s );
}
```

```Output
-16  001d  62511  A Test
```

## <a name="see-also"></a>Ayrıca bkz.

[Konsol ve bağlantı noktası g/ç](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_cscanf, _cscanf_l, _cwscanf, _cwscanf_l](cscanf-cscanf-l-cwscanf-cwscanf-l.md)<br/>
[_cscanf_s, _cscanf_s_l, _cwscanf_s, _cwscanf_s_l](cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)<br/>
[_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l](fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)<br/>
[fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l](fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)<br/>
[_printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l](printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)<br/>
[printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)<br/>
[_sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l](sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)<br/>
[_vfprintf_p, _vfprintf_p_l, _vfwprintf_p, _vfwprintf_p_l](vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)<br/>
[_cprintf_s, _cprintf_s_l, _cwprintf_s, _cwprintf_s_l](cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)<br/>
[printf_p Konumsal Parametreler](../../c-runtime-library/printf-p-positional-parameters.md)<br/>
[Biçim Belirtim Sözdizimi: printf ve wprintf İşlevleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)<br/>
