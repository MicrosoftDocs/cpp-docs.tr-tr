---
title: tmpnam_s, _wtmpnam_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- tmpnam_s
- _wtmpnam_s
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
- tmpnam_s
- _wtmpnam_s
- L_tmpnam_s
dev_langs:
- C++
helpviewer_keywords:
- tmpnam_s function
- file names [C++], creating temporary
- _wtmpnam_s function
- L_tmpnam_s constant
- temporary files, creating
- file names [C++], temporary
- wtmpnam_s function
ms.assetid: e70d76dc-49f5-4aee-bfa2-f1baa2bcd29f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 844da11b981b99d5fe69861c3198d0508857a1a5
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="tmpnams-wtmpnams"></a>tmpnam_s, _wtmpnam_s
Geçici dosyaları oluşturmak için kullanabileceğiniz adları oluşturun. Sürümleri bunlar [tmpnam ve _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t tmpnam_s(  
   char * str,  
   size_t sizeInChars   
);  
errno_t _wtmpnam_s(  
   wchar_t *str,  
   size_t sizeInChars   
);  
template <size_t size>  
errno_t tmpnam_s(  
   char (&str)[size]  
); // C++ only  
template <size_t size>  
errno_t _wtmpnam_s(  
   wchar_t (&str)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  
 [out] `str`  
 Oluşturulan ad tutacak işaretçi.  
  
 [in] `sizeInChars`  
 Karakter cinsinden arabellek boyutu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu işlevlerin her ikisi de 0 başarılı olursa ya da bir hata numarası hatası döndürür.  
  
### <a name="error-conditions"></a>Hata koşulları  
  
|||||  
|-|-|-|-|  
|`str`|`sizeInChars`|**Dönüş değeri**|**İçeriği**  `str`|  
|`NULL`|tüm|`EINVAL`|değiştirilmedi|  
|Değil `NULL` (noktaları için geçerli bellek)|çok kısa|`ERANGE`|değiştirilmedi|  
  
 Varsa `str` olan `NULL`, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi `errno` için `EINVAL` ve geri dönüp `EINVAL`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevlerin her biri şu anda var olmayan bir dosya adını döndürür. `tmpnam_s` Geçerli çalışma dizini içinde benzersiz adını döndürür. Bir dosya adı bekletilen bir ters eğik çizgi ve \fname21 gibi hiçbir yol bilgileriyle olduğunda bu adın geçerli çalışma dizini için geçerli olduğunu belirttiğinden unutmayın.  
  
 İçin `tmpnam_s`, bu oluşturulan dosya adı depolayabilir `str`. Tarafından döndürülen dize uzunluğu en fazla `tmpnam_s` olan `L_tmpnam_s`, STDIO tanımlı. H. Varsa `str` olan `NULL`, ardından `tmpnam_s` sonucu bir iç statik arabellek bırakır. Bu nedenle yapılan sonraki çağrılar bu değer yok. Tarafından oluşturulan adı `tmpnam_s` bir program tarafından oluşturulan dosya adının ve ilk çağrısından sonra oluşan `tmpnam_s`, temel 32 sıralı numaraları için bir dosya uzantısı (.1-.1vvvvvu olduğunda `TMP_MAX_S` STDIO içinde. H INT_MAX ise).  
  
 `tmpnam_s` çok baytlı karakter sıralarının işletim sisteminden alınan OEM kod sayfasına göre algılamayı çok baytlı karakter dizesi bağımsız değişkenleri uygun şekilde otomatik olarak yönetir. `_wtmpnam_s` bir joker karakter sürümü `tmpnam_s`; bağımsız değişkeni ve dönüş değeri `_wtmpnam_s` joker karakter dizelerdir. `_wtmpnam_s` ve `tmpnam_s` durumlar dışında aynı şekilde davranır `_wtmpnam_s` çok baytlı karakter dizeleri işlemez.  
  
 C++'da, bu işlevler kullanılarak şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı, boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan arabellek uzunluğu bir otomatik olarak Infer. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ttmpnam_s`|`tmpnam_s`|`tmpnam_s`|`_wtmpnam_s`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`tmpnam_s`|\<stdio.h >|  
|`_wtmpnam_s`|\<stdio.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_tmpnam_s.c  
// This program uses tmpnam_s to create a unique filename in the  
// current working directory.   
//  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{     
   char name1[L_tmpnam_s];  
   errno_t err;  
   int i;  
  
   for (i = 0; i < 15; i++)  
   {  
      err = tmpnam_s( name1, L_tmpnam_s );  
      if (err)  
      {  
         printf("Error occurred creating unique filename.\n");  
         exit(1);  
      }  
      else  
      {  
         printf( "%s is safe to use as a temporary file.\n", name1 );  
      }  
   }    
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [tmpfile_s](../../c-runtime-library/reference/tmpfile-s.md)