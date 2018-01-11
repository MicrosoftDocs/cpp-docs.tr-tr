---
title: _strinc, _wcsinc, _mbsinc, _mbsinc_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsinc
- _wcsinc
- _mbsinc_l
- _strinc
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
- mbsinc_l
- _strinc
- strinc
- _mbsinc
- _wcsinc
- wcsinc
- mbsinc
- _mbsinc_l
dev_langs: C++
helpviewer_keywords:
- _mbsinc function
- wcsinc function
- mbsinc_l function
- _strinc function
- strinc function
- _mbsinc_l function
- mbsinc function
- _wcsinc function
- _tcsinc function
- tcsinc function
ms.assetid: 54685943-8e2c-45e9-a559-2d94930dc6b4
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4fcda1d1c288e6fe8d6a3dfafea287e79ab6738f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="strinc-wcsinc-mbsinc-mbsincl"></a>_strinc, _wcsinc, _mbsinc, _mbsinc_l
Bir dize işaretçisi bir karakter ilerletir.  
  
> [!IMPORTANT]
>  `_mbsinc`ve `_mbsinc_l` Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
char *_strinc(  
   const char *current,  
   _locale_t locale  
);  
wchar_t *_wcsinc(  
   const wchar_t *current,  
   _locale_t locale  
);  
unsigned char *_mbsinc(  
   const unsigned char *current   
);  
unsigned char *_mbsinc_l(  
   const unsigned char *current,  
   _locale_t locale  
);  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `current`  
 Karakter işaretçi.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu yordamlar her bir işaretçi hemen izleyen karakterin döndürür `current`.  
  
## <a name="remarks"></a>Açıklamalar  
 `_mbsinc` İşlevi hemen izleyen birden çok baytlı karakter ilk bayta kalan için bir işaretçi döndürür `current`. `_mbsinc`çok baytlı karakter sıralarının göre tanıdığı [birden çok baytlı kod sayfası](../../c-runtime-library/code-pages.md) , şu anda kullanımda; `_mbsinc_l` yerine geçirilen yerel ayar parametresi kullanır dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
 Genel metin işlevi `_tcsinc`, Tchar.h'de eşlenir tanımlı `_mbsinc` varsa `_MBCS` tanımlanmış, veya `_wcsinc` varsa `_UNICODE` tanımlandı. Aksi takdirde, `_tcsinc` eşlendiği `_strinc`. `_strinc`ve `_wcsinc` tek bayt karakter ve joker karakter sürümleri `_mbsinc`. `_strinc`ve `_wcsinc` yalnızca bu eşleme için sağlanır ve aksi durumda kullanılmamalıdır. Daha fazla bilgi için bkz: [kullanarak genel metin eşlemeleri](../../c-runtime-library/using-generic-text-mappings.md) ve [genel metin eşlemeleri](../../c-runtime-library/generic-text-mappings.md).  
  
 Varsa `current` olan `NULL`, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev, yürütme devam etmek için izin verilip verilmediğini, döndürür `EINVAL` ve ayarlar `errno` için `EINVAL`.  
  
> [!IMPORTANT]
>  Bu işlevler taşması tehditlerine karşı savunmasız olabilir. Arabellek aşırı çalıştırmaları unwarranted ayrıcalıkların nedeni sistem saldırıları için kullanılabilir. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_mbsinc`|\<Mbstring.h >|  
|`_mbsinc_l`|\<Mbstring.h >|  
|`_strinc`|\<Tchar.h >|  
|`_wcsinc`|\<Tchar.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)   
 [_strdec, _wcsdec, _mbsdec, mbsdec_l](../../c-runtime-library/reference/strdec-wcsdec-mbsdec-mbsdec-l.md)   
 [_strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l](../../c-runtime-library/reference/strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)   
 [_strninc, _wcsninc, _mbsninc, _mbsninc_l](../../c-runtime-library/reference/strninc-wcsninc-mbsninc-mbsninc-l.md)