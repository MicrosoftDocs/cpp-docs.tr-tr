---
title: _fcvt_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _fcvt_s
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
- fcvt_s
- _fcvt_s
dev_langs:
- C++
helpviewer_keywords:
- fcvt_s function
- converting floating point, to strings
- floating-point functions, converting number to string
- _fcvt_s function
ms.assetid: 48671197-1d29-4c2b-a5d8-d2368f5f68a1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ba668d9c5604ee07b2cafdc4a9b8f70ae1cc884e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="fcvts"></a>_fcvt_s
Kayan noktalı sayı bir dizeye dönüştürür. Bu bir sürümüdür [_fcvt](../../c-runtime-library/reference/fcvt.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t _fcvt_s(   
   char* buffer,  
   size_t sizeInBytes,  
   double value,  
   int count,  
   int *dec,  
   int *sign   
);  
template <size_t size>  
errno_t _fcvt_s(   
   char (&buffer)[size],  
   double value,  
   int count,  
   int *dec,  
   int *sign   
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  
 [out] `buffer`  
 Dönüştürme işleminin sonucu tutacak sağlanan arabellek.  
  
 [in] `sizeInBytes`  
 Arabelleğinin bayt cinsinden boyutu.  
  
 [in] `value`  
 Dönüştürülecek sayı.  
  
 [in] `count`  
 Ondalık basamak sayısı.  
  
 [out] `dec`  
 Saklanan Ondalık ayırıcının konum işaretçi.  
  
 [out] `sign`  
 Depolanan oturum göstergesi işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Zero if successful. Bir hata olduğunda dönüş değeri bir hata kodudur. Hata kodları Errno.h içinde tanımlanmıştır. Bu hataların listesi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Geçersiz bir parametre söz konusu olduğunda aşağıdaki tabloda listelendiği gibi bu işlevi geçersiz parametre işleyicisi açıklandığı gibi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev devam etmek için yürütülmesine izin veriliyorsa, ayarlar `errno` için `EINVAL` ve döndürür `EINVAL`.  
  
### <a name="error-conditions"></a>Hata koşulları  
  
|`buffer`|`sizeInBytes`|value|count|dec|Oturum|Döndür|Değer `buffer`|  
|--------------|-------------------|-----------|-----------|---------|----------|------------|-----------------------|  
|`NULL`|tüm|tüm|tüm|tüm|tüm|`EINVAL`|Değiştirilmedi.|  
|Değil `NULL` (noktaları için geçerli bellek)|<=0|tüm|tüm|tüm|tüm|`EINVAL`|Değiştirilmedi.|  
|tüm|tüm|tüm|tüm|`NULL`|tüm|`EINVAL`|Değiştirilmedi.|  
|tüm|tüm|tüm|tüm|tüm|`NULL`|`EINVAL`|Değiştirilmedi.|  
  
 **Güvenlik Sorunları**  
  
 `_fcvt_s` erişim ihlali durumunda oluşturabilir `buffer` geçerli bellek göstermiyor ve değil `NULL`.  
  
## <a name="remarks"></a>Açıklamalar  
 `_fcvt_s` İşlevi kayan noktalı sayı null olarak sonlandırılan bir karakter dizeye dönüştürür. `value` Dönüştürülecek kayan noktalı sayı parametresidir. `_fcvt_s` rakamı depolar `value` dize olarak ve bir null karakter ('\0') ekler. `count` Parametresi, ondalık ayırıcıdan sonra depolanması için basamak sayısını belirtir. Aşırı basamak yuvarlanır için `count` yerleştirir. Varsa daha az `count` basamaklı duyarlık, dize sıfırlarla doldurulan.  
  
 Yalnızca rakamlar dizesinde depolanır. Ondalık ayırıcının ve işaretini konumunu `value` yükseltebilmeniz `dec` ve `sign` çağrısından sonra. `dec` Parametresi tamsayı değerine; işaret bu tamsayı değeri ondalık dizenin başlangıcını göre konumunu sağlar. Sıfır veya negatif tamsayı değeri belirten Ondalık ayırıcının sol tarafında ilk rakam arasındadır. Parametre `sign` işaret işaretini gösteren tamsayı `value`. Tamsayı varsa 0 olarak ayarlanırsa `value` pozitif ve sıfır olmayan bir sayı ise ayarlanır `value` negatiftir.  
  
 Arabellek uzunluğu `_CVTBUFSIZE` herhangi bir değişken için yeterliyse noktası değeri.  
  
 Arasındaki farkı `_ecvt_s` ve `_fcvt_s` yorumu içinde olduğu `count` parametresi. `_ecvt_s` Yorumlar `count` toplam çıkış dizesi basamak sayısı arttıkça ve `_fcvt_s` yorumlar `count` ondalık basamak sayısı.  
  
 C++'da, bu işlev tarafından bir şablon aşırı basitleştirilmiştir; aşırı yük, boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan arabellek uzunluğu bir otomatik olarak Infer. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
 Bu işlev hata ayıklama sürümü ilk arabellek 0xFD ile doldurur. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|İsteğe bağlı üstbilgi|  
|--------------|---------------------|---------------------|  
|`_fcvt_s`|\<stdlib.h>|\<errno.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
 **Kitaplıklar:** tüm sürümlerini [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Örnek  
  
```  
// fcvt_s.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main()  
{  
  char * buf = 0;  
  int decimal;  
  int sign;  
  int err;  
  
  buf = (char*) malloc(_CVTBUFSIZE);  
  err = _fcvt_s(buf, _CVTBUFSIZE, 1.2, 5, &decimal, &sign);  
  
  if (err != 0)  
  {  
     printf("_fcvt_s failed with error code %d\n", err);  
     exit(1);  
  }  
  
  printf("Converted value: %s\n", buf);    
  
}  
```  
  
```Output  
Converted value: 120000  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_ecvt_s](../../c-runtime-library/reference/ecvt-s.md)   
 [_gcvt_s](../../c-runtime-library/reference/gcvt-s.md)   
 [_fcvt](../../c-runtime-library/reference/fcvt.md)