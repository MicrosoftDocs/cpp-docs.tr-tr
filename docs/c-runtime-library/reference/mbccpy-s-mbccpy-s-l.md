---
title: _mbccpy_s, _mbccpy_s_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbccpy_s
- _mbccpy_s_l
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
- _mbccpy_s_l
- mbccpy_s_l
- mbccpy_s
- _mbccpy_s
dev_langs: C++
helpviewer_keywords:
- tccpy_s_l function
- _tccpy_s function
- _mbccpy_s function
- mbccpy_s function
- tccpy_s function
- mbccpy_s_l function
- _tccpy_s_l function
- _mbccpy_s_l function
ms.assetid: b6e965fa-53c1-4ec3-85ef-a1c4b4f2b2da
caps.latest.revision: "30"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 04c9091214928ecf7122868992974a0b0af9d3c6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="mbccpys-mbccpysl"></a>_mbccpy_s, _mbccpy_s_l
Tek baytlı karakter başka bir dizeye bir dizeden kopyalar. Bu sürümleri [_mbccpy, _mbccpy_l](../../c-runtime-library/reference/mbccpy-mbccpy-l.md) açıklandığı gibi güvenlik geliştirmeleri sahip [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t _mbccpy_s(  
   unsigned char *dest,  
   size_t buffSizeInBytes,  
   int * pCopied,  
   const unsigned char *src   
);  
errno_t _mbccpy_s_l(  
   unsigned char *dest,  
   size_t buffSizeInBytes,  
   int * pCopied,  
   const unsigned char *src,  
   locale_t locale  
);  
template <size_t size>  
errno_t _mbccpy_s(  
   unsigned char (&dest)[size],  
   int * pCopied,  
   const unsigned char *src   
); // C++ only  
template <size_t size>  
errno_t _mbccpy_s_l(  
   unsigned char (&dest)[size],  
   int * pCopied,  
   const unsigned char *src,  
   locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  
 [out]`dest`  
 Hedef kopyalayın.  
  
 [in]`buffSizeInBytes`  
 Hedef arabellek boyutu.  
  
 [out]`pCopied`  
 Bayt kopyalanan (1 veya 2 başarılı olursa) sayısı ile doldurulur. Geçirmek `NULL` numarası hakkında önemli değil durumunda.  
  
 [in]`src`  
 Kopyalamak için birden çok baytlı karakter.  
  
 [in]`locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır; hatasında bir hata kodu. Varsa `src` veya `dest` olan `NULL`, ya da birden fazla `buffSizeinBytes` bayt için kopyalanması `dest`, sonra da açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, işlevlerin dönüş `EINVAL` ve `errno` ayarlanır `EINVAL`.  
  
## <a name="remarks"></a>Açıklamalar  
 `_mbccpy_s` İşlevi bir çok baytlı karakter kopyalar `src` için `dest`. Varsa `src` birden çok baytlı karakter örtük bir çağrı tarafından belirlendiği bayt göstermiyor [_ismbblead](../../c-runtime-library/reference/ismbblead-ismbblead-l.md), ardından tek bayt, `src` noktalarına kopyalanır. Varsa `src` baytı ancak aşağıdaki bayt noktalarına 0 ve böylece geçersiz sonra 0 kopyalanır `dest`, `errno` ayarlanır `EILSEQ`, ve işlevi döndürür `EILSEQ`.  
  
 `_mbccpy_s`null Sonlandırıcı append değil; Ancak, varsa `src` bu null kopyalanır sonra bir null karakter işaret `dest` (yalnızca normal tek baytlı kopyasını budur).  
  
 Değer `pCopied` kopyalanan bayt sayısı ile doldurulur. İşlem başarılı olursa olası değerler şunlardır: 1 ve 2. Varsa `NULL` geçirilir, bu parametre yoksayılır.  
  
|`src`|kopyalanır`dest`|`pCopied`|Dönüş değeri|  
|-----------|----------------------|---------------|------------------|  
|ön bayt|ön bayt|1.|0|  
|0|0|1.|0|  
|baytı-0 olmayan tarafından izlenen|baytı-0 olmayan tarafından izlenen|2|0|  
|0 ve ardından ön bayt|0|1.|`EILSEQ`|  
  
 İkinci satır bir özel durum ilk olduğuna dikkat edin. Ayrıca tablo varsayar Not `buffSizeInBytes`  >=  `pCopied`.  
  
 `_mbccpy_s`Geçerli yerel ayar için tüm yerel ayara bağımlı davranışı kullanır. `_mbccpy_s_l`aynıdır `_mbccpy_s` dışında `_mbccpy_s_l` geçirilen tüm yerel ayara bağımlı davranışını yerel ayar kullanır.  
  
 C++'da, bu işlevler kullanılarak şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı, boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan arabellek uzunluğu bir otomatik olarak Infer. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tccpy_s`|Makro veya satır içi işlev eşlenir.|`_mbccpy_s`|Makro veya satır içi işlev eşlenir.|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_mbccpy_s`|\<Mbstring.h >|  
|`_mbccpy_s_l`|\<Mbstring.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [Çok baytlı karakter sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)