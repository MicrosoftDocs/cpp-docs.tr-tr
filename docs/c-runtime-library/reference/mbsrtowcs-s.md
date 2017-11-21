---
title: mbsrtowcs_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: mbsrtowcs_s
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
f1_keywords: mbsrtowcs_s
dev_langs: C++
helpviewer_keywords: mbsrtowcs_s function
ms.assetid: 4ee084ec-b15d-4e5a-921d-6584ec3b5a60
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 72489315ad23bf65086105c5d76da1edea48674d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="mbsrtowcss"></a>mbsrtowcs_s
Çok baytlı karakter dizesi geçerli yerel kendi geniş karakter dizesi gösterimine dönüştürür. Bir sürümünü [mbsrtowcs](../../c-runtime-library/reference/mbsrtowcs.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t mbsrtowcs_s(  
   size_t * pReturnValue,  
   wchar_t * wcstr,  
   size_t sizeInWords,  
   const char ** mbstr,  
   size_t count,  
   mbstate_t * mbstate  
);  
template <size_t size>  
errno_t mbsrtowcs_s(  
   size_t * pReturnValue,  
   wchar_t (&wcstr)[size],  
   const char ** mbstr,  
   size_t count,  
   mbstate_t * mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  
 [out]`pReturnValue`  
 Dönüştürülen karakter sayısı.  
  
 [out]`wcstr`  
 Elde edilen depolamak için arabellek adresini dönüştürülen geniş karakter dizesi.  
  
 [out]`sizeInWords`  
 Boyutunu `wcstr` içinde sözcükleri (geniş karakter).  
  
 [içinde out]`mbstr`  
 Dönüştürülecek birden çok baytlı karakter dizesi konuma dolaylı işaretçi.  
  
 [in]`count`  
 En fazla depolamak üzere geniş karakter sayısını `wcstr` arabellek, sonlandırma null dahil değil veya [_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 [içinde out]`mbstate`  
 Bir işaretçi bir `mbstate_t` dönüştürme durum nesnesi. Bu değer null işaretçi ise, bir statik iç dönüştürme durumu nesnesi kullanılır. Çünkü iç `mbstate_t` nesnesi iş parçacığı açısından güvenli değil, her zaman kendi geçirdiğiniz olmasını öneririz `mbstate` parametresi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Dönüştürme başarılı olduğunda sıfır veya hatasında bir hata kodu.  
  
|Hata durumu|Dönüş değeri ve`errno`|  
|---------------------|------------------------------|  
|`wcstr`null işaretçi ve `sizeInWords` > 0|`EINVAL`|  
|`mbstr`null işaretçi|`EINVAL`|  
|Dize dolaylı olarak işaret için tarafından `mbstr` geçerli yerel ayar için geçerli olmayan bir birden çok baytlı dizisi içerir.|`EILSEQ`|  
|Hedef arabellek dönüştürülmüş dizeyi içeren için çok küçük. (sürece `count` olan `_TRUNCATE`; daha fazla bilgi için açıklamalar bakın)|`ERANGE`|  
  
 Bu koşulların herhangi biri meydana gelirse, geçersiz bir parametre özel durum açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md) . Devam etmek için yürütülmesine izin veriliyorsa, bir hata kodu işlevi döndürür ve ayarlar `errno` tabloda belirtildiği şekilde.  
  
## <a name="remarks"></a>Açıklamalar  
 `mbsrtowcs_s` İşlevi dönüştürür dolaylı olarak gösterdiği birden çok baytlı karakter dizesi `mbstr` gösterdiği arabellek depolanan geniş karakterler içine `wcstr`, bulunan dönüştürme durumunu kullanarak `mbstate`. Bu koşullardan biri yerine getirilene kadar dönüştürme için her karakter devam eder:  
  
-   Birden çok baytlı null karakteri ile karşılaşıldı  
  
-   Geçersiz bir birden çok baytlı karakter karşılaştı  
  
-   Depolanan geniş karakter sayısını `wcstr` arabellek eşittir `count`.  
  
 Hedef dize `wcstr` null ile sonlandırılmış bir hata olması durumunda bile, her zaman olduğu sürece `wcstr` null işaretçi.  
  
 Varsa `count` özel değer [_TRUNCATE](../../c-runtime-library/truncate.md), `mbsrtowcs_s` dize olarak büyük dönüştürür hala null Sonlandırıcı yer bırakarak hedef arabelleğine sığacak.  
  
 Varsa `mbsrtowcs_s` başarıyla kaynak dizesi dönüştürür dönüştürülmüş dizeyi ve içine null Sonlandırıcı geniş karakter cinsinden boyutu koyar `*pReturnValue`, sağlanan `pReturnValue` null işaretçi değil. Bu meydana olsa bile `wcstr` bağımsız değişkeni null işaretçi ve gerekli arabellek boyutunu belirlemenize olanak tanır. Unutmayın `wcstr` null işaretçi `count` göz ardı edilir.  
  
 Varsa `wcstr` null işaretçinin değil tarafından işaretçi nesne işaret için `mbstr` sonlandırma bir null karakter ulaştığından dönüştürme durdurduysanız null işaretçi atanır. Aksi takdirde, varsa, son birden çok baytlı karakter dönüştürülür, adresi yalnızca geçmiş atanır. Bu, bir sonraki işlev çağrısı dönüştürme yeniden başlatmak bu çağrıyı durduğu sağlar.  
  
 Varsa `mbstate` null işaretçi, iç Kitaplığı `mbstate_t` dönüştürme durumu statik nesnesi kullanılır. Bu dahili statik nesnenin iş parçacığı olmadığı için kendi geçirmenizi öneririz `mbstate` değeri.  
  
 Varsa `mbsrtowcs_s` geçerli yerel ayarında geçersiz bir birden çok baytlı karakter karşılaştığında -1 koyar `*pReturnValue`, hedef arabelleği ayarlar `wcstr` boş bir dize olarak ayarlar `errno` için `EILSEQ`ve döndürür `EILSEQ`.  
  
 Dizileri gösterdiği varsa `mbstr` ve `wcstr` üst üste, davranışını `mbsrtowcs_s` tanımlanmadı. `mbsrtowcs_s`Geçerli yerel LC_TYPE kategoriye göre etkilenir.  
  
> [!IMPORTANT]
>  Emin `wcstr` ve `mbstr` çakışmaması ve `count` doğru şekilde dönüştürmek için birden çok baytlı karakter sayısını yansıtır.  
  
 `mbsrtowcs_s` İşlevi farklı olarak [mbstowcs_s, _mbstowcs_s_l](../../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md) kendi restartability tarafından. Dönüştürme durumu depolanan `mbstate` sonraki çağrılar aynı ya da yeniden başlatılabilir diğer işlevleri için. Sonuçlar, yeniden başlatılabilir ve nonrestartable işlevleri kullanımını kullanırken tanımlanmamış. Örneğin, bir uygulama kullanması gereken `mbsrlen` yerine `mbslen`, bir sonraki çağrı, `mbsrtowcs_s` yerine kullanılır`mbstowcs_s.`  
  
 C++'da, bu işlevi kullanarak şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı arabellek uzunluğu otomatik olarak Infer (boyutu bağımsız değişkeni belirtmeniz gerekliliğini ortadan) ve yeni, güvenli dekiler kullanarak bunlar daha eski, güvenli olmayan işlevleri otomatik olarak değiştirebilirsiniz. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="exceptions"></a>Özel Durumlar  
 `mbsrtowcs_s` İşlevi ise çoklu iş parçacığı güvenli bir işlev geçerli iş parçacığı çağrılarında `setlocale` bu işlevi çalıştırma sürece ve `mbstate` bağımsız değişkeni null işaretçi değil.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`mbsrtowcs_s`|\<wchar.h >|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri dönüştürme](../../c-runtime-library/data-conversion.md)   
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [Çok baytlı karakter sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbrtowc](../../c-runtime-library/reference/mbrtowc.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [mbstowcs_s, _mbstowcs_s_l](../../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)