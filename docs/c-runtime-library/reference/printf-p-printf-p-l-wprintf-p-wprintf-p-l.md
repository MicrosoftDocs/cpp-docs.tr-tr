---
description: 'Hakkında daha fazla bilgi edinin: _printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l'
title: _printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l
ms.date: 11/04/2016
api_name:
- _printf_p
- _wprintf_p
- _printf_p_l
- _wprintf_p_l
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wprintf_p
- _wprintf_p
- printf_p_l
- _printf_p
- printf_p
- _wprintf_p_l
- _printf_p_l
- wprintf_p_l
helpviewer_keywords:
- printf_p function
- printf_p_l function
- wprintf_p function
- wprintf_p_l function
- _tprintf_p_l function
- _wprintf_p function
- _wprintf_p_l function
- _printf_p function
- tprintf_p_l function
- _printf_p_l function
ms.assetid: 1b7e9ef9-a069-45db-af9d-c2730168322e
ms.openlocfilehash: 1249395c883306c04eb0b294d06ec73c4f04447c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97252850"
---
# <a name="_printf_p-_printf_p_l-_wprintf_p-_wprintf_p_l"></a>_printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l

, Biçimli çıktıyı standart çıkış akışına yazdırır ve parametrelerin biçim dizesinde kullanıldığı sıranın belirtimini sağlar.

## <a name="syntax"></a>Sözdizimi

```C
int _printf_p(
   const char *format [,
   argument]...
);
int _printf_p_l(
   const char *format,
   locale_t locale [,
   argument]...
);
int _wprintf_p(
   const wchar_t *format [,
   argument]...
);
int _wprintf_p_l(
   const wchar_t *format,
   locale_t locale [,
   argument]...
);
```

### <a name="parameters"></a>Parametreler

*formatını*<br/>
Biçim denetimi.

*değişkendir*<br/>
İsteğe bağlı bağımsız değişkenler.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bir hata oluşursa yazdırılan karakter sayısını veya negatif bir değer döndürür.

## <a name="remarks"></a>Açıklamalar

**_Printf_p** işlevi, standart çıkış akışına, **stdout** öğesine bir dizi karakter ve değer yazar. Bağımsız değişkenler *Biçim* dizesini izleyemiyorsa, *Biçim* dizesinin bağımsız değişkenlerin çıkış biçimini belirten belirtimleri içermesi gerekir (bkz. [printf_p Konumsal parametreler](../../c-runtime-library/printf-p-positional-parameters.md)).

**_Printf_p** ve **printf_s** arasındaki fark, **_printf_p** konumsal parametreleri desteklediğinden, bağımsız değişkenlerin biçim dizesinde kullanıldığı sırayı belirtmeye olanak tanır. Daha fazla bilgi için bkz. [Printf_p Konumsal parametreler](../../c-runtime-library/printf-p-positional-parameters.md).

**_wprintf_p** , **_printf_p** öğesinin geniş karakterli sürümüdür; Akış ANSI modunda açılırsa aynı şekilde davranır. **_printf_p** Şu anda UNICODE bir akışa çıktıyı desteklememektedir.

**_L** sonekine sahip bu işlevlerin sürümleri, geçerli iş parçacığı yerel ayarı yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır.

> [!IMPORTANT]
> *Biçimin* Kullanıcı tanımlı bir dize olmadığından emin olun.

*Biçim* veya *bağımsız değişken* **null** veya biçim dizesi geçersiz biçimlendirme karakterleri Içeriyorsa, **_printf_p** ve **_wprintf_p** işlevleri [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa işlev-1 döndürür ve **errno** öğesini **EINVAL** olarak ayarlar.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tprintf_p**|**_printf_p**|**_printf_p**|**_wprintf_p**|
|**_tprintf_p_l**|**_printf_p_l**|**_printf_p_l**|**_wprintf_p_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_printf_p**, **_printf_p_l**|\<stdio.h>|
|**_wprintf_p**, **_wprintf_p_l**|\<stdio.h> veya \<wchar.h>|

Konsol Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Console, **STDIN**, **stdout** ve **stderr** Ile ilişkili standart akış TUTAMAÇLARı, C çalışma zamanı işlevlerinin UWP uygulamalarında kullanabilmesi için yeniden yönlendirilmelidir. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_printf_p.c
// This program uses the _printf_p and _wprintf_p
// functions to choose the order in which parameters
// are used.

#include <stdio.h>

int main( void )
{
   // Positional arguments
   _printf_p( "Specifying the order: %2$s %3$s %1$s %4$s %5$s.\n",
              "little", "I'm", "a", "tea", "pot");

   // Resume arguments
   _wprintf_p( L"Reusing arguments: %1$d %1$d %1$d %1$d\n", 10);

   // Width argument
   _printf_p("Width specifiers: %1$*2$s", "Hello\n", 10);
}
```

```Output
Specifying the order: I'm a little tea pot.
Reusing arguments: 10 10 10 10
Width specifiers:     Hello
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l](fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l](fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)<br/>
[_sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l](sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \_ _swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l](sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)<br/>
[vprintf Işlevleri](../../c-runtime-library/vprintf-functions.md)<br/>
