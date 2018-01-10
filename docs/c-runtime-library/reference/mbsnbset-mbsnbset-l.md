---
title: _mbsnbset, _mbsnbset_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsnbset
- _mbsnbset_l
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
- mbsnbset
- mbsnbset_l
- _mbsnbset
- _mbsnbset_l
dev_langs: C++
helpviewer_keywords:
- tcsnset function
- _tcsnset_l function
- _mbsnbset function
- _tcsnset function
- _mbsnbset_l function
- mbsnbset_l function
- tcsnset_l function
- mbsnbset function
ms.assetid: 8e46ef75-9a56-42d2-a522-a08450c67c19
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9f868cdf5d0200df174c5df3629b5578dbf06d31
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mbsnbset-mbsnbsetl"></a>_mbsnbset, _mbsnbset_l
İlk Ayarlar `n` çok baytlı karakter dizesi belirtilen bir karakterin için bayt. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [_mbsnbset_s, _mbsnbset_s_l](../../c-runtime-library/reference/mbsnbset-s-mbsnbset-s-l.md).  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned char *_mbsnbset(  
   unsigned char *str,  
   unsigned int c,  
   size_t count   
);  
unsigned char *_mbsnbset_l(  
   unsigned char *str,  
   unsigned int c,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `str`  
 Değiştirilecek dize.  
  
 `c`  
 Tek baytlı veya çok baytlı karakter ayarı.  
  
 `count`  
 Ayarlanacak bayt sayısı.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_mbsnbset`bir işaretçi değiştirilmiş dizesi olarak döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `_mbsnbset` Ve `_mbsnbset_l` işlevleri ayarla, en fazla ilk `count` bayt `str` için `c`. Varsa `count` uzunluğundan daha büyük `str`, uzunluğu `str` yerine kullanılan `count`. Varsa `c` birden çok baytlı karakter ve tamamen tarafından belirtilen son bayt içine ayarlanamaz `count`, son bayta kalan boş bir karakter ile doldurulan. `_mbsnbset`ve `_mbsnbset_l` bir sonlandırma yerleştirmez sonunda null `str`.  
  
 `_mbsnbset`ve `_mbsnbset_l` benzer `_mbsnset`ayarlar dışında `count` bayt yerine `count` karakterlerinden `c`.  
  
 Varsa `str` olan `NULL` veya `count` sıfır açıklandığı gibi bu işlev geçersiz bir parametre özel bir durum oluşturur [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `errno` ayarlanır `EINVAL` ve işlevi döndürür `NULL`. Ayrıca, varsa `c` geçerli bir birden çok baytlı karakter değil `errno` ayarlanır `EINVAL` ve boşluk yerine kullanılır.  
  
 Çıkış değerini ayarı tarafından etkilenen `LC_CTYPE` yerel kategori ayarı; bkz: [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) daha fazla bilgi için. `_mbsnbset` Bu işlev sürümünü kullanan geçerli yerel ayar için bu yerel ayara bağımlı davranışı; `_mbsnbset_l` sürümüne sahip olduğunu aynı kullanmak dışında yerine geçirilen yerel ayar parametresi. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).  
  
 **Güvenlik Notu** bu API taşması sorundan duruma olası bir tehdit doğurur. Arabellek Taşması, sık yöntemi bir unwarranted ayrıcalıkların sonuçlanan sistem saldırı sorunlardır. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tcsnset`|`_strnset`|`_mbsnbset`|`_wcsnset`|  
|`_tcsnset_l`|`_strnset_l`|`_mbsnbset_l`|`_wcsnset_l`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_mbsnbset`|\<Mbstring.h >|  
|`_mbsnbset_l`|\<Mbstring.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_mbsnbset.c  
// compile with: /W3  
#include <mbstring.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[15] = "This is a test";  
   /* Set not more than 4 bytes of string to be *'s */  
   printf( "Before: %s\n", string );  
   _mbsnbset( string, '*', 4 ); // C4996  
   // Note; _mbsnbset is deprecated; consider _mbsnbset_s  
   printf( "After:  %s\n", string );  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
Before: This is a test  
After:  **** is a test  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)   
 [_mbsnbcat, _mbsnbcat_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [_strnset, _strnset_l, _wcsnset, _wcsnset_l, _mbsnset, _mbsnset_l](../../c-runtime-library/reference/strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)   
 [_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)