---
title: _ltoa, _ltow | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ltoa
- _ltow
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
apitype: DLLExport
f1_keywords:
- ltow
- _ltot
- _ltoa
- _ltow
dev_langs: C++
helpviewer_keywords:
- converting integers
- _ltoa function
- _ltow function
- ltow function
- ltoa function
- long integer conversion to string
- converting numbers, to strings
ms.assetid: 14036104-2c25-4759-87c0-918ed8521e47
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7e7ae79ed3505e4570b453e7fd56b68730010388
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ltoa-ltow"></a>_ltoa, _ltow
Uzun tamsayı bir dizeye dönüştürür. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [_ltoa_s, _ltow_s](../../c-runtime-library/reference/ltoa-s-ltow-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
char *_ltoa(  
   long value,  
   char *str,  
   int radix   
);  
wchar_t *_ltow(  
   long value,  
   wchar_t *str,  
   int radix   
);  
template <size_t size>  
char *_ltoa(  
   long value,  
   char (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
wchar_t *_ltow(  
   long value,  
   wchar_t (&str)[size],  
   int radix   
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  
 `value`  
 Dönüştürülecek sayı.  
  
 `str`  
 Sonuç dize.  
  
 `radix`  
 Taban `value`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu işlevlerin her biri için bir işaretçi döndürür `str`. Döndürülen hata yoktur.  
  
## <a name="remarks"></a>Açıklamalar  
 `_ltoa` İşlevi dönüştürür rakamı `value` null olarak sonlandırılan bir karakter dizesine ve sonuç (en fazla 33 bayt) depolar `str`. `radix` Bağımsız değişkeni belirtir tabanı `value`, 2-36 aralığında olmalıdır. Varsa `radix` eşittir 10 ve `value` olan negatif saklı dizenin ilk karakter eksi işareti (-)'dir. `_ltow`bir joker karakter sürümü `_ltoa`; ikinci bağımsız değişkeni ve dönüş değeri `_ltow` joker karakter dizelerdir. Bu işlevlerin her biri Microsoft özgüdür.  
  
> [!IMPORTANT]
>  Arabellek aşırı çalıştırmaları önlemek için emin `str` arabellek dönüştürülen basamak artı sonunda null karakteri ve bir oturum karakter tutabilecek kadar büyük.  
  
 C++'da, bu işlevler şablon aşırı yüklemeleri vardır. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_ltot`|`_ltoa`|`_ltoa`|`_ltow`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_ltoa`|\<stdlib.h >|  
|`_ltow`|\<stdlib.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [_itoa](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [_itoa, _i64toa, _ui64toa, _itow, _i64tow, _ui64tow](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)   
 [_ultoa, _ultow](../../c-runtime-library/reference/ultoa-ultow.md)