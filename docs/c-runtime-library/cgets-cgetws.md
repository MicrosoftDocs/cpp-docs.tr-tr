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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 9ae7baaa01029dcf2c02f6ea80b6e816bb671596
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82917438"
---
# <a name="_cgets-_cgetws"></a>_cgets, _cgetws

Konsolundan bir karakter dizesi alır. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [_cgets_s, _cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md).

> [!IMPORTANT]
> Bu işlevler artık kullanılmıyor. Visual Studio 2015 ' den başlayarak, bu dosyalar CRT içinde kullanılamaz. Bu işlevlerin güvenli sürümleri, _cgets_s ve _cgetws_s hala kullanılabilir. Bu alternatif işlevler hakkında daha fazla bilgi için bkz. [_cgets_s, _cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md).

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*arabelleğin*<br/>
Veriler için depolama konumu.

## <a name="return-value"></a>Dönüş Değeri

`_cgets`ve `_cgetws` ' de dizenin başlangıcına bir işaretçi döndürür `buffer[2]`. NULL `buffer` ise **NULL**, bu işlevler [parametre doğrulama](../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, **null** döndürür ve olarak `errno` `EINVAL`ayarlanır.

## <a name="remarks"></a>Açıklamalar

Bu işlevler, konsolundan bir karakter dizesini okur ve dizeyi ve uzunluğu tarafından `buffer`işaret edilen konuma depolar. Parametre `buffer` , bir karakter dizisine yönelik bir işaretçi olmalıdır. Dizinin `buffer[0]`ilk öğesi, okunacak dizenin uzunluk üst sınırını (karakter cinsinden) içermelidir. Dizi, dizeyi tutmak için yeterli öğe, bir Sonlandırıcı null karakteri (' \ 0 ') ve 2 ek bayt içermelidir. İşlev, satır başı satır besleme (CR-LF) birleşimi veya belirtilen karakter sayısı okunana kadar karakterleri okur. Dize, tarihinde `buffer[2]`başlayarak depolanır. İşlev bir CR-LF okurlarsa, null karakteri (' \ 0 ') depolar. Daha sonra işlevi, dizenin gerçek uzunluğunu ikinci dizi öğesinde depolar `buffer[1]`.

Bir konsol penceresinde `_cgets` veya `_cgetws` çağrıldığında tüm düzenleyen anahtarlar etkin olduğundan, F3 tuşuna basıldığında son girilen giriş yinelenir.

C++ ' da, bu işlevlerin, bu işlevlerin daha yeni ve güvenli bir şekilde çağrılmasını sağlayan şablon aşırı yüklemeleri vardır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../c-runtime-library/secure-template-overloads.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|`_cgetts`|`_cgets`|`_cgets`|`_cgetws`|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`_cgets`|\<conio. h>|
|`_cgetws`|\<conio. h> veya \<wchar. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../c-runtime-library/compatibility.md).

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
