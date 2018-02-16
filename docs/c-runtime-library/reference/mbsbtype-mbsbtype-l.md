---
title: _mbsbtype, _mbsbtype_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _mbsbtype_l
- _mbsbtype
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
- mbsbtype
- mbsbtype_l
- _mbsbtype_l
- _mbsbtype
dev_langs:
- C++
helpviewer_keywords:
- _mbsbtype function
- mbsbtype function
- _mbsbtype_l function
- mbsbtype_l function
ms.assetid: 0d5dd91a-d32d-4f98-ac57-98dfc9e98eac
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e25372291d4069e2fda5130a7166b1b4da8eb525
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="mbsbtype-mbsbtypel"></a>_mbsbtype, _mbsbtype_l
Dize içinde bayt türünü döndürür.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _mbsbtype(  
   const unsigned char *mbstr,  
   size_t count   
);  
int _mbsbtype_l(  
   const unsigned char *mbstr,  
   size_t count,  
   _locale_t locale   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `mbstr`  
 Birden çok baytlı karakter dizisi adresidir.  
  
 `count`  
 Dize başından uzaklık bayt.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_mbsbtype` ve `_mbsbtype_l` belirtilen bayt sınama sonucu gösteren bir Integer değeri döndürür. Aşağıdaki tabloda bildirim sabitleri Mbctype.h içinde tanımlanmıştır.  
  
|Dönüş değeri|Byte türü|  
|------------------|---------------|  
|`_MBC_SINGLE` (0)|Tek baytlı karakter. Örneğin, kod sayfası 932, içinde `_mbsbtype` belirtilen bayt 0xDF 0x20-0x7E veya 0xA1 - aralığında ise 0 döndürür.|  
|`_MBC_LEAD` (1)|Birden çok baytlı karakter baytını yol açar. Örneğin, kod sayfası 932, içinde `_mbsbtype` belirtilen bayt 0xFC 0x81-0x9F veya 0xE0 - aralığında ise 1 döndürür.|  
|`_MBC_TRAIL` (2)|Birden çok baytlı karakter izleyen baytı. Örneğin, kod sayfası 932, içinde `_mbsbtype` belirtilen bayt 0xFC 0x40-0x7E veya 0x80 - aralığında varsa 2 değerini döndürür.|  
|`_MBC_ILLEGAL` (-1)|`NULL` dize, geçersiz bir karakter veya `NULL` bayt uzaklığındaki önce bulunan bayt `count` içinde `mbstr`.|  
  
## <a name="remarks"></a>Açıklamalar  
 `_mbsbtype` Fonksiyonu byte birden çok baytlı karakter dizesi içinde türünü belirler. İşlevi yalnızca bayt uzaklığındaki inceler `count` içinde `mbstr`, belirtilen bayt önce geçersiz karakterler yoksayılıyor.  
  
 Çıkış değerini ayarı tarafından etkilenen `LC_CTYPE` yerel kategori ayarı; bkz: [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlev olmadan sürümü `_l` soneki için bu yerel ayara bağımlı davranışı; geçerli yerel ayarı kullanır sürümüyle `_l` kullanmak dışında bunun yerine geçirilen yerel ayar parametresi soneki aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
 Giriş dizesi ise `NULL`, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `errno` ayarlanır `EINVAL` ve işlevi döndürür `_MBC_ILLEGAL`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|---------------------|  
|`_mbsbtype`|\<Mbstring.h >|\<Mbctype.h > *|  
|`_mbsbtype_l`|\<Mbstring.h >|\<Mbctype.h > *|  
  
 \* Dönüş değerleri olarak kullanılan bildirim sabitler için.  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bayt Sınıflandırması](../../c-runtime-library/byte-classification.md)