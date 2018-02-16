---
title: _ismbbkpunct, _ismbbkpunct_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _ismbbkpunct_l
- _ismbbkpunct
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
- ismbbkpunct_l
- _ismbbkpunct_l
- ismbbkpunct
- _ismbbkpunct
dev_langs:
- C++
helpviewer_keywords:
- _ismbbkpunct_l function
- ismbbkpunct_l function
- ismbbkpunct function
- _ismbbkpunct function
ms.assetid: a04c59cd-5ca7-4296-bec0-2b0d7f04edd0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4bcf41bfa1e06643aebaf77575d98409be694a48
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="ismbbkpunct-ismbbkpunctl"></a>_ismbbkpunct, _ismbbkpunct_l
Birden çok baytlı karakter bir noktalama karakteri olup olmadığını denetler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _ismbbkpunct(  
   unsigned int c   
);  
int _ismbbkpunct_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `c`  
 Sınanacak tamsayı.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_ismbbkpunct` sıfır olmayan bir değer döndürür tamsayı `c` değilse ASCII olmayan noktalama işareti sembolü veya 0 değil. Örneğin, yalnızca kod sayfası 932 içinde `_ismbbkpunct` katakana noktalama için testleri. `_ismbbkpunct` Geçerli yerel ayar için herhangi bir yerel ayara bağımlı karakter ayarı kullanır. `_ismbbkpunct_l` geçirilen yerel kullanır ancak bu aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_ismbbkpunct`|\<Mbctype.h >|  
|`_ismbbkpunct_l`|\<Mbctype.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bayt sınıflandırması](../../c-runtime-library/byte-classification.md)   
 [_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)