---
title: alır, _getws | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _getws
- gets
apilocation:
- msvcr80.dll
- msvcr90.dll
- msvcr120.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- _getts
- gets
- _getws
dev_langs:
- C++
helpviewer_keywords:
- getws function
- getts function
- _getws function
- lines, getting
- streams, getting lines
- _getts function
- gets function
- standard input, reading from
ms.assetid: 1ec2dd4b-f801-48ea-97c2-892590f16024
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3309aee316c3b067c9bd0ade4e1064289cb4ddaf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="gets-getws"></a>gets, _getws
Bir satırından alır `stdin` akış. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [gets_s, _getws_s](../c-runtime-library/reference/gets-s-getws-s.md).  
  
> [!IMPORTANT]
>  Bu işlevler artık kullanılmıyor. Visual Studio 2015'te başlayarak, bunlar CRT kullanılabilir değildir. Bu işlev, gets_s ve _getws_s, güvenli sürümlerini hala kullanılabilir. Bu alternatif işlevler hakkında daha fazla bilgi için bkz: [gets_s, _getws_s](../c-runtime-library/reference/gets-s-getws-s.md).  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
char *gets(   
   char *buffer   
);  
wchar_t *_getws(   
   wchar_t *buffer   
);  
template <size_t size>  
char *gets(   
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_getws(   
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  
 `buffer`  
 Giriş dizesi için depolama konumu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, bağımsız değişkeni döndürür. A `NULL` işaretçi bir hata veya dosya sonu durumu gösterir. Kullanım [ferror](../c-runtime-library/reference/ferror.md) veya [feof](../c-runtime-library/reference/feof.md) hangisinin oluştu belirlemek için. Varsa `buffer` olan `NULL`, bu işlevler açıklandığı gibi bir geçersiz parametre işleyicisi çağırma [parametre doğrulaması](../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, bu işlevlerin dönüş `NULL` ve kümesine errno `EINVAL`.  
  
## <a name="remarks"></a>Açıklamalar  
 `gets` İşlevi bir satır standart giriş akışından okuma `stdin` ve depolar `buffer`. Satır kadar ve ilk yeni satır karakteri ('\n') dahil olmak üzere tüm karakterleri oluşur. `gets` ardından yeni satır karakteri satır döndürmeden önce bir null karakter ('\0') yerini alır. Buna karşılık, `fgets` işlevi yeni satır karakteri korur. `_getws` bir joker karakter sürümü `gets`; kendi bağımsız ve dönüş değeri joker karakter dizelerdir.  
  
> [!IMPORTANT]
>  Alır tarafından okuma karakter sayısını sınırlamak için bir yol olduğundan, güvenilmeyen giriş kolayca arabellek taşmaları neden olabilir. Bunun yerine `fgets` kullanın.  
  
 C++'da, bu işlevlerin daha yeni, güvenli ortaklarınıza çağırma şablon aşırı yüklemeleri bu işlevler vardır. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_getts`|`gets`|`gets`|`_getws`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`gets`|\<stdio.h >|  
|`_getws`|\<stdio.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_gets.c  
// compile with: /WX /W3  
  
#include <stdio.h>  
  
int main( void )  
{  
   char line[21]; // room for 20 chars + '\0'  
   gets( line );  // C4996  
   // Danger: No way to limit input to 20 chars.  
   // Consider using gets_s instead.  
   printf( "The line entered was: %s\n", line );  
}  
```  
  
 20 karakter satır arabellek taşması ve neredeyse kesinlikle programın çökmesine neden daha uzun giriş unutmayın.  
  
```Output  
  
Hello there!The line entered was: Hello there!  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../c-runtime-library/stream-i-o.md)   
 [fgets, fgetws](../c-runtime-library/reference/fgets-fgetws.md)   
 [fputs, fputws](../c-runtime-library/reference/fputs-fputws.md)   
 [puts, _putws](../c-runtime-library/reference/puts-putws.md)