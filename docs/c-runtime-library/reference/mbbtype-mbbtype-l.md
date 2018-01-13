---
title: _mbbtype, _mbbtype_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbbtype
- _mbbtype_l
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
- _mbbtype_l
- mbbtype
- mbbtype_l
- _mbbtype
dev_langs: C++
helpviewer_keywords:
- _mbbtype function
- _mbbtype_l function
- mbbtype function
- mbbtype_l function
ms.assetid: b8e34b40-842a-4298-aa39-0bd2d8e51c2a
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ae66b1c0765f496dcfe460c4ea7ff4f84e9333ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mbbtype-mbbtypel"></a>_mbbtype, _mbbtype_l
Önceki bayt üzerinde temel byte türü döndürür.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _mbbtype(  
   unsigned char c,  
   int type   
);  
int _mbbtype_l(  
   unsigned char c,  
   int type,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `c`  
 Test etmek için karakter.  
  
 `type`  
 Sınamak için bayt türü.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_mbbtype`byte türü bir dize döndürür. Bu değeri tarafından belirtilen bağlama duyarlı bir karardır `type`, Denetim test durumu sağlar. `type`Önceki bayt dizesindeki türüdür. Aşağıdaki tabloda bildirim sabitleri Mbctype.h içinde tanımlanmıştır.  
  
|Değeri`type`|`_mbbtype`testler için|Dönüş değeri|`c`|  
|---------------------|--------------------------|------------------|---------|  
|1 dışındaki herhangi bir değer|Geçerli bir tek bayt veya baytı|`_MBC_SINGLE` (0)|Tek bayt (0x20 - 0x7E, 0xA1 - 0xDF)|  
|1 dışındaki herhangi bir değer|Geçerli bir tek bayt veya baytı|`_MBC_LEAD` (1)|Birden çok baytlı karakter baytını sağlama (0x81 - 0x9F, 0xE0 - 0xFC)|  
|1 dışındaki herhangi bir değer|Geçerli bir tek baytlı veya sağlama bayt|`_MBC_ILLEGAL`<br /><br /> ( -1)|Geçersiz karakter (hiçbir değer 0x20 dışında-0x7E, 0xA1 - 0xDF, 0x81 - 0x9F, 0xE0 - 0xFC|  
|1.|Geçerli sondaki bayt|`_MBC_TRAIL` (2)|Birden çok baytlı karakter baytını sondaki (0x40 - 0x7E, 0x80 - 0xFC)|  
|1.|Geçerli sondaki bayt|`_MBC_ILLEGAL`<br /><br /> ( -1)|Geçersiz karakter (hiçbir değer 0x20 dışında-0x7E, 0xA1 - 0xDF, 0x81 - 0x9F, 0xE0 - 0xFC|  
  
## <a name="remarks"></a>Açıklamalar  
 `_mbbtype` Fonksiyonu byte birden çok baytlı karakter türünü belirler. Varsa değerini `type` 1 dışındaki herhangi bir değer `_mbbtype` testler için geçerli bir tek baytlı veya sağlama bayt birden çok baytlı karakter. Varsa değerini `type` 1 ' dir `_mbbtype` testler için birden çok baytlı karakter geçerli sondaki bayt.  
  
 Çıkış değerini ayarı tarafından etkilenen `LC_CTYPE` yerel kategori ayarı; bkz: [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) daha fazla bilgi için. `_mbbtype` Bu işlev sürümünü kullanan geçerli yerel ayar için bu yerel ayara bağımlı davranışı; `_mbbtype_l` sürümüne sahip olduğunu aynı kullanmak dışında yerine geçirilen yerel ayar parametresi. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
 Önceki sürümlerde, `_mbbtype` idi `chkctype`. Kullanmak için yeni kod, `_mbbtype` yerine.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|---------------------|  
|`_mbbtype`|\<Mbstring.h >|\<Mbctype.h > *|  
|`_mbbtype_l`|\<Mbstring.h >|\<Mbctype.h > *|  
  
 \*Bildirim sabitleri tanımlarında, dönüş değeri olarak kullanılır.  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bayt Sınıflandırması](../../c-runtime-library/byte-classification.md)