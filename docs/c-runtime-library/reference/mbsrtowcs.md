---
title: mbsrtowcs | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: mbsrtowcs
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
f1_keywords: mbsrtowcs
dev_langs: C++
helpviewer_keywords: mbsrtowcs function
ms.assetid: f3a29de8-e36e-425b-a7fa-a258e6d7909d
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6b51f8ccbac43e30202598499613d3b1c7c6e0a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mbsrtowcs"></a>mbsrtowcs
Çok baytlı karakter dizesi geçerli yerel birden çok baytlı karakter ortasında yeniden özelliği ile ilgili geniş karakter dizeye dönüştürür. Bu işlev daha güvenli bir sürümü kullanılabilir; bkz: [mbsrtowcs_s](../../c-runtime-library/reference/mbsrtowcs-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
size_t mbsrtowcs(  
   wchar_t *wcstr,  
   const char **mbstr,  
   sizeof count,  
   mbstate_t *mbstate  
);  
template <size_t size>  
size_t mbsrtowcs(  
   wchar_t (&wcstr)[size],  
   const char **mbstr,  
   sizeof count,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  
 [out]`wcstr`  
 Ortaya çıkan dönüştürülmüş geniş karakter dizesi depolamak için adres.  
  
 [içinde out]`mbstr`  
 Dönüştürme için birden çok baytlı karakter dizesi konuma dolaylı işaretçi.  
  
 [in]`count`  
 En fazla dönüştürmek ve depolamak için (bayt değil) karakter sayısını `wcstr`.  
  
 [içinde out]`mbstate`  
 Bir işaretçi bir `mbstate_t` dönüştürme durum nesnesi. Bu değer null işaretçi ise, bir statik iç dönüştürme durumu nesnesi kullanılır. Çünkü iç `mbstate_t` nesnesi iş parçacığı açısından güvenli değil, her zaman kendi geçirdiğiniz olmasını öneririz `mbstate` parametresi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sonlandırma null karakteri varsa hariç başarıyla dönüştürüldü karakterlerin sayısını döndürür. Döndürür (bir hata oluştu ve ayarlar size_t)(-1) `errno` EILSEQ için.  
  
## <a name="remarks"></a>Açıklamalar  
 `mbsrtowcs` İşlevi dönüştürür dolaylı olarak gösterdiği birden çok baytlı karakter dizesi `mbstr`, geniş karakterler gösterdiği arabellek depolanan içine `wcstr`, bulunan dönüştürme durumunu kullanarak `mbstate`. Ya da bir sonlandırma null birden çok baytlı karakter karşılaşılana kadar dönüştürme her bir karakter için geçerli bir karakter geçerli yerel karşılık gelmiyor birden çok baytlı bir dizisi hatayla karşılaşıldı, devam veya kadar `count` karakter edilmiştir dönüştürülür. Varsa `mbsrtowcs` birden çok baytlı null karakteri ('\0') önce veya ne zaman karşılaşırsa `count` oluşur, dönüştürür, 16 bit sonlandırma null karakter ve durdurur.  
  
 Bu nedenle, geniş karakter dizesini `wcstr` null-yalnızca sonlandırılır `mbsrtowcs` birden çok baytlı bir null karakter dönüştürme sırasında karşılaşır. Dizileri gösterdiği varsa `mbstr` ve `wcstr` üst üste, davranışını `mbsrtowcs` tanımlanmadı. `mbsrtowcs`Geçerli yerel LC_TYPE kategoriye göre etkilenir.  
  
 `mbsrtowcs` İşlevi farklı olarak [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md) kendi restartability tarafından. Dönüştürme durumu depolanan `mbstate` sonraki çağrılar aynı ya da yeniden başlatılabilir diğer işlevleri için. Sonuçlar, yeniden başlatılabilir ve nonrestartable işlevleri kullanımını kullanırken tanımlanmamış.  Örneğin, bir uygulama kullanması gereken `mbsrlen` yerine `mbslen`, bir sonraki çağrı, `mbsrtowcs` yerine kullanılır`mbstowcs.`  
  
 Varsa `wcstr` null işaretçinin değil tarafından işaretçi nesne işaret için `mbstr` sonlandırma bir null karakter ulaştığından dönüştürme durdurduysanız null işaretçi atanır. Aksi takdirde, varsa, son birden çok baytlı karakter dönüştürülür, adresi yalnızca geçmiş atanır. Bu, bir sonraki işlev çağrısı dönüştürme yeniden başlatmak bu çağrıyı durduğu sağlar.  
  
 Varsa `wcstr` bağımsız değişkeni olan bir null işaretçinin `count` bağımsız değişkeni göz ardı edilir ve `mbsrtowcs` gereken boyut geniş karakterler hedef dize döndürür. Varsa `mbstate` null işaretçi, iç iş parçacığı güvenli olmayan statik işlevini kullanıyor `mbstate_t` dönüştürme durum nesnesi. Varsa bir karakter dizisi `mbstr` karşılık gelen çok baytlı yok karakter gösterimi, -1 döndürülür ve `errno` ayarlanır `EILSEQ`.  
  
 Varsa `mbstr` ISA null işaretçinin, geçersiz parametre işleyicisi çağrılır, açıklandığı gibi [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev devam etmek için yürütülmesine izin veriliyorsa, ayarlar `errno` için `EINVAL` ve -1 döndürür.  
  
 C++'da, bu işlev bu işlevin yeni, güvenli karşılık gelen çağıran bir şablon aşırı sahiptir. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="exceptions"></a>Özel Durumlar  
 `mbsrtowcs` İşlevi, geçerli iş parçacığının hiçbir işlev çağrıları sürece çoklu iş parçacığı güvenli olduğu `setlocale` bu işlevi çalıştırma sürece ve `mbstate` bağımsız değişkeni null işaretçi değil.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`mbsrtowcs`|\<wchar.h >|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [Çok baytlı karakter sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbrtowc](../../c-runtime-library/reference/mbrtowc.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)