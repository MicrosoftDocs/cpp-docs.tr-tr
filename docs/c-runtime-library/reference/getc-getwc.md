---
title: getc, getwc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- getwc
- getc
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
- _gettc
- getwc
- _gettchar
- getc
dev_langs: C++
helpviewer_keywords:
- characters, reading
- _gettc function
- getwchar function
- streams, reading characters from
- reading characters from streams
- getc function
- getwc function
- gettc function
ms.assetid: 354ef514-d0c7-404b-92f5-995f6a834bb3
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 12ddc1fa68f1b27fa96ffb81ef24004fd1fb0a19
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="getc-getwc"></a>getc, getwc
Bir karakterin üzerinden bir akış okuyun.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int getc(   
   FILE *stream   
);  
wint_t getwc(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `stream`  
 Giriş akışı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Okuma karakteri döndürür. Bir okuma hatası ya da dosya sonu koşulu belirtmek üzere `getc` döndürür `EOF`, ve `getwc` döndürür `WEOF`. İçin `getc`, kullanın `ferror` veya `feof` bir hata ya da dosya sonu denetlemek için. Varsa `stream` olan `NULL`, `getc` ve `getwc` açıklandığı gibi geçersiz parametre işleyicisi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, bu işlevlerin dönüş `EOF` (veya `WEOF` için `getwc`) ve `errno` için `EINVAL`.  
  
 Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hata kodları hakkında daha fazla bilgi için.  
  
## <a name="remarks"></a>Açıklamalar  
 Her yordam tek bir karakterin geçerli konumu ve artışlarla bir dosyadan ilişkili dosya işaretçisini (tanımlıysa) sonraki karaktere işaret edecek şekilde okur. Dosya ile ilişkili `stream`.  
  
 Bu işlevler çağıran iş parçacığı Kilitle ve bu nedenle iş parçacığı güvenlidir. Kilitleme olmayan bir sürümü için bkz: [_getc_nolock, _getwc_nolock](../../c-runtime-library/reference/getc-nolock-getwc-nolock.md).  
  
 Yordamı özgü açıklamalar izleyin.  
  
|Yordam|Açıklamalar|  
|-------------|-------------|  
|`getc`|Aynı `fgetc`, ancak uygulanan bir makrosu ve bir işlevi olarak.|  
|`getwc`|Joker karakter sürümü `getc`. Birden çok baytlı karakter veya geniş karakter mi göre okur `stream` metin modunda veya ikili modunda açılır.|  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_gettc`|`getc`|`getc`|`getwc`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`getc`|\<stdio.h >|  
|`getwc`|\<stdio.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_getc.c  
// Use getc to read a line from a file.  
  
#include <stdio.h>  
  
int main()  
{  
    char buffer[81];  
    int i, ch;  
    FILE* fp;  
  
    // Read a single line from the file "crt_getc.txt".   
  
    fopen_s(&fp, "crt_getc.txt", "r");  
    if (!fp)  
    {  
       printf("Failed to open file crt_getc.txt.\n");  
       exit(1);  
    }  
  
    for (i = 0; (i < 80) && ((ch = getc(fp)) != EOF)  
                         && (ch != '\n'); i++)  
    {  
        buffer[i] = (char) ch;  
    }  
  
    // Terminate string with a null character   
    buffer[i] = '\0';  
    printf( "Input was: %s\n", buffer);  
  
    fclose(fp);  
}  
```  
  
## <a name="input-crtgetctxt"></a>Giriş: crt_getc.txt  
  
```  
Line one.  
Line two.  
```  
  
### <a name="output"></a>Çıkış  
  
```  
Input was: Line one.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [fgetc, fgetwc](../../c-runtime-library/reference/fgetc-fgetwc.md)   
 [_getch, _getwch](../../c-runtime-library/reference/getch-getwch.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)   
 [ungetc, ungetwc](../../c-runtime-library/reference/ungetc-ungetwc.md)