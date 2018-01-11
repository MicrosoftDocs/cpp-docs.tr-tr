---
title: wcsrtombs | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: wcsrtombs
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
f1_keywords: wcsrtombs
dev_langs: C++
helpviewer_keywords:
- wcsrtombs function
- string conversion, wide characters
- wide characters, strings
ms.assetid: a8d21fec-0d36-4085-9d81-9b1c61c7259d
caps.latest.revision: "26"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7fb18e5f66f431afb86e86815f50217782902b8d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="wcsrtombs"></a>wcsrtombs
Geniş karakter dizesi, birden çok baytlı karakter dizesi gösterimine dönüştürür. Bu işlev daha güvenli bir sürümü kullanılabilir; bkz: [wcsrtombs_s](../../c-runtime-library/reference/wcsrtombs-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
size_t wcsrtombs(  
   char *mbstr,  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
);  
template <size_t size>  
size_t wcsrtombs(  
   char (&mbstr)[size],  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  
 [out]`mbstr`  
 Elde edilen birden çok baytlı karakter dizesi'nın adres konumunu dönüştürülür.  
  
 [in]`wcstr`  
 Dolaylı olarak noktalarına dönüştürülecek geniş karakter dizesi konumu.  
  
 [in]`count`  
 Dönüştürülecek karakter sayısı.  
  
 [in]`mbstate`  
 Bir işaretçi bir `mbstate_t` dönüştürme durum nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bayt sayısı başarılı bir şekilde, bir hata oluştuysa null bayt (varsa), aksi takdirde -1 sonlandırma null hariç dönüştürülen döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `wcsrtombs` İşlevi dönüştürür bulunan belirtilen dönüşüm durumunu'den başlayarak, geniş karakter dizesi `mbstate`, içinde işaret değerlerden dolaylı `wcstr`, adresini içine `mbstr`. Dönüştürme için her bir karakteri kadar devam eder: olmayan karşılık gelen bir karakter karşılaşıldığında geniş karakter sonlandırma null karşılaştı sonra veya bir sonraki karakteri yer alan sınırı aşabilir `count`. Varsa `wcsrtombs` joker karakter null karakteri (M '\0') önce veya ne zaman karşılaşırsa `count` oluşur, dönüştürür, 8 bit 0 ve durdurur.  
  
 Bu nedenle, birden çok baytlı karakter dizesi adresindeki `mbstr` null-yalnızca sonlandırılır `wcsrtombs` geniş karakter null karakter dönüştürme sırasında karşılaşır. Dizileri gösterdiği varsa `wcstr` ve `mbstr` üst üste, davranışını `wcsrtombs` tanımlanmadı. `wcsrtombs`Geçerli yerel LC_TYPE kategoriye göre etkilenir.  
  
 `wcsrtombs` İşlevi farklı olarak [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md) kendi restartability tarafından. Dönüştürme durumu depolanan `mbstate` sonraki çağrılar aynı ya da yeniden başlatılabilir diğer işlevleri için. Sonuçlar, yeniden başlatılabilir ve nonrestartable işlevleri kullanımını kullanırken tanımlanmamış.  Örneğin, bir uygulama kullanırsınız `wcsrlen` yerine `wcsnlen`, bir sonraki çağrı, `wcsrtombs` yerine kullanılan `wcstombs`.  
  
 Varsa `mbstr` bağımsız değişkeni `NULL`, `wcsrtombs` gereken boyut hedef dizesi bayt cinsinden döndürür. Varsa `mbstate` null, iç `mbstate_t` dönüştürme durumu kullanılır. Varsa bir karakter dizisi `wchar` karşılık gelen çok baytlı yok karakter gösterimi, -1 döndürülür ve `errno` ayarlanır `EILSEQ`.  
  
 C++'da, bu işlev bu işlevin yeni, güvenli karşılık gelen çağıran bir şablon aşırı sahiptir. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="exceptions"></a>Özel Durumlar  
 `wcsrtombs` İşlevi, geçerli iş parçacığının hiçbir işlev çağrıları sürece çoklu iş parçacığı güvenli olduğu `setlocale` bu işlev yürütülürken ve `mbstate` null değil.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_wcsrtombs.cpp  
// compile with: /W3  
// This code example converts a wide  
// character string into a multibyte  
// character string.  
  
#include <stdio.h>  
#include <memory.h>  
#include <wchar.h>  
#include <errno.h>  
  
#define MB_BUFFER_SIZE 100  
  
int main()  
{  
    const wchar_t   wcString[] =   
                    {L"Every good boy does fine."};  
    const wchar_t   *wcsIndirectString = wcString;  
    char            mbString[MB_BUFFER_SIZE];  
    size_t          countConverted;  
    mbstate_t       mbstate;  
  
    // Reset to initial shift state  
    ::memset((void*)&mbstate, 0, sizeof(mbstate));  
  
    countConverted = wcsrtombs(mbString, &wcsIndirectString,  
                               MB_BUFFER_SIZE, &mbstate); // C4996  
    // Note: wcsrtombs is deprecated; consider using wcsrtombs_s  
    if (errno == EILSEQ)  
    {  
        printf( "An encoding error was detected in the string.\n" );  
    }  
    else   
    {  
        printf( "The string was successfuly converted.\n" );  
    }  
}  
```  
  
```Output  
The string was successfuly converted.  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`wcsrtombs`|\<wchar.h >|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [Çok baytlı karakter sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb_s](../../c-runtime-library/reference/wcrtomb-s.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)