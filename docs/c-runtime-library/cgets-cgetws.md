---
title: _cgets, _cgetws | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
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
apitype: DLLExport
f1_keywords:
- cgetws
- _cgetws
- _cgets
dev_langs:
- C++
helpviewer_keywords:
- _cgetws function
- strings [C++], getting from console
- console, getting strings from
- _cgets function
- cgetws function
- cgets function
ms.assetid: 4d5e134a-58c3-4f62-befd-5d235b0212f4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 144e08278fb37e08d741ac8cb5a441c8df788b5b
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
---
# <a name="cgets-cgetws"></a>_cgets, _cgetws
Bir karakter dizesi konsoldan alır. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [_cgets_s, _cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md).  
  
> [!IMPORTANT]
>  Bu işlevler artık kullanılmıyor. Visual Studio 2015'te başlayarak, bunlar CRT kullanılabilir değildir. Bu işlev, _cgets_s ve _cgetws_s, güvenli sürümlerini hala kullanılabilir. Bu alternatif işlevler hakkında daha fazla bilgi için bkz: [_cgets_s, _cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md).  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
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
 `buffer`  
 Verileri için depolama konumu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_cgets` ve `_cgetws` dize başlangıç için bir işaretçi dönüş `buffer[2]`. Varsa `buffer` olan **NULL**, bu işlevler açıklandığı gibi geçersiz parametre işleyicisi çağırma [parametre doğrulaması](../c-runtime-library/parameter-validation.md). Döndürmeleri yürütme devam etmek için izin verilip verilmediğini, **NULL** ve `errno` için `EINVAL`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevlerin bir karakter dizesi konsoldan okunan ve dize ve uzunluğu gösterdiği konumda depolamak `buffer`. `buffer` Parametresi, bir karakter dizisi için bir işaretçi olmalıdır. Dizinin ilk öğesi `buffer[0]`, okumak için dize maksimum uzunluğu (karakter cinsinden) içermelidir. Dizi dizesi, bir sonlandırma null karakteri ('\0') ve 2 ek bayt tutmak için yeterli sayıda öğe içermesi gerekir. İşlev karakter (CR-LF) birleşimi bir satır başı satır besleme veya belirtilen sayıda karakteri okuma kadar okur. Dize başlayarak depolanan `buffer[2]`. İşlev CR LF yazıyorsa, null karakteri ('\0') depolar. İşlev, dize gerçek uzunluğu sonra ikinci dizi öğesinde depolar. `buffer[1]`.  
  
 Tüm düzenleme anahtarları ne zaman etkin olduğundan `_cgets` veya `_cgetws` bir konsol penceresi F3 tuşuna basarak, son girilen giriş yineler sırasında çağrılır.  
  
 C++'da, bu işlevlerin daha yeni, güvenli ortaklarınıza çağırma şablon aşırı yüklemeleri bu işlevler vardır. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_cgetts`|`_cgets`|`_cgets`|`_cgetws`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_cgets`|\<conio.h >|  
|`_cgetws`|\<conio.h > veya \<wchar.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../c-runtime-library/compatibility.md).  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Konsol ve bağlantı noktası g/ç](../c-runtime-library/console-and-port-i-o.md)   
 [_getch, _getwch](../c-runtime-library/reference/getch-getwch.md)