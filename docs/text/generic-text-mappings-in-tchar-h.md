---
title: Tchar.h'de genel metin eşlemeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- tchar.h
dev_langs:
- C++
helpviewer_keywords:
- mapping generic-text
- generic-text mappings [C++]
- character sets [C++], generic-text mappings
- Unicode [C++], generic-text mappings
- MBCS [C++], generic-text mappings
- TCHAR.H data types, mapping
- mappings [C++], TCHAR.H
ms.assetid: 01e1bb74-5a01-4093-8720-68b6c1fdda80
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4fd66a0e2f45def3aa22342ca30eaa64846ebf4c
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40012016"
---
# <a name="generic-text-mappings-in-tcharh"></a>Tchar.h'de Genel Metin Eşlemeleri
Uluslararası kullanımı, kodun taşınmasını kolaylaştıran [!INCLUDE[TLA#tla_ms](../text/includes/tlasharptla_ms_md.md)] çalışma zamanı kitaplığı sağlar [!INCLUDE[TLA#tla_ms](../text/includes/tlasharptla_ms_md.md)]-birçok veri türleri, yordamlar ve diğer nesneler için belirli genel metin eşlemeleri. Bu eşlemeler tek bayt, çok baytlı, derlenebilir genel kod yazmak için Tchar.h'de tanımlanan kullanabilirsiniz veya [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] karakter kümesi kullanarak tanımladığınız bir bildirim sabiti bağlı olarak bir `#define` deyimi. Genel metin eşlemeleri [!INCLUDE[TLA#tla_ms](../text/includes/tlasharptla_ms_md.md)] değil uzantıları [!INCLUDE[vcpransi](../atl-mfc-shared/reference/includes/vcpransi_md.md)] uyumlu.  
  
 Tchar.h kullanarak tek baytlık çok baytlı karakter kümesi (MBCS) oluşturabilir ve [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] aynı kaynaklardan gelen uygulamaları. Tchar.h makroları tanımlar (öneki olan `_tcs`) ile doğru önişlemci tanımları, eşleme `str`, `_mbs`, veya `wcs` İşlevler, uygun şekilde. MBCS oluşturmak için sembolünü tanımlayın `_MBCS`. Oluşturulacak [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)], sembolünü tanımlayın `_UNICODE`. Tek baytlık bir uygulama oluşturmak için Hiçbiri (varsayılan) tanımlayın. Varsayılan olarak, `_MBCS` MFC uygulamaları için tanımlanır.  
  
 `_TCHAR` Veri türü Tchar.h koşullu olarak tanımlanmıştır. Sembol `_UNICODE` , yapı için tanımlanan `_TCHAR` olarak tanımlanan **wchar_t**; Aksi takdirde tek baytlı ve MBCS derlemeler için olarak tanımlanır **char**. (**wchar_t**, temel Unicode geniş karakter veri türü olan bir 8-bit işaretli 16 bit karşılık gelen **char**.) Uluslararası uygulamalar için `_tcs` çalışması işlevler ailesini `_TCHAR` birimleri, bayt sayısını değil. Örneğin, `_tcsncpy` kopyaları `n` `_TCHARs`değil `n` bayt.  
  
 Bazı tek baytlı karakter kümesi (SBCS) dize işleme işlevleri (imzalanmış) çünkü `char*` parametreler, bir tür uyuşmazlığı derleyici uyarı sonuçları, `_MBCS` tanımlanır. Bu uyarıyı engellemek için üç yolu vardır:  
  
1.  Tür kullanımı uyumlu satır içi işlev dönüştürücüler kullanın. Bu varsayılan davranıştır.  
  
2.  Tanımlayarak doğrudan makroları kullanın `_MB_MAP_DIRECT` komut satırında. Bunu yaparsanız, el ile türlerinin eşleşmesi gerekir. Bu, en hızlı yöntemdir, ancak tür kullanımı uyumlu değil.  
  
3.  Tür kullanımı uyumlu statik olarak bağlı bir kitaplığı işlevi dönüştürücüler kullanın. Bunu yapmak için definovat konstantu `_NO_INLINING` komut satırında. Ancak en iyi tür açısından güvenli yavaş yöntem budur.  
  
### <a name="preprocessor-directives-for-generic-text-mappings"></a>Genel metin eşlemeleri için ön işlemci yönergeleri  
  
|# tanımlayın|Derlenmiş sürüm|Örnek|  
|---------------|----------------------|-------------|  
|`_UNICODE`|[!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] (geniş karakter)|`_tcsrev` Eşleyen `_wcsrev`|  
|`_MBCS`|Çok baytlı karakter|`_tcsrev` Eşleyen `_mbsrev`|  
|Hiçbiri (varsayılan hiçbiri sahip `_UNICODE` ya da `_MBCS` tanımlanan)|SBCS ([!INCLUDE[TLA#tla_ascii](../text/includes/tlasharptla_ascii_md.md)])|`_tcsrev` Eşleyen `strrev`|  
  
 Örneğin, genel metin işlevi `_tcsrev`, Tchar.h içinde tanımlandığı eşlendiğini `_mbsrev` tanımladıysanız `_MBCS` programınızdaki veya çok `_wcsrev` tanımladıysanız `_UNICODE`. Aksi takdirde, `_tcsrev` eşlendiği `strrev`. Diğer veri türü eşlemeleri içinde Tchar.h programlama kolaylık olması için sağlanmıştır ancak `_TCHAR` en yararlı olur.  
  
### <a name="generic-text-data-type-mappings"></a>Genel metin veri türü eşlemeleri  
  
|Genel metin<br /><br /> Veri türü adı|_UNICODE &AMP;<br /><br /> _MBCS tanımlanmaz|_MBCS<br /><br /> Tanımlanan|_UNICODE<br /><br /> Tanımlanan|  
|--------------------------------------|----------------------------------------|------------------------|---------------------------|  
|`_TCHAR`|**char**|**char**|**wchar_t**|  
|`_TINT`|**int**|**işaretsiz int**|`wint_t`|  
|`_TSCHAR`|**İmzalı char**|**İmzalı char**|**wchar_t**|  
|`_TUCHAR`|**İmzasız char**|**İmzasız char**|**wchar_t**|  
|`_TXCHAR`|**char**|**İmzasız char**|**wchar_t**|  
|`_T` veya `_TEXT`|Herhangi bir etkisi (önişlemci tarafından kaldırıldı)|Herhangi bir etkisi (önişlemci tarafından kaldırıldı)|`L` (aşağıdaki karakter veya dize olarak dönüştürür, [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] karşılığı)|  
  
 Genel metin eşlemeleri yordamları, değişkenlerin ve diğer nesnelerin bir listesi için bkz. [genel metin eşlemeleri](../c-runtime-library/generic-text-mappings.md) çalışma zamanı kitaplığı başvurusu.  
  
> [!NOTE]
>  Kullanmayın `str` bulunma olasılığı olan Unicode dizelerini ana sahip işlev ailesi gömülü null bayt. Benzer şekilde, kullanmayın `wcs` MBCS (veya SBCS) dizeleri içeren işlevler ailesini.  
  
 Aşağıdaki kod parçalarını kullanımını gösteren `_TCHAR` ve `_tcsrev` eşleme için MBCS [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)]ve SBCS modelleri.  
  
```  
_TCHAR *RetVal, *szString;  
RetVal = _tcsrev(szString);  
```  
  
 Varsa `_MBCS` olmuştur tanımlanan, önişlemci bu parçayı bu koda eşler:  
  
```  
char *RetVal, *szString;  
RetVal = _mbsrev(szString);  
```  
  
 Varsa `_UNICODE` olmuştur tanımlanan, önişlemci bu parçayı bu koda eşler:  
  
```  
wchar_t *RetVal, *szString;  
RetVal = _wcsrev(szString);  
```  
  
 Kullanılmazsa `_MBCS` ya da `_UNICODE` silinmiş tanımlanan, önişlemci parça tek baytlık eşler [!INCLUDE[TLA#tla_ascii](../text/includes/tlasharptla_ascii_md.md)] kod gibi:  
  
```  
char *RetVal, *szString;  
RetVal = strrev(szString);  
```  
  
 Bu nedenle, yazma, korumak ve herhangi bir karakter kümesi üç tür için özel yordamlar çalıştırmak için tek kaynak kod dosyasını derleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Metin ve dizeler](../text/text-and-strings-in-visual-cpp.md)   
 [_MBCS Kodu ile TCHAR.H Veri Türlerini Kullanma](../text/using-tchar-h-data-types-with-mbcs-code.md)