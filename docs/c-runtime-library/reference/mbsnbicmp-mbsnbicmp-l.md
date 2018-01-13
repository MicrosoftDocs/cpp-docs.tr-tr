---
title: _mbsnbicmp, _mbsnbicmp_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsnbicmp_l
- _mbsnbicmp
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
- _strnicmp
- _wcsnicmp_l
- _mbsnbicmp
- mbsnbicmp
- mbsnbicmp_l
- _tcsnicmp
- _strnicmp_l
- _tcsnicmp_l
- _wcsnicmp
- _mbsnbicmp_l
dev_langs: C++
helpviewer_keywords:
- _tcsnicmp_l function
- _strnicmp function
- mbsnbicmp_l function
- _wcsnicmp_l function
- _mbsnbicmp function
- _mbsnbicmp_l function
- _tcsnicmp function
- _strnicmp_l function
- mbsnbicmp function
- _wcsnicmp function
ms.assetid: ddb44974-8b0c-42f0-90d0-56c9350bae0c
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2ba2bd2e7b4857d6c1bd57f608c20e4a2a7a85d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mbsnbicmp-mbsnbicmpl"></a>_mbsnbicmp, _mbsnbicmp_l
Karşılaştırır `n` bayt iki çok baytlı karakter dizeleri ve durumu yok sayar.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _mbsnbicmp(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `string1, string2`  
 Karşılaştırılacak null ile sonlandırılmış dizeler.  
  
 `count`  
 Karşılaştırılacak bayt sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri alt dizeler arasındaki ilişkiyi gösterir.  
  
|Dönüş değeri|Açıklama|  
|------------------|-----------------|  
|< 0|`string1`substring değerinden `string2` substring.|  
|0|`string1`substring aynı `string2` substring.|  
|> 0|`string1`substring büyük `string2` substring.|  
  
 Bir hata `_mbsnbcmp` döndürür `_NLSCMPERROR`, String.h ve Mbstring.h tanımlanmış.  
  
## <a name="remarks"></a>Açıklamalar  
 `_mbsnbicmp` İşlevi gerçekleştiren bir sıralı karşılaştırma en fazla ilk `count` bayt `string1` ve `string2`. Her karakteri küçük harf dönüştürerek karşılaştırma gerçekleştirilir; `_mbsnbcmp` büyük küçük harfe duyarlı bir sürümü `_mbsnbicmp`. Karşılaştırma sonlandırma bir null karakter önce ya da dizesinde ulaşıldığında sona `count` karakter karşılaştırılır. Dizeleri eşitse, ne zaman bir sonlandırma null karakter ulaşıldığında önce ya da dizesinde `count` karakter karşılaştırılır, kısa daha düşük bir dizedir.  
  
 `_mbsnbicmp`benzer `_mbsnicmp`dizeleri kadar karşılaştırır dışında `count` karaktere göre yerine bayt.  
  
 Karakterleri içeren iki dizeyi 'Z' arasında yer alan ve ASCII tablosundaki ' bir' ('[','\\', ']', ' ^', '_' ve '\`') farklı şekilde, kendi çalışması bağlı olarak karşılaştırın. Örneğin, iki dizeyi "`ABCDE`"ve"`ABCD^`" karşılaştırma küçük harf ise bir yolu karşılaştırma ("`abcde`" > "`abcd^`") ve diğer bir yol ("`ABCDE`" < "`ABCD^`") büyük harf ise.  
  
 `_mbsnbicmp`çok baytlı karakter sıralarının göre tanıdığı [birden çok baytlı kod sayfası](../../c-runtime-library/code-pages.md) şu anda kullanımda. Geçerli yerel ayarı tarafından etkilenmez.  
  
 Her iki `string1` veya `string2` null işaretçi `_mbsnbicmp` açıklandığı gibi geçersiz bir parametre işleyiciyi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, işlevi döndürür `_NLSCMPERROR` ve ayarlar `errno` için `EINVAL`.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tcsnicmp`|`_strnicmp`|`_mbsnbicmp`|`_wcsnicmp`|  
|`_tcsnicmp_l`|`_strnicmp_l`|`_mbsnbicmp_l`|`_wcsnicmp_l`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_mbsnbicmp`|< mbstring.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [_mbsnbcmp, _mbsnbcmp_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)   
 [_mbsnbcat, _mbsnbcat_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [_mbsnbcmp, _mbsnbcmp_l](../../c-runtime-library/reference/mbsnbcmp-mbsnbcmp-l.md)   
 [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)