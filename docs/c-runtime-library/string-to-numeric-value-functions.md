---
title: "Sayısal değer işlevleri dizesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apilocation:
- msvcr80.dll
- msvcr110.dll
- msvcr120.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- _tcstoui64
- _tcstoi64
dev_langs: C++
helpviewer_keywords:
- parsing, numeric strings
- string conversion, to numeric values
ms.assetid: 11cbd9ce-033b-4914-bf66-029070e7e385
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 68586bac573018bceb7dc982625ff6a859d18871
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="string-to-numeric-value-functions"></a>Sayısal Değer İşlevleri Dizesi
-   [strtod, _strtod_l, wcstod, _wcstod_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)  
  
-   [strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)  
  
-   [strtoul, _strtoul_l, wcstoul, _wcstoul_l](../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)  
  
-   [_strtoi64, _wcstoi64, _strtoi64_l, _wcstoi64_l](../c-runtime-library/reference/strtoi64-wcstoi64-strtoi64-l-wcstoi64-l.md)  
  
-   [_strtoui64, _wcstoui64, _strtoui64_l, _wcstoui64_l](../c-runtime-library/reference/strtoui64-wcstoui64-strtoui64-l-wcstoui64-l.md)  
  
## <a name="remarks"></a>Açıklamalar  
 Her işlev **strtod** ailesi null sonlandırılmış bir dize sayısal bir değere dönüştürür. Kullanılabilir işlevler aşağıdaki tabloda listelenmiştir.  
  
|İşlev|Açıklama|  
|--------------|-----------------|  
|`strtod`|Çift duyarlıklı kayan noktalı değeri dize Dönüştür|  
|`strtol`|Uzun tamsayı dize Dönüştür|  
|`strtoul`|İmzasız uzun tamsayı dize Dönüştür|  
|`_strtoi64`|64 bit dizeyi dönüştürme `__int64` tamsayı|  
|`_strtoui64`|Dönüştürme dizesi 64-bit işaretsiz `__int64` tamsayı|  
  
 `wcstod`, `wcstol`, `wcstoul`, ve `_wcstoi64` joker karakter sürümleri `strtod`, `strtol`, `strtoul`, ve `_strtoi64`sırasıyla. Bu joker karakter işlevlerin her biri için dize bağımsız değişkeni bir joker karakter dizesidir; Her işlevi aynı tek bayt karakter karşılığı aksi şekilde davranır.  
  
 `strtod` İşlev iki bağımsız değişkeni alır: ilk giriş dize ve karakter işaretçi ikinci sona erdiği dönüştürme işlemi. `strtol`, `strtoul`, **_strtoi64** ve **_strtoui64** dönüştürme işleminde kullanılacak temel sayı olarak üçüncü bağımsız değişken alın.  
  
 Giriş dizesi belirtilen türde bir sayısal değer yorumlanan karakterden oluşan bir dizidir. Her işlevi bir sayı bir parçası olarak tanıyamıyor ilk karakter dizesini okuma durdurur. Bu sonlandırma null karakter olabilir. İçin `strtol`, `strtoul`, `_strtoi64`, ve `_strtoui64`, bu sonlandırma karakter da sıfırdan büyük veya eşit kullanıcı tarafından sağlanan temel ilk sayısal karakter olabilir.  
  
 Kullanıcı tarafından sağlanan işaretçiyi bir dönüştürme son karakter ayarlanmamışsa **NULL** çağrısı zaman, tarama durduruldu karakteri gösteren bir işaretçi var. Bunun yerine depolanacak. Hiçbir dönüştürme gerçekleştirilebiliyorsa (hiç geçerli basamak bulunamadı veya geçersiz taban belirtildi), dize işaretçi değeri bu adresinde depolanır.  
  
 `strtod`aşağıdaki biçimde bir dize bekliyor:  
  
 [*boşluk*] [*oturum*] [`digits`] [**.** `digits`] [{**d** &#124; **D** &#124; **e** &#124; **E**} [*oturum*]`digits`]  
  
 A *boşluk* , göz ardı edilir; boşluk veya sekmesinde karakterlerden oluşabilir *oturum* da artı (**+**) veya eksi (**-**); ve `digits` bir veya daha fazla ondalık basamakların. Hiç basamak önce taban karakter görünüyorsa, en az bir taban karakter sonra görünmesi gerekir. Ondalık basamak giriş harfini oluşur üs tarafından izlenebilir (**d**, **D**, **e**, veya **E**) ve bir isteğe bağlı olarak İmzalı tam sayı. Ne üs bir parçası, ne de bir taban karakter görünürse, bir taban karakter dizesindeki son basamaklı izleyin varsayılır. Bu form sığmayan ilk karakter tarama durdurur.  
  
 `strtol`, `strtoul`, `_strtoi64`, Ve `_strtoui64` işlevleri beklediğiniz aşağıdaki biçimde bir dize:  
  
 [*boşluk*] [{ **+**  &#124;  **-** }] [**0** [{ **x** &#124; **X** }]] [`digits`]  
  
 Temel bağımsız 2 ile 36 arasında değilse, sayıyı temel olarak kullanılır. 0 ise, için dönüştürme son işaretçiyi tarafından başvurulan ilk karakter temel belirlemek için kullanılır. İlk karakter 0 ve ikinci karakter 'x' veya 'X' değil, dize sekizlik tamsayı olarak yorumlanır; Aksi takdirde, bu ondalık bir sayı olarak yorumlanır. İlk karakter '0' dir ve ikinci karakteri 'x' veya 'X', dize onaltılık bir tamsayı olarak yorumlanır. İlk karakteri ' 1' üzerinden ' 9'. dize ondalık bir tamsayı olarak yorumlanır. 'A' ile 'z' harf (veya 'A'-'Z') 35 10 değerler atanır; yalnızca atanan değerleri olan harf değerinden *temel* izin verilir. `strtoul`ve `_strtoui64` artı izin ver (**+**) veya eksi (**-**) oturum önek; önüne eksi işareti dönüş değeri tasarruflarını olduğunu gösterir.  
  
 Çıkış değerini ayarı tarafından etkilenen `LC_NUMERIC` yerel kategori ayarı; bkz: [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin sürümleri **_l** bu yerel ayara bağımlı davranış geçerli yerel kullanılmak soneki; sürümleriyle **_l** soneki, yerel ayar parametresi kullanmasını dışında aynıdır Bunun yerine geçirildi.  
  
 Bu işlevler tarafından olduğunda döndürülen değer taşma veya yetersiz neden olur veya dönüştürme mümkün olmadığı durumlarda, özel case değerlerini gösterildiği gibi döndürülür:  
  
|İşlev|Koşul|Döndürülen değer|  
|--------------|---------------|--------------------|  
|`strtod`|Taşma|+/- `HUGE_VAL`|  
|`strtod`|Yetersiz veya dönüştürme|0|  
|`strtol`|+ Taşması|**LONG_MAX**|  
|`strtol`|-Taşması|**LONG_MIN**|  
|`strtol`|Yetersiz veya dönüştürme|0|  
|`_strtoi64`|+ Taşması|**_I64_MAX**|  
|`_strtoi64`|-Taşması|**_I64_MIN**|  
|`_strtoi64`|Hiçbir dönüştürme|0|  
|`_strtoui64`|Taşma|**_UI64_MAX**|  
|`_strtoui64`|Hiçbir dönüştürme|0|  
  
 **_I64_MAX**, _**I64_MIN**, ve **_UI64_MAX** SINIRLARI tanımlanır. H.  
  
 `wcstod`, `wcstol`, `wcstoul`, `_wcstoi64`, ve `_wcstoui64` joker karakter sürümleri `strtod`, `strtol`, `strtoul`, `_strtoi64`, ve `_strtoui64`sırasıyla; işaretçi bir Bu joker karakter işlevlerin her biri dönüştürme son bağımsız değişkeni bir joker karakter dizesidir. Aksi durumda, tek bayt karakter karşılığı Bu joker karakter işlevlerin her biri aynı şekilde davranır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../c-runtime-library/data-conversion.md)   
 [Yerel ayar](../c-runtime-library/locale.md)   
 [Çok baytlı karakter sıralarının yorumu](../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [Kayan nokta desteği](../c-runtime-library/floating-point-support.md)   
 [atof, _atof_l, _wtof, _wtof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)