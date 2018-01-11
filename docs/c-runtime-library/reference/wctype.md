---
title: wctype | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: wctype
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
apitype: DLLExport
f1_keywords: wctype
dev_langs: C++
helpviewer_keywords:
- wctype function
- wide characters
ms.assetid: 14aded12-4087-4123-bc48-db4e10999223
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6dec5a3fd89703b3e27f9acf8c9edf976fdd18f4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="wctype"></a>wctype
Joker karakter kodları için bir sınıflandırma kuralı belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
wctype_t wctype(  
   const char * property   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `property`  
 Özellik dizesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Varsa `LC_CTYPE` geçerli yerel ayar kategorisi adı ile eşleşen özellik dizesi bir sınıflandırma kuralı tanımlamak değil `property`, sıfır işlevi döndürür. Aksi takdirde, sıfır olmayan bir değer ikinci bağımsız değişken olarak kullanım için uygun bir sonraki çağrı için döndürür [towctrans](../../c-runtime-library/reference/towctrans.md).  
  
## <a name="remarks"></a>Açıklamalar  
 İşlev joker karakter kodları için bir sınıflandırma kuralı belirler. Çağrıları aşağıdaki çiftleri tüm yerel ayarlarda aynı davranışı sahiptir (ancak uygulaması bile "C" yerel ayarda ek sınıflandırma kurallarını tanımlayabilirsiniz):  
  
|İşlev|Aynı|  
|--------------|-------------|  
|`iswalnum(`  `c`  `)`|`iswctype(`  `c` `, wctype( "alnum" ) )`|  
|`iswalpha(`  `c`  `)`|`iswctype(`  `c` `, wctype( "alpha" ) )`|  
|`iswcntrl(`  `c`  `)`|`iswctype(`  `c` `, wctype( "cntrl" ) )`|  
|`iswdigit(`  `c`  `)`|`iswctype(`  `c` `, wctype( "digit" ) )`|  
|`iswgraph(`  `c`  `)`|`iswctype(`  `c` `, wctype( "graph" ) )`|  
|`iswlower(`  `c`  `)`|`iswctype(`  `c` `, wctype( "lower" ) )`|  
|`iswprint(`  `c`  `)`|`iswctype(`  `c` `, wctype( "print" ) )`|  
|`iswpunct(`  `c`  `)`|`iswctype(`  `c` `, wctype( "punct" ) )`|  
|`iswspace(`  `c`  `)`|`iswctype(`  `c` `, wctype( "space" ) )`|  
|`iswupper(`  `c`  `)`|`iswctype(`  `c` `, wctype( "upper" ) )`|  
|`iswxdigit(`  `c`  `)`|`iswctype(`  `c` `, wctype( "xdigit" ) )`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`wctype`|\<wctype.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)