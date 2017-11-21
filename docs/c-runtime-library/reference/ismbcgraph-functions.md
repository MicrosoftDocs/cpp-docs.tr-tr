---
title: _ismbcgraph, _ismbcgraph_l, _ismbcprint, _ismbcprint_l, _ismbcpunct, _ismbcpunct_l, _ismbcblank, _ismbcblank_l, _ismbcspace, _ismbcspace_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ismbcpunct_l
- _ismbcblank
- _ismbcprint
- _ismbcgraph_l
- _ismbcblank_l
- _ismbcpunct
- _ismbcprint_l
- _ismbcspace_l
- _ismbcspace
- _ismbcgraph
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
- _ismbcspace
- _ismbcgraph
- _ismbcpunct
- ismbcspace_l
- ismbcgraph
- _ismbcgraph_l
- _ismbcprint
- _ismbcspace_l
- ismbcprint
- ismbcgraph_l
- ismbcspace
- ismbcpunct
dev_langs: C++
helpviewer_keywords:
- ismbcspace_l function
- _ismbcprint_l function
- ismbcspace function
- ismbcpunct function
- _ismbcspace_l function
- _ismbcprint function
- ismbcprint function
- _ismbcgraph function
- ismbcgraph_l function
- _ismbcpunct_l function
- ismbcpunct_l function
- ismbcprint_l function
- _ismbcpunct function
- ismbcgraph function
- _ismbcgraph_l function
- _ismbcspace function
ms.assetid: 8e0a5f47-ba64-4411-92a3-3c525d16e3be
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b2079cb0b00513babd6dc2d5b6c91e82675acc74
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ismbcgraph-ismbcgraphl-ismbcprint-ismbcprintl-ismbcpunct-ismbcpunctl-ismbcblank-ismbcblankl-ismbcspace-ismbcspacel"></a>_ismbcgraph, _ismbcgraph_l, _ismbcprint, _ismbcprint_l, _ismbcpunct, _ismbcpunct_l, _ismbcblank, _ismbcblank_l, _ismbcspace, _ismbcspace_l
Karakter grafik karakter, bir görüntü karakter, bir noktalama karakteri veya bir boşluk karakteri olup olmadığını belirler.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz:[/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _ismbcgraph(  
   unsigned int c   
);  
int _ismbcgraph_l(  
   unsigned int c,  
   _locale_t locale   
);  
int _ismbcprint(  
   unsigned int c   
);  
int _ismbcprint_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcpunct(  
   unsigned int c  
);  
int _ismbcpunct_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcblank(  
   unsigned int c   
);  
int _ismbcblank_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcspace(  
   unsigned int c   
);  
int _ismbcspace_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `c`  
 Belirlenecek karakter.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Karakter test durumu ya da 0 uymazsa mevcut değilse bu yordamlar her sıfır olmayan bir değer döndürür. Varsa `c` < = 255 ve karşılık gelen `_ismbb` yordamına (örneğin, `_ismbcalnum` karşılık gelen `_ismbbalnum`), buna karşılık gelen dönüş değeri sonucudur `_ismbb` yordamı.  
  
 Ayarlara sahip dışında bu işlevler sürümleri özdeş `_l` soneki geçerli yerel yerine yerel ayara bağımlı davranışlarını için geçirilen yerel kullanın. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevlerin her biri belirli bir birden çok baytlı karakter verilen bir koşul için sınar.  
  
|Yordam|Test durumu|Kod sayfası 932 örneği|  
|-------------|--------------------|---------------------------|  
|`_ismbcgraph`|Grafiği|Sıfır olmayan ve yalnız döndürür `c` ASCII veya katakana yazdırılabilir dışında herhangi bir karakter boşluk () tek baytlı gösterimidir.|  
|`_ismbcprint`|Yazdırılabilir|Sıfır olmayan ve yalnız döndürür `c` boşluk () dahil olmak üzere tüm ASCII veya katakana yazdırılabilir karakter tek baytlı gösterimidir.|  
|`_ismbcpunct`|Noktalama işaretleri|Sıfır olmayan ve yalnız döndürür `c` ASCII veya katakana herhangi bir noktalama karakteri tek baytlı gösterimidir.|  
|`_ismbcblank`|Boşluk veya yatay sekme|Sıfır olmayan ve yalnız döndürür `c` bir alanı ya da yatay sekme karakteri: `c`0x20 = veya `c`0x09 =.|  
|`_ismbcspace`|Beyaz alan|Sıfır olmayan ve yalnız döndürür `c` bir boşluk karakteri: `c`0x20 veya 0x09 = < =`c`< = 0x0D.|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_ismbcgraph`|\<Mbstring.h >|  
|`_ismbcgraph_l`|\<Mbstring.h >|  
|`_ismbcprint`|\<Mbstring.h >|  
|`_ismbcprint_l`|\<Mbstring.h >|  
|`_ismbcpunct`|\<Mbstring.h >|  
|`_ismbcpunct_l`|\<Mbstring.h >|  
|`_ismbcblank`|\<Mbstring.h >|  
|`_ismbcblank_l`|\<Mbstring.h >|  
|`_ismbcspace`|\<Mbstring.h >|  
|`_ismbcspace_l`|\<Mbstring.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Karakter Sınıflaması](../../c-runtime-library/character-classification.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [Çok baytlı karakter sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_ismbc rutinleri](../../c-runtime-library/ismbc-routines.md)   
 [is, isw rutinleri](../../c-runtime-library/is-isw-routines.md)   
 [_ismbb rutinleri](../../c-runtime-library/ismbb-routines.md)