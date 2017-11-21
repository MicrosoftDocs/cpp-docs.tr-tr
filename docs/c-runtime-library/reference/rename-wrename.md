---
title: "Yeniden Adlandır, _wrename | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- rename
- _wrename
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wrename
- _trename
- Rename
dev_langs: C++
helpviewer_keywords:
- trename function
- directories [C++], renaming
- renaming directories
- names [C++], changing file
- _trename function
- rename function
- wrename function
- files [C++], renaming
- _wrename function
- names [C++], changing directory
- renaming files
ms.assetid: 9f0a6103-26a2-4dda-b14b-79a48946266a
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5324b594631f0d45a49d04e771318a84d101fc32
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="rename-wrename"></a>yeniden adlandır, _wrename
Bir dosya veya dizin yeniden adlandırın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      int rename(  
   const char *oldname,  
   const char *newname   
);  
int _wrename(  
   const wchar_t *oldname,  
   const wchar_t *newname   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *EskiAd*  
 Eski adı işaretçi.  
  
 *newname*  
 Yeni ad işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa bu işlevlerin her biri 0 döndürür. Bir hata üzerinde işlevi sıfır olmayan bir değer döndürür ve ayarlar `errno` aşağıdaki değerlerden birine:  
  
 `EACCES`  
 Dosya veya dizin tarafından belirtilen *newname* zaten var veya (geçersiz bir yol) oluşturulamadı; veya *EskiAd* bir dizindir ve *newname* farklı bir yol belirtir.  
  
 `ENOENT`  
 Dosya veya tarafından belirtilen yol *EskiAd* bulunamadı.  
  
 `EINVAL`  
 Adı geçersiz karakterler içeriyor.  
  
 Diğer olası dönüş değerleri için bkz: [_doserrno, _errno, syserrlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 **Yeniden adlandırma** işlevi yeniden adlandırır dosya veya dizin tarafından belirtilen *EskiAd* tarafından verilen adına *newname*. Eski adı, varolan bir dosya veya dizin yolunu olması gerekir. Varolan bir dosya veya dizin adını yeni bir ad olmamalıdır. Kullanabileceğiniz **yeniden adlandırma** bir dosyayı bir dizin veya aygıtı farklı bir yol vererek diğerine taşıma *newname* bağımsız değişkeni. Ancak, kullanamazsınız **yeniden adlandırma** bir dizin taşımak için. Dizinleri yeniden adlandırıldı ancak taşınmaz.  
  
 `_wrename`bir joker karakter sürümü **_rename**; bağımsız değişkenleri `_wrename` joker karakter dizelerdir. `_wrename`ve **_rename** Aksi takdirde aynı şekilde davranır.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_trename`|**Yeniden Adlandır**|**Yeniden Adlandır**|`_wrename`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|**Yeniden Adlandır**|\<io.h > veya \<stdio.h >|  
|`_wrename`|\<stdio.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_renamer.c  
/* This program attempts to rename a file named  
 * CRT_RENAMER.OBJ to CRT_RENAMER.JBO. For this operation  
 * to succeed, a file named CRT_RENAMER.OBJ must exist and  
 * a file named CRT_RENAMER.JBO must not exist.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   int  result;  
   char old[] = "CRT_RENAMER.OBJ", new[] = "CRT_RENAMER.JBO";  
  
   /* Attempt to rename file: */  
   result = rename( old, new );  
   if( result != 0 )  
      printf( "Could not rename '%s'\n", old );  
   else  
      printf( "File '%s' renamed to '%s'\n", old, new );  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
File 'CRT_RENAMER.OBJ' renamed to 'CRT_RENAMER.JBO'  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosya işleme](../../c-runtime-library/file-handling.md)