---
title: _sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l
ms.date: 11/04/2016
apiname:
- _sprintf_p
- _swprintf_p_l
- _swprintf_p
- _sprintf_p_l
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
- _sprintf_p
- _swprintf_p_l
- _sprintf_p_l
- _swprintf_p
- sprintf_p
- swprint_p_l
- swprintf_p
- swprintf_p_l
helpviewer_keywords:
- sprintf_p_l function
- swprintf_p function
- swprintf_p_l function
- _sprintf_p function
- _sprintf_p_l function
- _swprintf_p function
- sprintf_p function
- _stprintf_p function
- stprintf_p function
- _swprintf_p_l function
- stprintf_p_l function
- formatted text [C++]
- _stprintf_p_l function
ms.assetid: a2ae78e8-6b0c-48d5-87a9-ea2365b0693d
ms.openlocfilehash: c55dce7d37d63c79e8c8d9976a76adf331412812
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62354967"
---
# <a name="sprintfp-sprintfpl-swprintfp-swprintfpl"></a>_sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l

Biçimlendirilmiş verileri bir dizeye parametreleri Biçim dizesinde kullanılır sırasını belirtme olanağı ile yazın.

## <a name="syntax"></a>Sözdizimi

```C
int _sprintf_p(
   char *buffer,
   size_t sizeOfBuffer,
   const char *format [,
   argument_list]
);
int _sprintf_p_l(
   char *buffer,
   size_t sizeOfBuffer,
   const char *format,
   locale_t locale [,
   argument_list]
);
int _swprintf_p(
   wchar_t *buffer,
   size_t sizeOfBuffer,
   const wchar_t *format [,
   argument_list]
);
int _swprintf_p_l(
   wchar_t *buffer,
   size_t sizeOfBuffer,
   const wchar_t *format,
   locale_t locale [,
   argument_list]
);
```

### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
Çıktı için depolama konumu

*sizeOfBuffer*<br/>
Depolanacak maksimum karakter sayısı.

*Biçim*<br/>
Biçim denetimi dizesi.

*argument_list*<br/>
Biçim dizesi için isteğe bağlı bağımsız değişkenler.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

Daha fazla bilgi için [biçim belirtimleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Dönüş Değeri

Yazılan karakter sayısını veya bir hata oluştu, -1.

## <a name="remarks"></a>Açıklamalar

**_Sprintf_p** işlevi biçimlendirir ve bir dizi karakter ve değerlerini depolar *arabellek*. Her bağımsız değişkende *argument_list* (varsa) dönüştürülür ve karşılık gelen kapsamındaki biçim belirtimine göre çıkışı *biçimi*. *Biçimi* bağımsız değişken kullanan [biçim belirtim Sözdizimi printf ve wprintf işlevleri için](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md). Bir null karakter son karakter yazıldıktan sonra eklenir. Çakışan dizeler arasında kopyalama olursa davranış tanımsızdır. Arasındaki fark **_sprintf_p** ve **sprintf_s** olan **_sprintf_p** bağımsız değişkenleri olan sırasını belirtmeye izin veren konum parametrelerini desteklemesidir Biçim dizesindeki kullanılır. Daha fazla bilgi için [printf_p konumsal parametreler](../../c-runtime-library/printf-p-positional-parameters.md).

**_swprintf_p** geniş karakterli sürümüdür **_sprintf_p**; işaretçi bağımsız değişkenler **_swprintf_p** geniş karakterli dizelerdir. İçinde kodlama hatalarının algılanması **_swprintf_p** farklı **_sprintf_p**. **_swprintf_p** ve **fwprintf_p** aynı şekilde davranır **_swprintf_p** türünde bir hedef yerine bir dizeye çıktı Yazar **dosya**, ve **_swprintf_p** gerektirir *sayısı* parametresi en fazla yazılacak karakter sayısını belirtin. Sahip bu işlevlerin sürümleri **_l** sonekine, geçerli iş parçacığı yerel ayarı yerine iletilen yerel ayar parametresini kullanmalarıdır.

**_sprintf_p** içinde depolanan bayt sayısını döndüren *arabellek*, sondaki null karakter sayılmaz. **_swprintf_p** içinde depolanan geniş karakterlerin sayısını döndürür *arabellek*, sonlandırıcı geniş null karakter sayılmaz. Varsa *arabellek* veya *biçimi* null bir işaretçiyse veya biçim dizesi geçersiz biçim karakterleri içeriyorsa, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [parametre doğrulama ](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevler -1 döndürür ve **errno** için **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_stprintf_p**|**_sprintf_p**|**_sprintf_p**|**_swprintf_p**|
|**_stprintf_p_l**|**_sprintf_p_l**|**_sprintf_p_l**|**_swprintf_p_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_sprintf_p**, **_sprintf_p_l**|\<stdio.h >|
|**_swprintf_p**, **_swprintf_p_l**|\<stdio.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_sprintf_p.c
// This program uses _sprintf_p to format various
// data and place them in the string named buffer.
//

#include <stdio.h>

int main( void )
{
    char     buffer[200],
            s[] = "computer", c = 'l';
    int      i = 35,
            j;
    float    fp = 1.7320534f;

    // Format and print various data:
    j  = _sprintf_p( buffer, 200,
                     "   String:    %s\n", s );
    j += _sprintf_p( buffer + j, 200 - j,
                     "   Character: %c\n", c );
    j += _sprintf_p( buffer + j, 200 - j,
                     "   Integer:   %d\n", i );
    j += _sprintf_p( buffer + j, 200 - j,
                     "   Real:      %f\n", fp );

    printf( "Output:\n%s\ncharacter count = %d\n",
            buffer, j );
}
```

```Output
Output:
   String:    computer
   Character: l
   Integer:   35
   Real:      1.732053

character count = 79
```

## <a name="example"></a>Örnek

```C
// crt_swprintf_p.c
// This is the wide character example which
// also demonstrates _swprintf_p returning
// error code.
#include <stdio.h>

#define BUFFER_SIZE 100

int main( void )
{
    wchar_t buffer[BUFFER_SIZE];
    int     len;

    len = _swprintf_p(buffer, BUFFER_SIZE, L"%2$s %1$d",
                      0, L" marbles in your head.");
    _printf_p( "Wrote %d characters\n", len );

    // _swprintf_p fails because string contains WEOF (\xffff)
    len = _swprintf_p(buffer, BUFFER_SIZE, L"%s",
                      L"Hello\xffff world" );
    _printf_p( "Wrote %d characters\n", len );
}
```

```Output
Wrote 24 characters
Wrote -1 characters
```

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l](fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[_printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l](printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, __swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l](sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)<br/>
[vprintf İşlevleri](../../c-runtime-library/vprintf-functions.md)<br/>
[printf_p Konumsal Parametreler](../../c-runtime-library/printf-p-positional-parameters.md)<br/>
