---
title: btowc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: btowc
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
f1_keywords: btowc
dev_langs: C++
helpviewer_keywords: btowc function
ms.assetid: 99a46e02-6f86-4569-af79-5feca012add8
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 71af03a57886b150d6543e3aa11bfb0e05896890
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="btowc"></a>btowc
Tamsayı ilk kaydırma durumda geçerli bir tek baytlı karakter temsil edip etmediğini belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
wint_t btowc(  
   int c  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `c`  
 Test etmek için bir tamsayı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir tek baytlı karakter ilk kaydırma durumda tamsayı temsil ediyorsa karakter joker karakter gösterimini döndürür. Tamsayı EOF ya da geçerli bir tek baytlı karakter ilk kaydırma durumda değil ise WEOF döndürür. Bu işlev çıktısını geçerli tarafından etkilenen `LC_TYPE` yerel ayar.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`btowc`|\<stdio.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)