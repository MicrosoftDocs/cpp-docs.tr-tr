---
title: _ismbclegal, _ismbclegal_l, _ismbcsymbol, _ismbcsymbol_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _ismbclegal_l
- _ismbclegal
- _ismbcsymbol
- _ismbcsymbol_l
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
- ismbcsymbol_l
- _ismbcsymbol_l
- _ismbcsymbol
- _ismbclegal_l
- _ismbclegal
- ismbclegal_l
- ismbcsymbol
- ismbclegal
dev_langs:
- C++
helpviewer_keywords:
- ismbcsymbol function
- ismbclegal_l function
- _istlegal_l function
- istlegal function
- _istlegal function
- _ismbcsymbol function
- _ismbclegal_l function
- ismbclegal function
- ismbcsymbol_l function
- _ismbclegal function
- _ismbcsymbol_l function
- istlegal_l function
ms.assetid: 31bf1ea5-b56f-4e28-b21e-b49a2cf93ffc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ead23d6e1263086c1044e77bf20f689b2f5f2bc5
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="ismbclegal-ismbclegall-ismbcsymbol-ismbcsymboll"></a>_ismbclegal, _ismbclegal_l, _ismbcsymbol, _ismbcsymbol_l
Birden çok baytlı karakter bir yasal olup olmadığını denetler veya sembol karakter.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _ismbclegal(  
   unsigned int c   
);  
int _ismbclegal_l(  
   unsigned int c,   
   _locale_t locale  
);  
int _ismbcsymbol(  
   unsigned int c   
);  
int _ismbcsymbol_l(  
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
 Karakter test durumu ya da 0 uymazsa mevcut değilse bu yordamlar her sıfır olmayan bir değer döndürür. Varsa `c`< = 255 ve karşılık gelen `_ismbb` yordamına (örneğin, `_ismbcalnum` karşılık gelen `_ismbbalnum`), buna karşılık gelen dönüş değeri sonucudur `_ismbb` yordamı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevlerin her biri belirli bir birden çok baytlı karakter verilen bir koşul için sınar.  
  
 Bu işlevleri sürümlerini `_l` soneki, yerel ayara bağımlı davranışlarını geçerli yerel yerine geçirilen yerel ayar kullanmasını dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
|Yordam|Test durumu|Kod sayfası 932 örneği|  
|-------------|--------------------|---------------------------|  
|`_ismbclegal`|Geçerli çok baytlı|Sıfır olmayan IF ve yalnızca ilk baytı döndürür `c` 0x81-0x9F veya 0xE0 - aralıklara ikinci 0x40-0x7E veya 0x80 - aralıklara FC bayttır 0xFC, açıkken.|  
|`_ismbcsymbol`|Birden çok baytlı simgesi|Sıfır olmayan ve yalnız döndürür 0x8141 < =`c`< 0x81AC =.|  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_istlegal`|Her zaman false döndürür|`_ismbclegal`|Her zaman false döndürür.|  
|`_istlegal_l`|Her zaman false döndürür|`_ismbclegal_l`|Her zaman false döndürür.|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_ismbclegal,_ismbclegal_l`|\<Mbstring.h >|  
|`_ismbcsymbol,_ismbcsymbol_l`|\<Mbstring.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Karakter Sınıflaması](../../c-runtime-library/character-classification.md)   
 [_ismbc rutinleri](../../c-runtime-library/ismbc-routines.md)   
 [is, isw rutinleri](../../c-runtime-library/is-isw-routines.md)   
 [_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)