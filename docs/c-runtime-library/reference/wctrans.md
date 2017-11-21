---
title: wctrans | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: wctrans
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
f1_keywords: wctrans
dev_langs: C++
helpviewer_keywords:
- character codes, wctrans
- characters, codes
- characters, converting
- wctrans function
ms.assetid: 215404bf-6d60-489c-9ae9-880e6b586162
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6b22ed97755b150831282c517b9bf98851da9003
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="wctrans"></a>wctrans
Karakter kodları bir kümesinden eşleme diğerine belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
wctrans_t wctrans(  
   const char *property   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `property`  
 Geçerli dönüşümler birini belirten bir dize.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Varsa `LC_CTYPE` geçerli yerel ayar kategorisi adı ile eşleşen özellik dizesi eşleme tanımlamak değil `property`, sıfır işlevi döndürür. Aksi takdirde, sıfır olmayan bir değer ikinci bağımsız değişken olarak kullanım için uygun bir sonraki çağrı için döndürür [towctrans](../../c-runtime-library/reference/towctrans.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev bir karakter kodları kümesinden eşleme diğerine belirler.  
  
 Çağrıları aşağıdaki çiftleri tüm yerel ayarlarda aynı davranışı sahiptir, ancak ek eşlemeleri bile "C" yerel ayarda tanımlamak mümkündür:  
  
|İşlev|Aynı|  
|--------------|-------------|  
|`tolower(`  `c`  `)`|`towctrans(`  `c` `, wctrans("towlower" ) )`|  
|`towupper(`  `c`  `)`|`towctrans(`  `c` `, wctrans( "toupper" ) )`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli üstbilgisi|  
|-------------|---------------------|  
|`wctrans`|\<wctype.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_wctrans.cpp  
// compile with: /EHsc  
// This example determines a mapping from one set of character  
// codes to another.   
  
#include <wchar.h>  
#include <wctype.h>  
#include <stdio.h>  
#include <iostream>  
  
int main()   
{  
    wint_t c = 'a';  
    printf_s("%d\n",c);  
  
    wctrans_t i = wctrans("toupper");  
    printf_s("%d\n",i);  
  
    wctrans_t ii = wctrans("towlower");  
    printf_s("%d\n",ii);  
  
    wchar_t wc = towctrans(c, i);  
    printf_s("%d\n",wc);  
}  
```  
  
```Output  
97  
1  
0  
65  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)