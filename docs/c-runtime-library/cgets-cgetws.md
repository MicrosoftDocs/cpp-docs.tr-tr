---
title: _cgets, _cgetws
ms.date: 11/04/2016
apiname:
- _cgetws
- _cgets
apilocation:
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-conio-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: ea4d7be7631f22eecbea7c6727295c17d86dba06
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750343"
---
# <a name="cgets-cgetws"></a>_cgets, _cgetws

Konsoldan bir karakter dizesi alır. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [_cgets_s, _cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md).

> [!IMPORTANT]
>  Bu işlevler kullanım dışıdır. Visual Studio 2015'te başlayarak, CRT içinde kullanılamaz. Bu işlevler, _cgets_s ve _cgetws_s, güvenli sürümleri yine de kullanılabilir. Bu diğer işlevler hakkında daha fazla bilgi için bkz: [_cgets_s, _cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md).

> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
Veri için depolama konumu.

## <a name="return-value"></a>Dönüş Değeri

`_cgets` ve `_cgetws` dizenin başlangıcına bir işaretçi dönüş `buffer[2]`. Varsa `buffer` olduğu **NULL**, bu işlevler içinde açıklanan şekilde geçersiz parametre işleyicisi çağırır [Parameter Validation](../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bunlar döndürür **NULL** ayarlayıp `errno` için `EINVAL`.

## <a name="remarks"></a>Açıklamalar

Bu işlevler, konsoldan bir karakter dizesini okuyun ve dizeyi ve uzunluğunu tarafından işaret edilen konumda depolamak `buffer`. `buffer` Parametresi, bir karakter dizisine bir işaretçi olmalıdır. Dizinin ilk öğesinin `buffer[0]`, okunacak dizenin maksimum uzunluğunu (karakter cinsinden) içermelidir. Dizi, dize, bir sonlandırıcı null karakteri ('\0') ve 2 ek bayt tutmak için yeterli sayıda öğe içermelidir. İşlev bir satır başı satır besleme (CR-LF) birleşimi veya belirli sayıda karakteri okuma kadar karakterleri okur. Dize başlayarak depolanıyor `buffer[2]`. İşlev CR-LF yazıyorsa null karakteri ('\0') depolar. İşlev, dizenin gerçek uzunluğundan ardından ikinci dizi öğesinde depolar. `buffer[1]`.

Tüm düzenleme tuşları etkin olduğu için `_cgets` veya `_cgetws` bir konsolda F3 tuşuna basılması en son girilen girdiyi yineler sırasında çağrılır.

C++'da, bu işlevler, bu işlevlerin daha yeni ve güvenli karşılıklarını çağırma şablon aşırı yüklemeleri vardır. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|`_cgetts`|`_cgets`|`_cgets`|`_cgetws`|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`_cgets`|\<conio.h >|
|`_cgetws`|\<conio.h > veya \<wchar.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```
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

[Konsol ve bağlantı noktası g/ç](../c-runtime-library/console-and-port-i-o.md)<br/>
[_getch, _getwch](../c-runtime-library/reference/getch-getwch.md)
