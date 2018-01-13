---
title: _mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbcjistojms
- _mbcjmstojis
- _mbcjistojms_l
- _mbcjmstojis_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbcjistojms
- _mbcjistojms
- _mbcjistojms_l
- _mbcjmstojis_l
- _mbcjmstojis
- mbcjmstojis_l
- mbcjistojms_l
- mbcjmstojis
dev_langs: C++
helpviewer_keywords:
- _mbcjmstojis_l function
- _mbcjistojms function
- mbcjmstojis function
- _mbcjistojms_l function
- _mbcjmstojis function
- mbcjistojms function
- mbcjmstojis_l function
- mbcjistojms_l function
ms.assetid: dece5127-b337-40a4-aa10-53320a2c9432
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3ed3aada11b5020c285ce9fb867f08b288055581
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mbcjistojms-mbcjistojmsl-mbcjmstojis-mbcjmstojisl"></a>_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l
Japonya endüstri standardı (JIS) ve Japonya Microsoft (JMS) karakter arasında dönüştürür.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned int _mbcjistojms(  
   unsigned int c   
);  
unsigned int _mbcjistojms_l(  
   unsigned int c,  
   _locale_t locale  
);  
unsigned int _mbcjmstojis(  
   unsigned int c   
);  
unsigned int _mbcjmstojis_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `c`  
 Dönüştürülecek karakter.  
  
 `local`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Japonca yerel ayar, bu işlevler dönüştürülen karakter döndürür veya hiçbir dönüştürme mümkün ise 0 döndürür. Bir olmayan Japonca yerel ayarını bu işlevler geçirilen karakteri döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `_mbcjistojms` İşlevi için bir Microsoft Kanji (Shift JIS) karakteri Japonya endüstri standardı (JIS) karakter dönüştürür. Yalnızca sağlama ve izi bayt 0x21 - 0x7E aralıkta olduğunda karakter dönüştürülür. Sağlama veya deneme bayt bu aralığın dışında kalırsa `errno` ayarlanır `EILSEQ`. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 `_mbcjmstojis` İşlevi Shift JIS karakter JIS karaktere dönüştürür. Karakter yalnızca bayt aralığı 0x81-0x9F veya 0xE0 - 0xFC ve sondaki bayt aralığı 0x40-0x7E veya 0x80 - 0xFC ise dönüştürülür. Bazı kod aralık yok atanmış bir karakter içeren ve dönüştürülemiyor noktaları unutmayın.  
  
 Değer `c` baytı dönüştürmek için karakter olan üst 8 bit temsil eder ve sondaki bayt olan alt 8 bit temsil bir 16 bit değeri olmalıdır.  
  
 Çıkış değerini ayarı tarafından etkilenen `LC_CTYPE` yerel kategori ayarı; bkz: [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin sürümleri `_l` bu yerel ayara bağımlı davranış geçerli yerel kullanılmak soneki; sürümleriyle `_l` soneki, bunun yerine geçirilen yerel ayar parametresi kullanmasını dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
 Önceki sürümlerde, `_mbcjistojms` ve `_mbcjmstojis` adı veriliyordu `jistojms` ve `jmstojis`sırasıyla. `_mbcjistojms`, `_mbcjistojms_l`, `_mbcjmstojis` ve `_mbcjmstojis_l` bunun yerine kullanılmalıdır.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_mbcjistojms`|\<Mbstring.h >|  
|`_mbcjistojms_l`|\<Mbstring.h >|  
|`_mbcjmstojis`|\<Mbstring.h >|  
|`_mbcjmstojis_l`|\<Mbstring.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)