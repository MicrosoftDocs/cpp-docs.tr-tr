---
title: _ismbchira, _ismbchira_l, _ismbckata, _ismbckata_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ismbckata
- _ismbchira_l
- _ismbchira
- _ismbckata_l
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
- ismbckata_l
- _ismbckata_l
- ismbckata
- ismbchira
- _ismbckata
- ismbchira_l
- _ismbchira_l
- _ismbchira
dev_langs: C++
helpviewer_keywords:
- _ismbckata function
- _ismbchira function
- _ismbckata_l function
- Katakana
- ismbchira function
- _ismbchira_l function
- ismbchira_l function
- ismbdkata_l function
- Hiragana
- ismbckata function
ms.assetid: 2db388a2-be31-489b-81c8-f6bf3f0582d3
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b0e257ac4a1998e75fc47e719df2163d49654c71
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ismbchira-ismbchiral-ismbckata-ismbckatal"></a>_ismbchira, _ismbchira_l, _ismbckata, _ismbckata_l
**Kod sayfası 932 özel işlevleri**  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _ismbchira(  
   unsigned int c   
);  
int _ismbchira_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbckata(  
   unsigned int c   
);  
int _ismbckata_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `c`  
 Sınanacak karakter.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Karakter test durumu ya da 0 uymazsa mevcut değilse bu yordamlar her sıfır olmayan bir değer döndürür. Varsa `c` < = 255 ve karşılık gelen `_ismbb` yordamına (örneğin, `_ismbcalnum` karşılık gelen `_ismbbalnum`), buna karşılık gelen dönüş değeri sonucudur `_ismbb` yordamı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevlerin her biri belirli bir birden çok baytlı karakter verilen bir koşul için sınar.  
  
 Bu işlevleri sürümlerini `_l` soneki, yerel ayara bağımlı davranışlarını geçerli yerel yerine geçirilen yerel ayar kullanmasını dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
|Yordam|(Yalnızca kod sayfası 932) koşulu test|  
|-------------|-------------------------------------------|  
|`_ismbchira`|Çift baytlık Hiragana: 0x829F < =`c`< 0x82F1 =.|  
|`_ismbchira_l`|Çift baytlık Hiragana: 0x829F < =`c`< 0x82F1 =.|  
|`_ismbckata`|Çift baytlık katakana: 0x8340 < =`c`< 0x8396 =.|  
|`_ismbckata_l`|Çift baytlık katakana: 0x8340 < =`c`< 0x8396 =.|  
  
 **Son kod sayfası 932 özel**  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_ismbchira`|\<Mbstring.h >|  
|`_ismbchira_l`|\<Mbstring.h >|  
|`_ismbckata`|\<Mbstring.h >|  
|`_ismbckata_l`|\<Mbstring.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Karakter Sınıflaması](../../c-runtime-library/character-classification.md)   
 [_ismbc rutinleri](../../c-runtime-library/ismbc-routines.md)   
 [is, isw rutinleri](../../c-runtime-library/is-isw-routines.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [Çok baytlı karakter sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)