---
title: strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- wcscoll
- _mbscoll
- _mbscoll_l
- strcoll
- _strcoll_l
- _wcscoll_l
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wcscoll
- _mbscoll
- _tcscoll
- _ftcscoll
dev_langs:
- C++
helpviewer_keywords:
- code pages, using for string comparisons
- mbscoll function
- wcscoll_l function
- ftcscoll function
- wcscoll function
- _strcoll_l function
- tcscoll function
- _ftcscoll function
- _tcscoll function
- _wcscoll_l function
- _mbscoll function
- strcoll_l function
- strcoll functions
- strings [C++], comparing by code page
ms.assetid: 900a7540-c7ec-4c2f-b292-7a85f63e3fe8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0db4e70e4bdb7642c5df0c94c007eacdfd33ea9d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="strcoll-wcscoll-mbscoll-strcolll-wcscolll-mbscolll"></a>strcoll, wcscoll, _mbscoll, _strcoll_l, _wcscoll_l, _mbscoll_l
Geçerli yerel veya belirtilen LC_COLLATE dönüştürme durumu kategorisinin kullanarak dizeleri karşılaştırır.  
  
> [!IMPORTANT]
>  `_mbscoll` ve `_mbscoll_l` Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int strcoll(  
   const char *string1,  
   const char *string2   
);  
int wcscoll(  
   const wchar_t *string1,  
   const wchar_t *string2   
);  
int _mbscoll(  
   const unsigned char *string1,  
   const unsigned char *string2   
);  
int _strcoll_l(  
   const char *string1,  
   const char *string2,  
   _locale_t locale   
);  
int wcscoll_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   _locale_t locale   
);  
int _mbscoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   _locale_t locale   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `string1`, `string2`  
 Karşılaştırılacak null ile sonlandırılmış dizeler.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu işlevlerin her biri arasındaki ilişkiyi gösteren bir değer döndürür `string1` için `string2`aşağıdaki gibi.  
  
|Dönüş değeri|Dize2 Dize1 ilişkisi|  
|------------------|----------------------------------------|  
|< 0|`string1` Küçüktür `string2`|  
|0|`string1` aynı `string2`|  
|> 0|`string1` Büyüktür `string2`|  
  
 Bunların her biri döndürür işlevleri `_NLSCMPERROR` bir hata. Kullanılacak `_NLSCMPERROR`, her iki dize içerir. H veya MBSTRING. H. `wcscoll` ya da başarısız `string1` veya `string2` null ya da etki alanının harmanlama sırası dışında joker karakter kodları içerir. Hata oluştuğunda `wcscoll` ayarlayabilir `errno` için `EINVAL`. Çağrı sırasında bir hata olup olmadığını denetlemek için `wcscoll`ayarlayın `errno` 0 ve denetleyin `errno` çağırdıktan sonra `wcscoll`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevlerin her biri bir büyük küçük harfe duyarlı karşılaştırma gerçekleştirir `string1` ve `string2` şu anda kullanımda kod sayfasına göre. Bu işlevler yalnızca, geçerli kod sayfası karakter arasında bir fark sipariş ve lexicographic karakter sırası ayarlayabilir ve bu fark dize karşılaştırma için ilgilendirir olduğunda kullanılmalıdır.  
  
 Tüm bu işlevlerin kendi parametreleri doğrulayın. Her iki `string1` veya `string2` null işaretçinin veya `count` değerinden daha büyük `INT_MAX`, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md) . Yürütme devam etmek için izin verilip verilmediğini, bu işlevlerin dönüş `_NLSCMPERROR` ve `errno` için `EINVAL`.  
  
 Her yerel ayar karakter sırası için farklı kurallar olduğundan, iki dizeyi karşılaştırması yerel ayara bağımlı bir işlemdir. Bu işlevlerin sürümleri `_l` sonekini kullanın Bu yerel ayara bağımlı davranış geçerli iş parçacığının yerel; sürümleriyle `_l` kullandıkları dışında sonek aynı soneki olmayan karşılık gelen işlevi yerel ayar geçerli yerel yerine bir parametre olarak geçirilen. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcscoll`|`strcoll`|`_mbscoll`|`wcscoll`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`strcoll`|\<String.h >|  
|`wcscoll`|\<wchar.h >, \<string.h >|  
|`_mbscoll`, `_mbscoll_l`|\<Mbstring.h >|  
|`_strcoll_l`|\<String.h >|  
|`_wcscoll_l`|\<wchar.h >, \<string.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)   
 [strcoll işlevleri](../../c-runtime-library/strcoll-functions.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [_mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l](../../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)   
 [strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)