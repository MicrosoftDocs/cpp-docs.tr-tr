---
title: _cgets, _cgetws
ms.date: 4/2/2020
api_name:
- _cgetws
- _cgets
- _o__cgets
- _o__cgetws
api_location:
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-conio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- cgetws
- _cgetws
- _cgets
helpviewer_keywords:
- _cgetws function
- strings [C++], getting from console
- console, getting strings from
- _cgets function
- cgetws function
- cgets function
ms.assetid: 4d5e134a-58c3-4f62-befd-5d235b0212f4
ms.openlocfilehash: afffb691ca8bf8d180cac11ac5f16a84d871b1b9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81334409"
---
# <a name="_cgets-_cgetws"></a>_cgets, _cgetws

Konsoldan bir karakter dizesi alır. Bu işlevlerin daha güvenli sürümleri mevcuttur; [_cgets_s, _cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md)bakın.

> [!IMPORTANT]
> Bu işlevler geçersizdir. Visual Studio 2015'ten itibaren CRT'de kullanılamazlar. Bu işlevlerin güvenli sürümleri, _cgets_s ve _cgetws_s, hala kullanılabilir. Bu alternatif işlevler hakkında bilgi için [_cgets_s _cgetws_s.](../c-runtime-library/reference/cgets-s-cgetws-s.md)

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```
char *_cgets(
   char *buffer
);
wchar_t *_cgetws(
   wchar_t *buffer
);
template <size_t size>
char *_cgets(
   char (&buffer)[size]
); // C++ only
template <size_t size>
wchar_t *_cgetws(
   wchar_t (&buffer)[size]
); // C++ only
```

#### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
Veriler için depolama konumu.

## <a name="return-value"></a>Dönüş Değeri

`_cgets`ve `_cgetws` dize başlangıcına bir işaretçi `buffer[2]`döndürün, at. NULL `buffer` **NULL**ise, bu işlevler [Parametre Doğrulama'da](../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin verilirse, `errno` `EINVAL` **NULL'u** döndürer ve ' e ayarlarlar.

## <a name="remarks"></a>Açıklamalar

Bu işlevler konsoldan bir karakter dizesini okur ve dizeve `buffer`uzunluğunu işaret ettiği yerde saklar. `buffer` Parametre, bir karakter dizisiiçin bir işaretçi olmalıdır. Dizinin ilk öğesi, `buffer[0]`okunacak dizenin en büyük uzunluğunu (karakterlerde) içermelidir. Dizi dize, bir sonlandırıcı null karakter ('\0') ve 2 ek bayt tutmak için yeterli öğe içermelidir. İşlev, bir satır döndürme satırı beslemesi (CR-LF) birleşimi veya belirtilen karakter sayısı okunana kadar karakterleri okur. Dize' den başlayarak `buffer[2]`depolanır. İşlev cr-lf okursa, null karakterini ('\0') depolar. İşlev daha sonra dize gerçek uzunluğunu ikinci `buffer[1]`dizi öğesinde depolar, .

Tüm düzenleme tuşları bir `_cgets` `_cgetws` konsol penceresindeyken çağrıldığında etkin olduğundan, F3 tuşuna basıldığında son girilen giriş yinelenir.

C++'da, bu işlevlerin daha yeni ve güvenli karşıtlarını çağıran şablon aşırı yüklemeleri vardır. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../c-runtime-library/secure-template-overloads.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|`_cgetts`|`_cgets`|`_cgets`|`_cgetws`|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`_cgets`|\<conio.h>|
|`_cgetws`|\<conio.h> \<veya wchar.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```c
// crt_cgets.c
// compile with: /c /W3
// This program creates a buffer and initializes
// the first byte to the size of the buffer. Next, the
// program accepts an input string using _cgets and displays
// the size and text of that string.

#include <conio.h>
#include <stdio.h>
#include <errno.h>

int main( void )
{
   char buffer[83] = { 80 };  // Maximum characters in 1st byte
   char *result;

   printf( "Input line of text, followed by carriage return:\n");

   // Input a line of text:
   result = _cgets( buffer ); // C4996
   // Note: _cgets is deprecated; consider using _cgets_s
   if (!result)
   {
      printf( "An error occurred reading from the console:"
              " error code %d\n", errno);
   }
   else
   {
      printf( "\nLine length = %d\nText = %s\n",
              buffer[1], result );
   }
}
```

```Output

      A line of input.Input line of text, followed by carriage return:
Line Length = 16
Text = A line of input.
```

## <a name="see-also"></a>Ayrıca bkz.

[Konsol ve Bağlantı Noktası G/Ç](../c-runtime-library/console-and-port-i-o.md)<br/>
[_getch, _getwch](../c-runtime-library/reference/getch-getwch.md)
