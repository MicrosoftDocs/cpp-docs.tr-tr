---
title: c16rtomb, c32rtomb1 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- c16rtomb
- c32rtomb
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
- c16rtomb
- c32rtomb
- uchar/c16rtomb
- uchar/c32rtomb
dev_langs: C++
helpviewer_keywords:
- c16rtomb function
- c32rtomb function
ms.assetid: 7f5743ca-a90e-4e3f-a310-c73e16f4e14d
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9eb43d6b225bce002eb2ce5293cb048d3062bcd5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="c16rtomb-c32rtomb"></a>c16rtomb, c32rtomb
Geçerli yerel birden çok baytlı karakter UTF-16 veya UTF-32 geniş karakter dönüştürün.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
size_t c16rtomb(  
    char *mbchar,   
    char16_t wchar,  
    mbstate_t *state  
);  
size_t c32rtomb(  
    char *mbchar,   
    char32_t wchar,  
    mbstate_t *state  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [out]`mbchar`  
 İşaretçi dönüştürülen birden çok baytlı karakter depolamak için bir dizi.  
  
 [in]`wchar`  
 Dönüştürülecek geniş karakter.  
  
 [içinde out]`state`  
 Bir işaretçi bir `mbstate_t` nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Dizi nesnesi içinde depolanan bayt sayısı `mbchar`, tüm üst karakter sıraları dahil olmak üzere. Varsa `wchar` geçerli bir uluslararası karakter, değeri değil (`size_t`)(-1) döndürülür, `errno` ayarlanır `EILSEQ`, değerini `state` belirtilmedi.  
  
## <a name="remarks"></a>Açıklamalar  
 `c16rtomb` İşlevi dönüştürür UTF-16 karakter `wchar` için geçerli yerel eşdeğer birden çok baytlı dar karakter dizisi. Varsa `mbchar` tarafından için dizi nesnesi dönüştürülen sırayla işaret işlevi depoları null işaretçi değil `mbchar`. En fazla `MB_CUR_MAX` bayt depolanır `mbchar`, ve `state` elde edilen birden çok baytlı shift durumuna ayarlanır.    Varsa `wchar` null geniş bir karakter olan bir sırası için gerekli olan ilk kaydırma durumu depolanır, gerekirse, geri yükleme ve ardından null karakteriyle ve `state` ilk dönüştürme durumuna ayarlanır. `c32rtomb` İşlevi aynıdır, ancak UTF-32 karakter dönüştürür.  
  
 Varsa `mbchar` null işaretçi davranışı, bir iç arabellek için değiştirir işlevi çağrısı eşdeğerdir `mbchar` ve geniş bir null karakter için `wchar`.  
  
 `state` Dönüştürme durumu nesne bu işlev ve çok baytlı çıkış karakterleri shift durumunu korumak yeniden başlatılabilir diğer işlevleri yapılan sonraki çağrılar yapmanızı sağlar. Yeniden başlatılabilir ve yeniden başlatılabilir olmayan işlevleri kullanımını karışık veya çağrı olsa sonuçları tanımsız `setlocale` yeniden başlatılabilir işlev çağrıları arasında yapılır.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`c16rtomb`, `c32rtomb`|C, C++: \<uchar.h >|  
  
 Uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [Çok baytlı karakter sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbrtoc16, mbrtoc32](../../c-runtime-library/reference/mbrtoc16-mbrtoc323.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb_s](../../c-runtime-library/reference/wcrtomb-s.md)