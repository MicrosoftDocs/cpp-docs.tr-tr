---
title: _ecvt_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _ecvt_s
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
- ecvt_s
- _ecvt_s
dev_langs: C++
helpviewer_keywords:
- _ecvt_s function
- ecvt_s function
- numbers, converting
- converting double numbers
ms.assetid: d52fb0a6-cb91-423f-80b3-952a8955d914
caps.latest.revision: "25"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d835b45d9f06b9b8ff59916e36b124f8b1ec848d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ecvts"></a>_ecvt_s
Dönüştüren bir `double` dizeye sayı. Bu bir sürümüdür [_ecvt](../../c-runtime-library/reference/ecvt.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t _ecvt_s(   
   char * _Buffer,  
   size_t _SizeInBytes,  
   double _Value,  
   int _Count,  
   int *_Dec,  
   int *_Sign  
);  
template <size_t size>  
errno_t _ecvt_s(   
   char (&_Buffer)[size],  
   double _Value,  
   int _Count,  
   int *_Dec,  
   int *_Sign  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  
 [out]`_Buffer`  
 İşaretçi dönüştürme işleminin sonucu olan basamak dizisi ile doldurulur.  
  
 [in]`_SizeInBytes`  
 Arabelleğin bayt cinsinden boyutu.  
  
 [in]`_Value`  
 Dönüştürülecek sayı.  
  
 [in]`_Count`  
 Depolanan basamak sayısı.  
  
 [out]`_Dec`  
 Ondalık noktasının konumunu depolanır.  
  
 [out]`_Sign`  
 Dönüştürülen sayısının işareti.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır. Bir hata olduğunda dönüş değeri bir hata kodudur. Hata kodları Errno.h içinde tanımlanmıştır. Daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Geçersiz bir parametre söz konusu olduğunda aşağıdaki tabloda listelendiği gibi bu işlevi geçersiz parametre işleyicisi açıklandığı gibi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev devam etmek için yürütülmesine izin veriliyorsa, ayarlar `errno` için `EINVAL` ve döndürür `EINVAL`.  
  
### <a name="error-conditions"></a>Hata koşulları  
  
|`_Buffer`|`_SizeInBytes`|_Value|_Count|_Dec|_Sign|Dönüş değeri|Değer`buffer`|  
|---------------|--------------------|-------------|-------------|-----------|------------|------------------|-----------------------|  
|`NULL`|tüm|tüm|tüm|tüm|tüm|`EINVAL`|Değiştirilmedi.|  
|Değil `NULL` (noktaları için geçerli bellek)|<=0|tüm|tüm|tüm|tüm|`EINVAL`|Değiştirilmedi.|  
|tüm|tüm|tüm|tüm|`NULL`|tüm|`EINVAL`|Değiştirilmedi.|  
|tüm|tüm|tüm|tüm|tüm|`NULL`|`EINVAL`|Değiştirilmedi.|  
  
 **Güvenlik sorunları**  
  
 `_ecvt_s`erişim ihlali durumunda oluşturabilir `buffer` geçerli bellek göstermiyor ve değil `NULL`.  
  
## <a name="remarks"></a>Açıklamalar  
 `_ecvt_s` İşlevi bir karakter dizesi kayan noktalı sayı dönüştürür. `_Value` Dönüştürülecek kayan noktalı sayı parametresidir. Bu işlev kadar saklar `count` rakamı `_Value` dize olarak ve bir null karakter ('\0') ekler. Varsa basamak sayısı `_Value` aşıyor `_Count`, düşük düzey basamaklı yuvarlanır. Varsa daha az `count` basamak, dize sıfırlarla doldurulan.  
  
 Yalnızca rakamlar dizesinde depolanır. Ondalık ayırıcının ve işaretini konumunu `_Value` yükseltebilmeniz `_Dec` ve `_Sign` çağrısından sonra. `_Dec` Parametresi dizenin başlangıcını göre Ondalık ayırıcının konumunu vermiş bir tamsayı değeri işaret eder. 0 veya eksi tamsayı değeri, Ondalık ayırıcının ilk rakam solunda kalan gösterir. `_Sign` Parametresi işaret dönüştürülen sayının işaretini gösteren bir tamsayı. Tamsayı değer 0 ise, pozitif bir sayıdır. Aksi takdirde, negatif sayısıdır.  
  
 Arabellek uzunluğu `_CVTBUFSIZE` için herhangi bir kayan nokta değerini yeterlidir.  
  
 Arasındaki farkı `_ecvt_s` ve `_fcvt_s` yorumu içinde olduğu `_Count` parametresi. `_ecvt_s`Yorumlar `_Count` toplam çıkış dizesinde basamak sayısı olarak ancak `_fcvt_s` yorumlar `_Count` ondalık basamak sayısı.  
  
 C++'da, bu işlev tarafından bir şablon aşırı basitleştirilmiştir; aşırı yük, boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan arabellek uzunluğu bir otomatik olarak Infer. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
 Bu işlev hata ayıklama sürümü ilk arabellek 0xFD ile doldurur. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|İsteğe bağlı üstbilgi|  
|--------------|---------------------|---------------------|  
|`_ecvt_s`|\<stdlib.h >|\<errno.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// ecvt_s.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main( )  
{  
  char * buf = 0;  
  int decimal;  
  int sign;  
  int err;  
  
  buf = (char*) malloc(_CVTBUFSIZE);  
  err = _ecvt_s(buf, _CVTBUFSIZE, 1.2, 5, &decimal, &sign);  
  
  if (err != 0)  
  {  
     printf("_ecvt_s failed with error code %d\n", err);  
     exit(1);  
  }  
  
  printf("Converted value: %s\n", buf);    
  
}  
```  
  
```Output  
Converted value: 12000  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [_fcvt_s](../../c-runtime-library/reference/fcvt-s.md)   
 [_gcvt_s](../../c-runtime-library/reference/gcvt-s.md)