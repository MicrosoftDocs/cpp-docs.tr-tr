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
ms.openlocfilehash: c7ed29b03a37c9b911a954192152115b1458fd94
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="generic-text-mappings-in-tcharh"></a>Tchar.h'de Genel Metin Eşlemeleri
Uluslararası kullanımda kodun taşınmasını kolaylaştırmak için [!INCLUDE[TLA#tla_ms](../text/includes/tlasharptla_ms_md.md)] çalışma zamanı kitaplığı sağlayan [!INCLUDE[TLA#tla_ms](../text/includes/tlasharptla_ms_md.md)]-birçok veri türleri, yordamlar ve diğer nesneleri için belirli genel metin eşlemeleri. Bu eşlemeler Tchar.h'de tek bayt, birden çok baytlı, derlenmiş genel kodlar yazmak için tanımlanan kullanabilirsiniz veya [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] karakter kümesi kullanarak tanımladığınız bir bildirim sabit bağlı olarak bir `#define` deyimi. Genel metin eşlemeleri [!INCLUDE[TLA#tla_ms](../text/includes/tlasharptla_ms_md.md)] olmayan uzantıları [!INCLUDE[vcpransi](../atl-mfc-shared/reference/includes/vcpransi_md.md)] uyumlu.  
  
 Tchar.h kullanarak, tek baytlı, çok baytlı karakter kümesi (MBCS) oluşturabilir ve [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] aynı kaynaktan uygulamalar. Tchar.h tanımlar makroları (öneki olan `_tcs`) doğru önişlemci tanımlarıyla eşlemek için `str`, `_mbs`, veya `wcs` uygun olarak işlev. MBCS oluşturmak için simge tanımlama `_MBCS`. Derleme için [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)], sembolünü tanımlayın `_UNICODE`. Tek baytlı uygulama oluşturmak için Hiçbiri (varsayılan) tanımlayın. Varsayılan olarak, `_MBCS` MFC uygulamaları için tanımlanır.  
  
 `_TCHAR` Veri türü Tchar.h koşullu olarak tanımlanır. Varsa simgenin `_UNICODE` yapılandırmanız için tanımlanan `_TCHAR` olarak tanımlanan `wchar_t`; Aksi takdirde, tek baytlı ve MBCS yapılar için olarak tanımlanır `char`. (`wchar_t`, temel Unicode geniş karakter veri türü olan bir 8-bit işaretli 16 bit eşdeğerine `char`.) Uluslararası uygulamalar için `_tcs` ailesi çalışması işlevlerini `_TCHAR` birimleri, bayt değil. Örneğin, `_tcsncpy` kopya `n` `_TCHARs`değil `n` bayt sayısı.  
  
 Bazı tek baytlı karakter kümesi (SBCS) dize işleme (işaretli) gördüğünden `char*` parametreleri, bir tür uyuşmazlığı derleyici uyarı sonuçları zaman `_MBCS` tanımlanır. Bu uyarıyı önlemek için üç yolu vardır:  
  
1.  Tür kullanımı uyumlu satır içi işlev dönüştürücüler kullanın. Bu varsayılan davranıştır.  
  
2.  Tanımlayarak doğrudan makroları kullanın `_MB_MAP_DIRECT` komut satırında. Bunu yaparsanız, türleri el ile eşleşmelidir. Bu en hızlı yöntemdir, ancak tür kullanımı uyumlu değil.  
  
3.  Tür kullanımı uyumlu statik olarak bağlantılı kitaplığı işlevi dönüştürücüler kullanın. Bunu yapmak için sabit tanımlamak `_NO_INLINING` komut satırında. En fazla tür kullanımı uyumlu ancak yavaş yöntem budur.  
  
### <a name="preprocessor-directives-for-generic-text-mappings"></a>Genel metin eşlemeleri önişlemci yönergeleri  
  
|# tanımlayın|Derlenmiş sürüm|Örnek|  
|---------------|----------------------|-------------|  
|`_UNICODE`|[!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] (geniş karakter)|`_tcsrev` Eşler `_wcsrev`|  
|`_MBCS`|Çok baytlı karakter|`_tcsrev` Eşler `_mbsrev`|  
|Hiçbiri (varsayılan hiçbirine sahip `_UNICODE` ya da `_MBCS` tanımlanan)|SBCS ([!INCLUDE[TLA#tla_ascii](../text/includes/tlasharptla_ascii_md.md)])|`_tcsrev` Eşler `strrev`|  
  
 Örneğin, genel metin işlevi `_tcsrev`, Tchar.h içinde tanımlandığı eşlendiğini `_mbsrev` tanımladıysanız `_MBCS` programınızdaki veya çok `_wcsrev` tanımladıysanız `_UNICODE`. Aksi takdirde, `_tcsrev` eşlendiği `strrev`. Diğer veri türü eşlemeleri programlama kolaylığı için Tchar.h içinde sağlanır, ancak `_TCHAR` en yararlı olur.  
  
### <a name="generic-text-data-type-mappings"></a>Genel metin veri türü eşlemeleri  
  
|Genel metin<br /><br /> Veri türü adı|_UNICODE &AMP;<br /><br /> _MBCS tanımlanmamış|_MBCS<br /><br /> Tanımlı|_UNICODE<br /><br /> Tanımlı|  
|--------------------------------------|----------------------------------------|------------------------|---------------------------|  
|`_TCHAR`|`char`|`char`|`wchar_t`|  
|`_TINT`|`int`|`unsigned int`|`wint_t`|  
|`_TSCHAR`|`signed char`|`signed char`|`wchar_t`|  
|`_TUCHAR`|`unsigned char`|`unsigned char`|`wchar_t`|  
|`_TXCHAR`|`char`|`unsigned char`|`wchar_t`|  
|`_T` Veya `_TEXT`|(Önişlemci tarafından kaldırılır) herhangi bir etkisi|(Önişlemci tarafından kaldırılır) herhangi bir etkisi|`L` (aşağıdaki karakter veya dizeye dönüştürür kendi [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] karşılık gelen)|  
  
 Genel metin eşlemeleri yordamları, değişkenlerin ve diğer nesnelerin bir listesi için bkz: [genel metin eşlemeleri](../c-runtime-library/generic-text-mappings.md) çalışma zamanı kitaplığı başvurusu.  
  
> [!NOTE]
>  Kullanmayın `str` bulunma olasılığı Unicode dizeleri işlevleriyle ailesi gömülü boş bayt. Benzer şekilde, kullanmayın `wcs` ailesi işlevlerini MBCS (veya SBCS) dizeler.  
  
 Aşağıdaki kod parçası kullanımını göstermek `_TCHAR` ve `_tcsrev` eşleme MBCS için [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)]ve SBCS modeller.  
  
```  
_TCHAR *RetVal, *szString;  
RetVal = _tcsrev(szString);  
```  
  
 Varsa `_MBCS` bırakıldı tanımlanan önişlemci bu parçasını şu koda eşler:  
  
```  
char *RetVal, *szString;  
RetVal = _mbsrev(szString);  
```  
  
 Varsa `_UNICODE` bırakıldı tanımlanan önişlemci bu parçasını şu koda eşler:  
  
```  
wchar_t *RetVal, *szString;  
RetVal = _wcsrev(szString);  
```  
  
 Ne `_MBCS` ya da `_UNICODE` silinmiş tanımlanan, önişlemci parça tek baytlı eşlemeleri [!INCLUDE[TLA#tla_ascii](../text/includes/tlasharptla_ascii_md.md)] kod, aşağıdaki gibi:  
  
```  
char *RetVal, *szString;  
RetVal = strrev(szString);  
```  
  
 Bu nedenle, yazma, korumanıza ve herhangi bir karakter kümesi üç tür için özel yordamlar çalıştırmak için tek kaynak kodu dosyasını derleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Metin ve dizeler](../text/text-and-strings-in-visual-cpp.md)   
 [_MBCS Kodu ile TCHAR.H Veri Türlerini Kullanma](../text/using-tchar-h-data-types-with-mbcs-code.md)