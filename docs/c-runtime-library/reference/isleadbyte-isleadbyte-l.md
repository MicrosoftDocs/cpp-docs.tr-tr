---
title: isleadbyte, _isleadbyte_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords:
- lead bytes
- _isleadbyte_l function
- _istleadbyte function
- istleadbyte function
- isleadbyte function
ms.assetid: 3b2bcf09-d82b-4803-9e80-59d04942802a
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e6d679d634d14f3a762a6ef3d32d2ca4c5d4b6f0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="isleadbyte-isleadbytel"></a>isleadbyte, _isleadbyte_l
Bir karakter baytı birden çok baytlı karakter olup olmadığını belirler.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
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
 `isleadbyte`bağımsız değişken test durumu ya da 0 uymazsa yoksa sıfır olmayan bir değer döndürür. "C" yerel ayarını ve tek baytlı karakter (SBCS) yerel kümesi `isleadbyte` her zaman 0 döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `isleadbyte` Makrosu bağımsız değişken birden çok baytlı karakter ilk baytını ise sıfır olmayan bir değer döndürür. `isleadbyte`Tüm tamsayı bağımsız değişkeni-1 için anlamlı bir sonuç üretir (`EOF`) için `UCHAR_MAX` (0xFF) (dahil) arasındadır.  
  
 Beklenen bağımsız değişken türü `isleadbyte` olan `int`; imzalı karakter aktarılırsa derleyici öngörülemeyen sonuçlara sağlayan oturum uzantısı tarafından bir tamsayıya dönüştürmek.  
  
 Bu işlev ile sürümü `_l` sonekidir aynı yerel ayara bağımlı davranışı için geçerli yerel yerine geçirilen yerel ayar kullanır.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_istleadbyte`|Her zaman false döndürür|**_** `isleadbyte`|Her zaman false döndürür|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`isleadbyte`|\<CType.h >|  
|`_isleadbyte_l`|\<CType.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bayt sınıflandırması](../../c-runtime-library/byte-classification.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [_ismbb rutinleri](../../c-runtime-library/ismbb-routines.md)