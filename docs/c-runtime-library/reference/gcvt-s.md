---
title: _gcvt_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _gcvt_s
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _gcvt_s
- gcvt_s
dev_langs:
- C++
helpviewer_keywords:
- _gcvt_s function
- _CVTBUFSIZE
- floating-point functions, converting number to string
- gcvt_s function
- numbers, converting to strings
- conversions, floating point to strings
- strings [C++], converting from floating point
- CVTBUFSIZE
ms.assetid: 0a8d8a26-5940-4ae3-835e-0aa6ec1b0744
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 567738b488ae648dbd67ea1d2b5cdf34b649170c
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="gcvts"></a>_gcvt_s
Kayan nokta değeri dizeye dönüştürür. Bu bir sürümüdür [_gcvt](../../c-runtime-library/reference/gcvt.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t _gcvt_s(   
   char *buffer,  
   size_t sizeInBytes,  
   double value,  
   int digits   
);  
template <size_t cchStr>  
errno_t _gcvt_s(   
   char (&buffer)[cchStr],  
   double value,  
   int digits   
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  
 [out] `buffer`  
 Dönüştürme işleminin sonucu depolamak için bir arabellek.  
  
 [in] `sizeInBytes`  
 Arabellek boyutu.  
  
 [in] `value`  
 Dönüştürülecek değer.  
  
 [in] `digits`  
 Depolanan basamak sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Zero if successful. Bir hata nedeniyle geçersiz bir parametre oluşursa (geçersiz değerler için aşağıdaki tabloya bakın), geçersiz parametre işleyicisi açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bir hata kodu döndürdü. Hata kodları Errno.h içinde tanımlanmıştır. Bu hataların listesi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
### <a name="error-conditions"></a>Hata koşulları  
  
|`buffer`|`sizeInBytes`|`value`|`digits`|Döndür|Değer `buffer`|  
|--------------|-------------------|-------------|--------------|------------|-----------------------|  
|`NULL`|tüm|tüm|tüm|`EINVAL`|Değiştirilmedi.|  
|Değil `NULL` (noktaları için geçerli bellek)|sıfır|tüm|tüm|`EINVAL`|Değiştirilmedi.|  
|Değil `NULL` (noktaları için geçerli bellek)|tüm|tüm|>= `sizeInBytes`|`EINVAL`|Değiştirilmedi.|  
  
 **Güvenlik Sorunları**  
  
 `_gcvt_s` erişim ihlali durumunda oluşturabilir `buffer` geçerli bellek göstermiyor ve değil `NULL`.  
  
## <a name="remarks"></a>Açıklamalar  
 `_gcvt_s` İşlevin bir kayan nokta dönüştürür `value` (, ondalık ayırıcıdan ve olası oturum bayt içeren) bir karakter dizesine ve dizesinde depolar `buffer`. `buffer` Dönüştürülen değer artı bir sonlandırma null otomatik olarak eklenir karakteri uyabilecek kadar büyük olmalıdır. Arabellek uzunluğu `_CVTBUFSIZE` herhangi bir değişken için yeterliyse noktası değeri. Arabellek boyutu, `digits` + 1 kullanılır, işlevi son üzerine yazmaz arabelleği, bu nedenle bu işlem için yeterli arabellek sağladığınızdan emin olun. `_gcvt_s` üretmek çalışır `digits` onlu basamak. Başaramazsa üreten `digits` üstel biçimdeki rakamları. Sondaki sıfırlar dönüştürmede gizlenebilir.  
  
 C++'da, bu işlev tarafından bir şablon aşırı basitleştirilmiştir; aşırı yük, boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan arabellek uzunluğu bir otomatik olarak Infer. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
 Bu işlev hata ayıklama sürümü ilk arabellek 0xFD ile doldurur. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|---------------------|  
|`_gcvt_s`|\<stdlib.h>|\<Error.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_gcvt_s.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main()  
{  
  char buf[_CVTBUFSIZE];  
  int decimal;  
  int sign;  
  int err;  
  
  err = _gcvt_s(buf, _CVTBUFSIZE, 1.2, 5);  
  
  if (err != 0)  
  {  
     printf("_gcvt_s failed with error code %d\n", err);  
     exit(1);  
  }  
  
  printf("Converted value: %s\n", buf);    
  
}  
```  
  
```Output  
Converted value: 1.2  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_ecvt_s](../../c-runtime-library/reference/ecvt-s.md)   
 [_fcvt_s](../../c-runtime-library/reference/fcvt-s.md)   
 [_gcvt](../../c-runtime-library/reference/gcvt.md)