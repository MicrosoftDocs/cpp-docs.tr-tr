---
title: _mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsnbicoll_l
- _mbsnbcoll_l
- _mbsnbcoll
- _mbsnbicoll
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
- mbsnbicoll
- mbsnbcoll
- mbsnbicoll_l
- _mbsnbcoll
- _mbsnbicoll
- _ftcsnicoll
- _ftcsncoll
- mbsnbcoll_l
dev_langs: C++
helpviewer_keywords:
- _mbsnbcoll_l function
- mbsnbcoll_l function
- _mbsnbcoll function
- _tcsnicoll function
- mbsnbcoll function
- mbsnbicoll_l function
- mbsnbicoll function
- _tcsncoll function
- _mbsnbicoll function
- _mbsnbicoll_l function
- tcsncoll function
- tcsnicoll function
ms.assetid: d139ed63-ccba-4458-baa2-61cbcef03e94
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 501c2d1fe8978b75d1f5e0321f12d5a933a00d75
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="mbsnbcoll-mbsnbcolll-mbsnbicoll-mbsnbicolll"></a>_mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l
Karşılaştırır `n` birden çok baytlı kod sayfası bilgileri kullanarak iki çok baytlı karakter dizeleri bayt.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _mbsnbcoll(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _mbsnbcoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,  
   _locale_t locale  
);  
int _mbsnbicoll(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _mbsnbicoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `string1, string2`  
 Karşılaştırılacak dizeleri.  
  
 `count`  
 Karşılaştırılacak bayt sayısı.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Alt dizeler ilişkisi dönüş değerini gösteren `string1` ve `string2`.  
  
|Dönüş değeri|Açıklama|  
|------------------|-----------------|  
|< 0|`string1`substring değerinden `string2` substring.|  
|0|`string1`substring aynı `string2` substring.|  
|> 0|`string1`substring büyük `string2` substring.|  
  
 Varsa `string1` veya `string2` olan `NULL` veya `count` değerinden daha büyük `INT_MAX`, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, bu işlevlerin dönüş `_NLSCMPERROR` ve `errno` için `EINVAL`. Kullanılacak `_NLSCMPERROR`, String.h veya Mbstring.h içerir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevlerin her biri, en fazla ilk harmanlar `count` bayt cinsinden `string1` ve `string2` ve sonuçta elde edilen alt dizeler arasındaki ilişkiyi gösteren bir değer döndürür `string1` ve `string2`. Varsa dizenin son bayt `string1` veya `string2` sağlama bayt Karşılaştırmada bulunmaz; bu işlevler yalnızca tam karakterler alt dizeler karşılaştırın. `_mbsnbicoll`büyük küçük harf duyarsız bir sürümü `_mbsnbcoll`. Gibi `_mbsnbcmp` ve `_mbsnbicmp`, `_mbsnbcoll` ve `_mbsnbicoll` çok baytlı tarafından belirtilen lexicographic sırasına göre iki çok baytlı karakter dizeleri collate [kod sayfası](../../c-runtime-library/code-pages.md) şu anda kullanımda.  
  
 Bazı kod sayfaları ve karşılık gelen karakter kümesi için karakter kümesinden karakter sırasını lexicographic karakter siparişte farklı olabilir. "C" yerel ayarını durum böyle değildir: ASCII karakter kümesinden karakter sırasını karakterleri lexicographic sırasını ile aynıdır. Ancak, bazı Avrupa kod sayfalarında, örneğin, karakter 'a' (değer 0x61) karakter 'ä ''yı (değer 0xE4) karakter kümesini, karakter önündeki 'ä' önündeki karakter 'a' lexicographically. Bu tür bir örneğini bayt tarafından dizeleri lexicographic karşılaştırması gerçekleştirmek için kullanın `_mbsnbcoll` yerine `_mbsnbcmp`; yalnızca dize eşitlik için denetleyin, kullanmak için `_mbsnbcmp`.  
  
 Çünkü `coll` işlevleri collate dizeleri karşılaştırma, lexicographically için ise `cmp` işlevleri yalnızca dize eşitlik için test `coll` işlevlerdir karşılık gelen daha çok daha yavaş `cmp` sürümleri. Bu nedenle, `coll` işlevleri yalnızca geçerli kod sayfası karakter kümesi sırasını ve lexicographic karakter sırası arasında bir fark yoktur ve bu fark karşılaştırma için ilgi olduğunda kullanılmalıdır.  
  
 Çıkış değerini ayarı tarafından etkilenen `LC_CTYPE` yerel kategori ayarı; bkz: [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin sürümleri `_l` bu yerel ayara bağımlı davranış geçerli yerel kullanılmak soneki; sürümleriyle `_l` soneki, bunun yerine geçirilen yerel ayar parametresi kullanmasını dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tcsncoll`|[_strncoll](../../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|`_mbsnbcoll`|[_wcsncoll](../../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|  
|`_tcsncoll_l`|[_strncoll, _wcsncoll, _mbsncoll, _strncoll_l, _wcsncoll_l, _mbsncoll_l](../../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|`_mbsnbcoll_l`|[_wcsncoll_l](../../c-runtime-library/reference/strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|  
|`_tcsnicoll`|[_strnicoll](../../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|`_mbsnbicoll`|[_wcsnicoll](../../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|  
|`_tcsnicoll_l`|[_strnicoll_l](../../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|`_mbsnbicoll_l`|[_wcsnicoll_l](../../c-runtime-library/reference/strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_mbsnbcoll`|\<Mbstring.h >|  
|`_mbsnbcoll_l`|\<Mbstring.h >|  
|`_mbsnbicoll`|\<Mbstring.h >|  
|`_mbsnbicoll_l`|\<Mbstring.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)   
 [_mbsnbcat, _mbsnbcat_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [_mbsnbcmp, _mbsnbcmp_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [_mbsnbicmp, _mbsnbicmp_l](../../c-runtime-library/reference/mbsnbicmp-mbsnbicmp-l.md)   
 [strcoll işlevleri](../../c-runtime-library/strcoll-functions.md)   
 [strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)