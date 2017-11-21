---
title: toupper, _toupper, towupper, _toupper_l, _towupper_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _toupper_l
- towupper
- toupper
- _towupper_l
- _toupper
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
- towupper
- _toupper
- _totupper
- toupper
dev_langs: C++
helpviewer_keywords:
- _toupper function
- towupper function
- uppercase, converting strings to
- totupper function
- string conversion, to different characters
- towupper_l function
- toupper_l function
- string conversion, case
- _toupper_l function
- _towupper_l function
- _totupper function
- case, converting
- characters, converting
- toupper function
ms.assetid: cdef1b0f-b19c-4d11-b7d2-cf6334c9b6cc
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a40472922e61cbcc6c5788d575305613ae300e1e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="toupper-toupper-towupper-toupperl-towupperl"></a>toupper, _toupper, towupper, _toupper_l, _towupper_l
Karakter büyük harfe Dönüştür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int toupper(  
   int c   
);  
int _toupper(  
   int c   
);  
int towupper(  
   wint_t c   
);  
int _toupper_l(  
   int c ,  
   _locale_t locale  
);  
int _towupper_l(  
   wint_t c ,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `c`  
 Dönüştürülecek karakter.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu yordamlar her bir kopyasını dönüştürür `c`, mümkünse ve sonucu döndürür.  
  
 Varsa `c` geniş karakter olduğu `iswlower` sıfır olmayan olduğundan ve karşılık gelen bir geniş karakter olan `iswupper` sıfır olmayan, olan `towupper` karşılık gelen döndürür geniş karakter; Aksi takdirde `towupper` döndürür`c`değişmez.  
  
 Hiçbir değer döndürmeyen bir hata belirtmek üzere ayrılmış.  
  
 Sırayla `toupper` beklenen sonuçları elde etmek için [__isascii](../../c-runtime-library/reference/isascii-isascii-iswascii.md) ve [islower](../../c-runtime-library/reference/islower-iswlower-islower-l-iswlower-l.md) her ikisi de sıfır olmayan bir değer döndürmesi gerekir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yordamlar her mümkünse belirli bir küçük harf bir büyük harfe dönüştürür ve gerekli. Büyük/küçük harfe dönüştürülmesini `towupper` yerel ayar özgüdür. Yalnızca geçerli yerel ilgili karakterleri durumda değiştirilir. Olmadan çalışır `_l` sonekini kullan ayarlanmış yerel ayar. Bu işlevleri sürümlerini `_l` soneki yerel bir parametre olarak geçirmesine ve ayarlanmış yerine kullanan yerel ayar. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
 Sırayla `toupper` beklenen sonuçları elde etmek için [__isascii](../../c-runtime-library/reference/isascii-isascii-iswascii.md) ve [isupper](../../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md) her ikisi de sıfır olmayan bir değer döndürmesi gerekir.  
  
 [Veri dönüştürme yordamları](../../c-runtime-library/data-conversion.md)  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_totupper`|`toupper`|`_mbctoupper`|`towupper`|  
|`_totupper_l`|`_toupper_l`|`_mbctoupper_l`|`_towupper_l`|  
  
> [!NOTE]
>  `_toupper_l`ve `_towupper_l` hiçbir yerel ayar bağımlılığı olan ve doğrudan çağrılması amaçlanmamıştır. Tarafından iç kullanım için sağlanan `_totupper_l`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`toupper`|\<CType.h >|  
|`_toupper`|\<CType.h >|  
|`towupper`|\<CType.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
 Örnekte bkz [işlevlere](../../c-runtime-library/to-functions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [is, isw rutinleri](../../c-runtime-library/is-isw-routines.md)   
 [to işlevleri](../../c-runtime-library/to-functions.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [Çok baytlı karakter sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)