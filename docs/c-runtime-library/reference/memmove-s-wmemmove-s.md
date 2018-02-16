---
title: memmove_s, wmemmove_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- wmemmove_s
- memmove_s
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wmemmove_s
- memmove_s
dev_langs:
- C++
helpviewer_keywords:
- wmemmove_s function
- memmove_s function
ms.assetid: a17619e4-1307-4bb0-98c6-77f8c68dab2d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 48d63ebfc9e59872f48384f2c84a8dab6df52182
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="memmoves-wmemmoves"></a>memmove_s, wmemmove_s
Bir arabellek diğerine taşır. Sürümleri bunlar [memmove, wmemmove](../../c-runtime-library/reference/memmove-wmemmove.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      errno_t memmove_s(  
   void *dest,  
   size_t numberOfElements,  
   const void *src,  
   size_t count  
);  
errno_t wmemmove_s(  
   wchar_t *dest,  
   size_t numberOfElements,  
   const wchar_t *src,  
   size_t count  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dest`  
 Hedef nesne.  
  
 `numberOfElements`  
 Hedef arabellek boyutu.  
  
 `src`  
 Kaynak nesne.  
  
 `count`  
 Bayt sayısı (`memmove_s`) veya karakter (`wmemmove_s`) kopyalamak için.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır; hatasında bir hata kodu  
  
### <a name="error-conditions"></a>Hata koşulları  
  
|`dest`|`numberOfElements`|`src`|Dönüş değeri|İçeriği `dest`|  
|------------|------------------------|-----------|------------------|------------------------|  
|`NULL`|tüm|tüm|`EINVAL`|değiştirilmedi|  
|tüm|tüm|`NULL`|`EINVAL`|değiştirilmedi|  
|tüm|< `count`|tüm|`ERANGE`|değiştirilmedi|  
  
## <a name="remarks"></a>Açıklamalar  
 Kopya `count` karakterlerinden baytını `src` için `dest`. Kaynak alan ve hedef bazı bölümlerinin çakışırsa, `memmove_s` çakışan bölgede özgün kaynak bayt üzerine önce kopyalanır sağlar.  
  
 Varsa `dest` veya `src` null işaretçi ya da hedef dize çok küçük ise, bu işlevlerin bir geçersiz parametre işleyicisi açıklandığı gibi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md) . Yürütme devam etmek için izin verilip verilmediğini, bu işlevlerin dönüş `EINVAL` ve `errno` için `EINVAL`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`memmove_s`|\<String.h >|  
|`wmemmove_s`|\<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_memmove_s.c  
//  
// The program demonstrates the   
// memmove_s function which works as expected  
// for moving overlapping regions.  
  
#include <stdio.h>  
#include <string.h>  
  
int main()  
{  
   char str[] = "0123456789";  
  
   printf("Before: %s\n", str);  
  
   // Move six bytes from the start of the string  
   // to a new position shifted by one byte. To protect against  
   // buffer overrun, the secure version of memmove requires the  
   // the length of the destination string to be specified.   
  
   memmove_s((str + 1), strnlen(str + 1, 10), str, 6);   
  
   printf_s(" After: %s\n", str);  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
Before: 0123456789  
 After: 0012345789  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ara bellek düzenlemesi](../../c-runtime-library/buffer-manipulation.md)   
 [_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memcpy, wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)   
 [strcpy_s, wcscpy_s, _mbscpy_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)   
 [strcpy, wcscpy, _mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)   
 [strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)