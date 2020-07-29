---
title: _cscanf, _cscanf_l, _cwscanf, _cwscanf_l
ms.date: 10/21/2019
api_name:
- _cscanf_l
- _cscanf
- _cwscanf
- _cwscanf_l
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
- _cwscanf
- cwscanf_l
- tcscanf_l
- _tcscanf_l
- _cscanf
- _cscanf_l
- tcscanf
- cwscanf
- _cwscanf_l
- cscanf_l
- _tcscanf
helpviewer_keywords:
- _cwscanf function
- data [C++], reading from the console
- cscanf_l function
- tcscanf function
- _cscanf_l function
- cwscanf function
- _tcscanf_l function
- _cscanf function
- _tcscanf function
- cwscanf_l function
- tcscanf_l function
- reading data [C++], from the console
- _cwscanf_l function
ms.assetid: dbfe7547-b577-4567-a1cb-893fa640e669
ms.openlocfilehash: 45dcbd93ab689c8c86ab35e53552a65f561dfd18
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87234256"
---
# <a name="_cscanf-_cscanf_l-_cwscanf-_cwscanf_l"></a>_cscanf, _cscanf_l, _cwscanf, _cwscanf_l

Konsoldan biçimlendirilen verileri okur. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [_cscanf_s, _cscanf_s_l, _cwscanf_s, _cwscanf_s_l](cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md).

> [!NOTE]
> Visual Studio 2015 ' de `printf` ve içindeki `scanf` İşlevler, **`inline`** `<stdio.h>` ve üst bilgileri ile olarak bildirilmiştir ve taşınır `<conio.h>` . Eski kodu geçiriyorsanız, Bu işlevlerle bağlantılı *LNK2019* görebilirsiniz. Daha fazla bilgi için bkz. [Visual C++ değişiklik geçmişi 2003-2015](../../porting/visual-cpp-change-history-2003-2015.md#stdio_and_conio).

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Söz dizimi

```C
int _cscanf(
   const char *format [,
   argument] ...
);
int _cscanf_l(
   const char *format,
   locale_t locale [,
   argument] ...
);
int _cwscanf(
   const wchar_t *format [,
   argument] ...
);
int _cwscanf_l(
   const wchar_t *format,
   locale_t locale [,
   argument] ...
);
```

### <a name="parameters"></a>Parametreler

*formatını*<br/>
Biçim denetimi dizesi.

*değişkendir*<br/>
İsteğe bağlı parametreler.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Başarıyla dönüştürülen ve atanan alan sayısı. Dönüş değeri, okunan ancak atanmamış alanları içermez. Dosyanın sonunda okuma girişimi için dönüş değeri **EOF** olur. Klavye girişi, işletim sistemi komut satırı düzeyinde yeniden yönlendirildiğinde bu durum oluşabilir. 0 dönüş değeri hiçbir alanın atanmadığı anlamına gelir.

## <a name="remarks"></a>Açıklamalar

**_Cscanf** işlevi, verileri doğrudan konsolundan *bağımsız değişken*tarafından verilen konumlara okur. [_Getche](getch-getwch.md) işlevi karakterleri okumak için kullanılır. Her isteğe bağlı parametre, *biçimdeki*bir tür belirticisine karşılık gelen türe sahip bir değişkene bir işaretçi olmalıdır. Biçim, giriş alanlarının yorumunu denetler ve [scanf](scanf-scanf-l-wscanf-wscanf-l.md) işlevinin *Format* parametresiyle aynı form ve işleve sahiptir. **_Cscanf** normalde giriş karakterini yankılarken, son çağrı **_ungetch**, bunu yapmaz.

Bu işlev, parametrelerini doğrular. Biçim **null**Ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve işlev **EOF**döndürür.

**_L** sonekine sahip bu işlevlerin sürümleri, geçerli iş parçacığı yerel ayarı yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcscanf**|**_cscanf**|**_cscanf**|**_cwscanf**|
|**_tcscanf_l**|**_cscanf_l**|**_cscanf_l**|**_cwscanf_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_cscanf**, **_cscanf_l**|\<conio.h>|
|**_cwscanf**, **_cwscanf_l**|\<conio.h> veya \<wchar.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_cscanf.c
// compile with: /c /W3
/* This program prompts for a string
* and uses _cscanf to read in the response.
* Then _cscanf returns the number of items
* matched, and the program displays that number.
*/

#include <stdio.h>
#include <conio.h>

int main( void )
{
   int   result, i[3];

   _cprintf_s( "Enter three integers: ");
   result = _cscanf( "%i %i %i", &i[0], &i[1], &i[2] ); // C4996
   // Note: _cscanf is deprecated; consider using _cscanf_s instead
   _cprintf_s( "\r\nYou entered " );
   while( result-- )
      _cprintf_s( "%i ", i[result] );
   _cprintf_s( "\r\n" );
}
```

```Input
1 2 3
```

```Output
Enter three integers: 1 2 3
You entered 3 2 1
```

## <a name="see-also"></a>Ayrıca bkz.

[Konsol ve bağlantı noktası g/ç](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](cprintf-cprintf-l-cwprintf-cwprintf-l.md)<br/>
[fscanf, _fscanf_l, fwscanf, _fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
[scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
