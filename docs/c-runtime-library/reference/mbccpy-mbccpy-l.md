---
title: _mbccpy, _mbccpy_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbccpy
- _mbccpy_l
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
- _mbccpy
- tccpy
- ftccpy
- mbccpy
- _tccpy
- _ftccpy
dev_langs: C++
helpviewer_keywords:
- _tccpy function
- _tccpy_l function
- tccpy_l function
- tccpy function
- mbccpy function
- _mbccpy_l function
- _mbccpy function
- mbccpy_l function
ms.assetid: 13f4de6e-7792-41ac-b319-dd9b135433aa
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 96273d317409f8c79740b1c7200af1533467d9f9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mbccpy-mbccpyl"></a>_mbccpy, _mbccpy_l
Birden çok baytlı karakter başka bir dizeye bir dizeden kopyalar. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [_mbccpy_s, _mbccpy_s_l](../../c-runtime-library/reference/mbccpy-s-mbccpy-s-l.md).  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void _mbccpy(  
   unsigned char *dest,  
   const unsigned char *src   
);  
void _mbccpy_l(  
   unsigned char *dest,  
   const unsigned char *src,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dest`  
 Hedef kopyalayın.  
  
 `src`  
 Kopyalamak için birden çok baytlı karakter.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="remarks"></a>Açıklamalar  
 `_mbccpy` İşlevi bir çok baytlı karakter kopyalar `src` için `dest`.  
  
 Bu işlev parametrelerini doğrular. Varsa `_mbccpy` null işaretçi geçirilen `dest` veya `src`, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `errno` ayarlanır `EINVAL`.  
  
 `_mbccpy`Geçerli yerel ayar için tüm yerel ayara bağımlı davranışı kullanır. `_mbccpy_l`aynıdır `_mbccpy` dışında `_mbccpy_l` geçirilen tüm yerel ayara bağımlı davranışını yerel ayar kullanır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
 **Güvenlik Notu** null sonlandırılmış bir dize kullanın. Sonlandırılmış dize hedef arabellek boyutunu aşmamalıdır. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795). Arabellek Taşması, sık yöntemi bir unwarranted ayrıcalıkların sonuçlanan sistem saldırı sorunlardır.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tccpy`|Makro veya satır içi işlev eşlemeleri|`_mbccpy`|Makro veya satır içi işlev eşlemeleri|  
|`_tccpy_l`|yok|`_mbccpy_l`|yok|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_mbccpy`|\<Mbctype.h >|  
|`_mbccpy_l`|\<Mbctype.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [Çok baytlı karakter sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)