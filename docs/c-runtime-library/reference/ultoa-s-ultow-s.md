---
title: _ultoa_s, _ultow_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _ultow_s
- _ultoa_s
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _ultow_s
- ultoa_s
- ultow_s
- _ultoa_s
dev_langs:
- C++
helpviewer_keywords:
- _ultoa_s function
- converting integers
- integers, converting
- _ultow_s function
- ultoa_s function
- converting numbers, to strings
- ultow_s function
ms.assetid: 606ce905-6752-46ac-a15a-bdc22920e1d4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1e6b882e8e4017410e0f377aaf4b49b658b39afa
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="ultoas-ultows"></a>_ultoa_s, _ultow_s
İmzasız uzun tamsayı bir dizeye dönüştürür. Sürümleri bunlar [_ultoa, _ultow](../../c-runtime-library/reference/ultoa-ultow.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t _ultoa_s(  
    unsigned long value,  
    char *str,  
    size_t sizeOfstr,  
    int radix   
);  
errno_t _ultow_s(  
    unsigned long value,  
    wchar_t *str,  
    size_t sizeOfstr,  
    int radix   
);  
template <size_t size>  
errno_t _ultoa_s(  
    unsigned long value,  
    char (&str)[size],  
    int radix   
); // C++ only  
template <size_t size>  
errno_t _ultow_s(  
    unsigned long value,  
    wchar_t (&str)[size],  
    int radix   
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  
 `value`  
 Dönüştürülecek sayı.  
  
 `str`  
 Sonuç dize.  
  
 `sizeOfstr`  
 Boyutunu `str` için bayt cinsinden `_ultoa_s` veya için sözcükleri `_ultow_s`.  
  
 `radix`  
 Taban `value`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olduğunda sıfır veya bir hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 `_ultoa_s` İşlevi dönüştürür rakamı `value` null olarak sonlandırılan bir karakter dizesine ve sonuç (en fazla 33 bayt) depolar `str`. `radix` Bağımsız değişkeni belirtir tabanı `value`, 2-36 aralığında olmalıdır. `_ultow_s` bir geniş karakter sürümü `_ultoa_s`; ikinci bağımsız değişkeni `_ultow_s` geniş karakter dizeler.  
  
 Varsa `str` olan bir `NULL` işaretçisi veya `sizeOfstr` küçük veya ona eşit sıfır olarak geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler -1 döndürür ve `errno` için `EINVAL` veya `value` veya `str` uzun tamsayı aralık dışında bu işlevler bir -1 döndürür ve ayarlayın `errno` için `ERANGE`.  
  
 C++'da, bu işlevler kullanılarak şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı arabellek uzunluğu otomatik olarak Infer (boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan) ve bunlar otomatik olarak yeni, güvenli dekiler ile daha eski, güvenli olmayan işlevleri değiştirebilirsiniz. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ultot_s`|`_ultoa_s`|`_ultoa_s`|`_ultow_s`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_ultoa_s`|\<stdlib.h>|  
|`_ultow_s`|\<stdlib.h>|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [_ultoa, _ultow](../../c-runtime-library/reference/ultoa-ultow.md)   
 [_ltoa, _ltow](../../c-runtime-library/reference/ltoa-ltow.md)   
 [_ltoa_s, _ltow_s](../../c-runtime-library/reference/ltoa-s-ltow-s.md)   
 [_ltoa_s, _ltow_s](../../c-runtime-library/reference/ltoa-s-ltow-s.md)