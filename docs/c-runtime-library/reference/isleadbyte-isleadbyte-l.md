---
title: isleadbyte, _isleadbyte_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _isleadbyte_l
- isleadbyte
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
- _istleadbyte
- _isleadbyte_l
- isleadbyte
dev_langs:
- C++
helpviewer_keywords:
- lead bytes
- _isleadbyte_l function
- _istleadbyte function
- istleadbyte function
- isleadbyte function
ms.assetid: 3b2bcf09-d82b-4803-9e80-59d04942802a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 82c8f6eb81e96527c0955d9b19fd8ce931e8d7fe
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="isleadbyte-isleadbytel"></a>isleadbyte, _isleadbyte_l
Bir karakter baytı birden çok baytlı karakter olup olmadığını belirler.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int isleadbyte(  
   int c   
);  
int _isleadbyte_l(  
   int c   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `c`  
 Test etmek için bir tamsayı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `isleadbyte` bağımsız değişken test durumu ya da 0 uymazsa yoksa sıfır olmayan bir değer döndürür. "C" yerel ayarını ve tek baytlı karakter (SBCS) yerel kümesi `isleadbyte` her zaman 0 döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `isleadbyte` Makrosu bağımsız değişken birden çok baytlı karakter ilk baytını ise sıfır olmayan bir değer döndürür. `isleadbyte` Tüm tamsayı bağımsız değişkeni-1 için anlamlı bir sonuç üretir (`EOF`) için `UCHAR_MAX` (0xFF) (dahil) arasındadır.  
  
 Beklenen bağımsız değişken türü `isleadbyte` olan `int`; imzalı karakter aktarılırsa derleyici öngörülemeyen sonuçlara sağlayan oturum uzantısı tarafından bir tamsayıya dönüştürmek.  
  
 Bu işlev ile sürümü `_l` sonekidir aynı yerel ayara bağımlı davranışı için geçerli yerel yerine geçirilen yerel ayar kullanır.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_istleadbyte`|Her zaman false döndürür|**_** `isleadbyte`|Her zaman false döndürür|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`isleadbyte`|\<ctype.h>|  
|`_isleadbyte_l`|\<ctype.h>|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bayt sınıflandırması](../../c-runtime-library/byte-classification.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)