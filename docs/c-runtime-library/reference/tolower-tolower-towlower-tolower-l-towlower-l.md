---
title: tolower, _tolower, towlower, _tolower_l, _towlower_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _tolower_l
- towlower
- tolower
- _tolower
- _towlower_l
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
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _totlower
- tolower
- _tolower
- towlower
dev_langs: C++
helpviewer_keywords:
- tolower_l function
- _tolower_l function
- totlower function
- string conversion, to different characters
- lowercase, converting to
- tolower function
- string conversion, case
- towlower function
- _tolower function
- _totlower function
- towlower_l function
- case, converting
- characters, converting
- _towlower_l function
ms.assetid: 86e0fc02-94ae-4472-9631-bf8e96f67b92
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7fe06748a6e349f612fdf564c9aed917e43f164b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="tolower-tolower-towlower-tolowerl-towlowerl"></a>tolower, _tolower, towlower, _tolower_l, _towlower_l
Bir karakteri küçük harfe dönüştürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int tolower(  
   int c   
);  
int _tolower(  
   int c   
);  
int towlower(  
   wint_t c   
);  
int _tolower_l(  
   int c,  
   _locale_t locale   
);  
int _towlower_l(  
   wint_t c,  
   _locale_t locale   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`c`  
 Dönüştürülecek karakter.  
  
 [in]`locale`  
 Yerel ayarlara özgü çevirisi için kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu yordamlar her bir kopyasını dönüştürür `c` alt örneğine dönüştürme mümkün ise ve sonucunu döndürür. Hiçbir değer döndürmeyen bir hata belirtmek üzere ayrılmış.  
  
## <a name="remarks"></a>Açıklamalar  
 Olası ve ilgili ise bu yordamlar her bir küçük harf belirli bir büyük harf dönüştürür. Büyük/küçük harfe dönüştürülmesini `towlower` yerel ayar özgüdür. Yalnızca geçerli yerel ilgili karakterleri durumda değiştirilir. Olmadan çalışır `_l` sonekini kullan ayarlanmış yerel ayar. Bu işlevleri sürümlerini `_l` soneki yerel bir parametre olarak geçirmesine ve ayarlanmış yerine kullanan yerel ayar. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
 Sırayla `_tolower` beklenen sonuçları elde etmek için [__isascii](../../c-runtime-library/reference/isascii-isascii-iswascii.md) ve [isupper](../../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md) her ikisi de sıfır olmayan bir değer döndürmesi gerekir.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_totlower`|`tolower`|`_mbctolower`|`towlower`|  
|`_totlower_l`|`_tolower_l`|`_mbctolower_l`|`_towlower_l`|  
  
> [!NOTE]
>  `_tolower_l`ve `_towlower_l` hiçbir yerel ayar bağımlılığı olan ve doğrudan çağrılması amaçlanmamıştır. Tarafından iç kullanım için sağlanan `_totlower_l`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`tolower`|\<CType.h >|  
|`_tolower`|\<CType.h >|  
|`towlower`|\<CType.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
 Örnekte bkz [işlevlere](../../c-runtime-library/to-functions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [is, isw rutinleri](../../c-runtime-library/is-isw-routines.md)   
 [to işlevleri](../../c-runtime-library/to-functions.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)