---
title: gets_s, _getws_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _getws_s
- gets_s
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getws_s
- gets_s
dev_langs:
- C++
helpviewer_keywords:
- getws_s function
- _getws_s function
- lines, getting
- streams, getting lines
- buffers, avoiding overruns
- buffer overruns
- buffers, buffer overruns
- gets_s function
- standard input, reading from
ms.assetid: 5880c36f-122c-4061-a1a5-aeeced6fe58c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a1cc1437d826584b89c7c4d9bb513f99af122ca0
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="getss-getwss"></a>gets_s, _getws_s
Bir satırından alır `stdin` akış. Bu sürümleri [alır, _getws](../../c-runtime-library/gets-getws.md) açıklandığı gibi güvenlik geliştirmeleri sahip [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
char *gets_s(   
   char *buffer,  
   size_t sizeInCharacters  
);  
wchar_t *_getws_s(   
   wchar_t *buffer,  
   size_t sizeInCharacters  
);  
template <size_t size>  
char *gets_s(   
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_getws_s(   
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  
 [out] `buffer`  
 Giriş dizesi için depolama konumu.  
  
 [in] `sizeInCharacters`  
 Arabellek boyutu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Döndürür `buffer` başarılı olursa. A `NULL` işaretçi bir hata veya dosya sonu durumu gösterir. Kullanım [ferror](../../c-runtime-library/reference/ferror.md) veya [feof](../../c-runtime-library/reference/feof.md) hangisinin oluştu belirlemek için.  
  
## <a name="remarks"></a>Açıklamalar  
 `gets_s` İşlevi bir satır standart giriş akışından okuma `stdin` ve depolar `buffer`. Satır kadar ve ilk yeni satır karakteri ('\n') dahil olmak üzere tüm karakterleri oluşur. `gets_s` ardından yeni satır karakteri satır döndürmeden önce bir null karakter ('\0') yerini alır. Buna karşılık, `fgets_s` işlevi yeni satır karakteri korur.  
  
 Okuma ilk karakter dosya sonu karakteri ise, bir null karakter başında depolanan `buffer` ve `NULL` döndürülür.  
  
 `_getws` bir joker karakter sürümü `gets_s`; kendi bağımsız ve dönüş değeri joker karakter dizelerdir.  
  
 Varsa `buffer` olan `NULL` veya `sizeInCharacters` sıfırdan küçük veya ona eşit veya arabellek giriş satırı ve null Sonlandırıcı içermesi için çok küçük ise, bu işlevlerin bir geçersiz parametre işleyicisi açıklandığı gibi çağırma [parametresi Doğrulama](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, bu işlevlerin dönüş `NULL` ve kümesine errno `ERANGE`.  
  
 C++'da, bu işlevler kullanılarak şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı arabellek uzunluğu otomatik olarak Infer (boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan) ve bunlar otomatik olarak yeni, güvenli dekiler ile daha eski, güvenli olmayan işlevleri değiştirebilirsiniz. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_getts`|`gets_s`|`gets_s`|`_getws`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`gets_s`|\<stdio.h >|  
|`_getws`|\<stdio.h > veya \<wchar.h >|  
  
Konsol Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Konsol ile ilişkili standart akış tanıtıcıları `stdin`, `stdout`, ve `stderr`, C çalışma zamanı işlevleri UWP uygulamalarında kullanabilmek için önce yeniden yönlendirilmesi gerekiyor. Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).
  
## <a name="example"></a>Örnek  
  
```  
// crt_gets_s.c  
// This program retrieves a string from the stdin and   
// prints the same string to the console.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char line[21]; // room for 20 chars + '\0'  
   gets_s( line, 20 );  
   printf( "The line entered was: %s\n", line );  
}  
```  
  
```Output  
  
Hello there!The line entered was: Hello there!  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [_getws alır](../../c-runtime-library/gets-getws.md)   
 [fgets, fgetws](../../c-runtime-library/reference/fgets-fgetws.md)   
 [fputs, fputws](../../c-runtime-library/reference/fputs-fputws.md)   
 [puts, _putws](../../c-runtime-library/reference/puts-putws.md)