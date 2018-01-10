---
title: _ltoa_s, _ltow_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ltoa_s
- _ltow_s
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
- _ltow_s
- _ltoa_s
- ltoa_s
- ltow_s
dev_langs: C++
helpviewer_keywords:
- converting integers
- _ltoa_s function
- ltow_s function
- long integer conversion to string
- converting numbers, to strings
- ltoa_s function
- _ltow_s function
ms.assetid: d7dc61ea-1ccd-412d-b262-555a58647386
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: de078e5ad6d2488b852e14247d2d72ca751a9635
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ltoas-ltows"></a>_ltoa_s, _ltow_s
Uzun tamsayı bir dizeye dönüştürür. Sürümleri bunlar [_ltoa, _ltow](../../c-runtime-library/reference/ltoa-ltow.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t _ltoa_s(  
    long value,  
    char *str,  
    size_t sizeOfstr,  
    int radix   
);  
errno_t _ltow_s(  
    long value,  
    wchar_t *str,  
    size_t sizeOfstr,  
    int radix   
);  
template <size_t size>  
errno_t _ltoa_s(  
    long value,  
    char (&str)[size],  
    int radix   
); // C++ only  
template <size_t size>  
errno_t _ltow_s(  
    long value,  
    wchar_t (&str)[size],  
    int radix   
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  
 `value`  
 Dönüştürülecek sayı.  
  
 `str`  
 Sonuç dizesini için arabellek boyutu.  
  
 `sizeOfstr`  
 Boyutunu `str` için bayt cinsinden `_ltoa_s` veya için sözcükleri `_ltow_s`.  
  
 `radix`  
 Taban `value`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olduğunda sıfır veya bir hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 `_ltoa_s` İşlevi dönüştürür rakamı `value` null olarak sonlandırılan bir karakter dizesine ve sonuç (en fazla 33 bayt) depolar `str`. `radix` Bağımsız değişkeni belirtir tabanı `value`, 2-36 aralığında olmalıdır. Varsa `radix` eşittir 10 ve `value` olan negatif saklı dizenin ilk karakter eksi işareti (-)'dir. `_ltow_s`bir geniş karakter sürümü `_ltoa_s`; ikinci bağımsız değişkeni `_ltow_s` geniş karakter dizeler.  
  
 Varsa `str` olan bir `NULL` işaretçi veya `sizeOfstr` küçük veya ona eşit sıfır olarak açıklandığı gibi bu işlevlerin bir geçersiz parametre işleyicisi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler -1 döndürür ve ayarlayın `errno` için `EINVAL` veya `value` veya `str` uzun tamsayı aralık dışında bu işlevler -1 döndürür ve `errno` için `ERANGE`.  
  
 C++'da, bu işlevler kullanılarak şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı arabellek uzunluğu otomatik olarak Infer (boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan) ve bunlar otomatik olarak yeni, güvenli dekiler ile daha eski, güvenli olmayan işlevleri değiştirebilirsiniz. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_ltot_s`|`_ltoa_s`|`_ltoa_s`|`_ltow_s`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_ltoa_s`|\<stdlib.h >|  
|`_ltow_s`|\<stdlib.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [_itoa, _i64toa, _ui64toa, _itow, _i64tow, _ui64tow](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)   
 [_ultoa, _ultow](../../c-runtime-library/reference/ultoa-ultow.md)   
 [_ultoa_s, _ultow_s](../../c-runtime-library/reference/ultoa-s-ultow-s.md)