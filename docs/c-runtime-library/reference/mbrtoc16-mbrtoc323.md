---
title: mbrtoc16, mbrtoc323 | Microsoft Docs
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
- mbrtoc16
- mbrtoc32
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
- mbrtoc16
- mbrtoc32
- uchar/mbrtoc16
- uchar/mbrtoc32
dev_langs: C++
helpviewer_keywords:
- mbrtoc16 function
- mbrtoc32 function
ms.assetid: 099ade4d-56f7-4e61-8b45-493f1d7a64bd
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c24a7426c788ac7ecfc98f3e649397912960505a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mbrtoc16-mbrtoc32"></a>mbrtoc16, mbrtoc32
İlk birden çok baytlı karakter dar bir dize, eşdeğer UTF-16 veya UTF-32 karakter çevirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
size_t mbrtoc16(   
   char16_t* destination,   
   const char* source,   
   size_t max_bytes,   
   mbstate_t* state   
);  
  
size_t mbrtoc32(  
   char32_t* destination,   
   const char* source,   
   size_t max_bytes,   
   mbstate_t* state   
);  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `destination`  
 İşaretçi `char16_t` veya `char32_t` dönüştürmek için birden çok baytlı karakter eşdeğeridir. Null ise bir değer işlevi depolamaz.  
  
 `source`  
 İşaretçi dönüştürmek için birden çok baytlı karakter dizesi.  
  
 `max_bytes`  
 Bayt cinsinden en büyük sayısını `source` dönüştürmek için bir karakter incelemek için. Bu bir ve içinde kalan tüm boş Sonlandırıcı dahil olmak üzere bayt sayısı arasında bir değer olmalıdır `source`.  
  
 `state`  
 İşaretçi bir `mbstate_t` bir veya daha fazla çıkış karakter birden çok baytlı dizeye yorumlamak için kullanılan dönüştürme durumu nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa ilk değerini döndürür geçerli geçerlidir Bu koşullar, verilen `state` değeri:  
  
|Değer|Koşul|  
|-----------|---------------|  
|0|Sonraki `max_bytes` veya daha az karakter gelen dönüştürülen `source` durumunda depolanan değeri olan null geniş karakter için karşılık gelen `destination` null değil.<br /><br /> `state`ilk kaydırma durumunu içerir.|  
|1 arasında ve `max_bytes`(dahil)|Döndürülen değer bayt sayısıdır. `source` geçerli bir birden çok baytlı karakter tamamlayın. Dönüştürülen geniş karakter durumunda depolanan `destination` null değil.|  
|-3|Bir önceki işlevi çağrısı kaynaklanan sonraki geniş karakter içinde depolanan `destination` varsa `destination` null değil. Hiçbir baytlar `source` işlev çağrısı tarafından kullanılır.<br /><br /> Zaman `source` işaret (örneğin, bir yedek çifti) göstermek için birden fazla geniş karakter gerektiriyorsa bir birden çok baytlı karakter sonra `state` değeri, böylece sonraki işlev çağrısı ek karakter Yazar güncelleştirilir.|  
|-2|Sonraki `max_bytes` bayt temsil eden bir, ancak tamamlanmamış büyük olasılıkla geçerli, birden çok baytlı karakter. Hiçbir değer depolanan `destination`. Bu sonuç ortaya çıkabilir `max_bytes` sıfırdır.|  
|-1|Bir kodlama hatası oluştu. Sonraki `max_bytes` veya daha az sayıda bayt tam ve geçerli birden çok baytlı karakter katkıda bulunmamaktadır. Hiçbir değer depolanan `destination`.<br /><br /> `EILSEQ`depolanan `errno` ve dönüştürme durumu `state` belirtilmedi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `mbrtoc16` İşlevi okur kadar `max_bytes` baytlar `source` ilk tam, geçerli birden çok baytlı karakter ve ardından depoları eşdeğer UTF-16 karakter bulmak için `destination`. Kaynak bayt geçerli iş parçacığı birden çok baytlı yerel ayar göre değerlendirilir. Birden çok baytlı karakter yedek çifti gibi birden fazla UTF-16 çıkış karakter gerektiriyorsa sonra `state` değeri sonraki UTF-16 karakteri depolamak için ayarlanır `destination` sonraki çağrıda `mbrtoc16`. `mbrtoc32` İşlevi ile aynıdır, ancak çıktı UTF-32 karakter olarak depolanır.  
  
 Varsa `source` bir çağrı denk yapılan bağımsız kullanarak null, bu işlevlerin dönüş `NULL` için `destination`, `""` için `source`, ve `1` için `max_bytes`. Geçirilen değerlerini `destination` ve `max_bytes` göz ardı edilir.  
  
 Varsa `source` olan null, işlevi dizenin başında başlar ve en fazla inceler `max_bytes` tüm üst karakter sıraları dahil olmak üzere sonraki birden çok baytlı karakter tamamlamak için gereken bayt sayısını belirlemek için bayt. Examined bayt geçerli ve tam bir birden çok baytlı karakter içeriyorsa, işlev karakter eşdeğer 16 bit veya 32-bit geniş karakter ya da karakterlerini dönüştürür. Varsa `destination` null olmayan ilk (ve muhtemelen yalnızca) sonuç karakter hedef işlevi mağazaları olan. Ek çıkış karakterleri gerekirse, bir değer kümesinde `state`, böylece işlevi yapılan sonraki çağrılar ek karakterler çıkış ve -3 değerini döndürür. Daha fazla çıkış karakter sonra gerekirse `state` ilk kaydırma durumuna ayarlanır.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|C üstbilgisi|C++ üstbilgi|  
|--------------|--------------|------------------|  
|`mbrtoc16`,                `mbrtoc32`|\<UCHAR.h >|\<cuchar >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [Çok baytlı karakter sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [c16rtomb, c32rtomb](../../c-runtime-library/reference/c16rtomb-c32rtomb1.md)   
 [mbrtowc](../../c-runtime-library/reference/mbrtowc.md)   
 [mbsrtowcs](../../c-runtime-library/reference/mbsrtowcs.md)   
 [mbsrtowcs_s](../../c-runtime-library/reference/mbsrtowcs-s.md)