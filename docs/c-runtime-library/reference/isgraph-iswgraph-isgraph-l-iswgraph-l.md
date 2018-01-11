---
title: isgraph, iswgraph, _isgraph_l, _iswgraph_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- isgraph
- iswgraph
- _iswgraph_l
- _isgraph_l
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
- _isgraph_l
- _iswgraph_l
- _ismbcgraph_l
- Isgraph
- _istgraph_l
- _istgraph
- iswgraph
dev_langs: C++
helpviewer_keywords:
- isgraph function
- _istgraph_l function
- istgraph function
- _isgraph_l function
- iswgraph function
- _iswgraph_l function
- _istgraph function
- _ismbcgraph_l function
ms.assetid: 531a5f34-4302-4d0a-8a4f-b7ea150ad941
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fc1dd32d2b427f6d22fad330cc25804ac528ea83
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="isgraph-iswgraph-isgraphl-iswgraphl"></a>isgraph, iswgraph, _isgraph_l, _iswgraph_l
Tamsayı grafik bir karakteri temsil edip etmediğini belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int isgraph(  
   int c   
);  
int iswgraph(  
   wint_t c   
);  
int _isgraph_l(  
   int c,  
   _locale_t locale  
);  
int _iswgraph_l(  
   wint_t c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `c`  
 Test etmek için bir tamsayı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu yordamları döndürür sıfır olmayan IF her `c` yazdırılabilir karakteri boşluk dışında belirli bir gösterimidir. `isgraph`sıfır olmayan bir değer döndürür `c` bir alanı dışında yazdırılabilir bir karakterdir. `iswgraph`sıfır olmayan bir değer döndürür `c` geniş karakter alanı dışında yazdırılabilir bir geniş karakter. Bu yordamlar her 0 döndürür `c` test durumu uygun değil.  
  
 Bu işlevleri sürümlerini `_l` soneki yerine geçerli yerel geçirilen yerel ayar için yerel ayara bağımlı davranışlarını kullanın. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
 Davranışını `isgraph` ve `_isgraph_l` tanımsız ise `c` EOF değil veya 0'dan 0xFF (bunlar dahil) aralığında. CRT hata ayıklama Kitaplığı kullanıldığında ve `c` işlevleri olursa bu değerleri onayı ifade değil.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_istgraph`|`isgraph`|[_ismbcgraph](../../c-runtime-library/reference/ismbcgraph-functions.md)|`iswgraph`|  
|`_istgraph_l`|`_isgraph_l`|[_ismbcgraph_l](../../c-runtime-library/reference/ismbcgraph-functions.md)|`_iswgraph_l`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`isgraph`|\<CType.h >|  
|`iswgraph`|\<CType.h > veya \<wchar.h >|  
|`_isgraph_l`|\<CType.h >|  
|`_iswgraph_l`|\<CType.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Karakter Sınıflaması](../../c-runtime-library/character-classification.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)