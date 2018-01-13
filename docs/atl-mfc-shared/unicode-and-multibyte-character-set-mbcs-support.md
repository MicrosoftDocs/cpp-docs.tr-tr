---
title: "Unicode ve çok baytlı karakter kümesi (MBCS) destek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- MFC [C++], character set support
- MBCS [C++], strings and MFC support
- strings [C++], MBCS support in MFC
- character sets [C++], multibyte
- Unicode [C++], MFC strings
- Unicode [C++], string objects
- strings [C++], Unicode
- strings [C++], character set support
ms.assetid: 44b3193b-c92d-40c5-9fa8-5774da303cce
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ea35f36012eb893d8784c626c533690e97b517e5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="unicode-and-multibyte-character-set-mbcs-support"></a>Unicode ve çok baytlı karakter kümesi (MBCS) desteği
Örneğin, Japonca ve Çince, bazı dillerde geniş karakter kümesi vardır. Bu pazarlarında programlama desteklemek için geniş karakter kümeleri işleme için iki farklı yaklaşım için Microsoft Foundation Class Kitaplığı (MFC) etkinleştirilir:  
  
-   [Unicode](#_core_mfc_support_for_unicode_strings)  
  
-   [Çok baytlı karakter kümeleri (MBCS)](#_core_mfc_support_for_mbcs_strings)  
  
 Tüm yeni geliştirme projeleri için Unicode kullanmanız gerekir.  
  
##  <a name="_core_mfc_support_for_unicode_strings"></a>Unicode dizeleri için MFC desteği  
 Tüm sınıf kitaplığı koşullu Unicode karakterden ve dizeleri için etkinleştirilir. Özellikle, sınıf [CString](../atl-mfc-shared/reference/cstringt-class.md) Unicode etkindir.  
  
|||||  
|-|-|-|-|  
|UAFXCW. LIB|UAFXCW. PDB|UAFXCWD. LIB|UAFXCWD. PDB|  
|MFC*xx*U.LIB|MFC*xx*U.PDB|MFC*xx*U.DLL|MFC*xx*UD. LIB|  
|MFC*xx*UD. PDB|MFC*xx*UD. DLL|MFCS*xx*U.LIB|MFCS*xx*U.PDB|  
|MFCS*xx*UD. LIB|MFCS*xx*UD. PDB|MFCM*xx*U.LIB|MFCM*xx*U.PDB|  
|MFCM*xx*U.DLL|MFCM*xx*UD. LIB|MFCM*xx*UD. PDB|MFCM*xx*UD. DLL|  
  
 (*xx* ; dosyasının sürüm numarasını temsil eder örneğin sürüm 8.0 '80' anlamına gelir.)  
  
 `CString`dayanır `TCHAR` veri türü. Varsa simgenin `_UNICODE` programınızın, derleme için tanımlanan `TCHAR` türü olarak tanımlanmış `wchar_t`, 16 bit karakter kodlama türü. Aksi takdirde, `TCHAR` olarak tanımlanan `char`, normal 8 bit karakter kodlaması. Bu nedenle, Unicode altında bir `CString` 16 bit karakterlerinden oluşur. Unicode türü karakterlerinden oluşur `char`.  
  
 İçin tam Unicode programlama uygulamanızın ayrıca gerekir:  
  
-   Kullanım `_T` Unicode'a taşınabilmesini koşullu kod değişmez değer dizeleri makrosuna.  
  
-   Dizeleri geçirdiğinizde olup gerektirir karakter cinsinden uzunluğu veya bayt cinsinden uzunluğu işlev bağımsız değişkenleri için dikkat edin. Fark, Unicode dizelerini kullanıyorsanız önemlidir.  
  
-   C çalışma zamanı dize işleme işlevleri taşınabilir sürümlerini kullanın.  
  
-   Aşağıdaki veri türlerini karakterleri ve karakter işaretçileri için kullanın:  
  
    -   `TCHAR`Burada kullandığınız `char`.  
  
    -   `LPTSTR`Burada kullandığınız `char*`.  
  
    -   `LPCTSTR`Burada kullandığınız `const char*`. `CString`işleç sağlar `LPCTSTR` arasında dönüştürme yapma `CString` ve `LPCTSTR`.  
  
 `CString`Ayrıca Unicode algılayan Oluşturucular, atama işleçleri ve Karşılaştırma işleçleri sağlar.  
  
 Unicode programlama ilgili bilgi için bkz: [Unicode konuları](../mfc/unicode-in-mfc.md). [Çalışma zamanı kitaplığı başvurusu](../c-runtime-library/c-run-time-library-reference.md) taşınabilir sürümlerinde tüm dize işleme işlevleri tanımlar. Kategorisini görmek [uluslararası hale getirme](../c-runtime-library/internationalization.md).  
  
##  <a name="_core_mfc_support_for_mbcs_strings"></a>MBCS dizeleri için MFC desteği  
  
 Sınıf kitaplığı için birden çok baytlı karakter kümeleri de etkinleştirilir, ancak yalnızca çift bayt karakter (DBCS) ayarlar.  
  
 Birden çok baytlı karakter kümesinde bir veya iki bayt geniş karakter olabilir. Bu iki bayt genişliğinde ilk baytı özel bir "baytı" ise, yani seçilen bağlı olarak hangi kod sayfası kullanılıyor belirli bir aralıktan. Birlikte ele alındığında, sağlama ve "baytlara" benzersiz karakter kodlamasını belirleyin.  
  
 Varsa simgenin `_MBCS` türü programınızın bir yapı için tanımlanan `TCHAR`, üretileceği `CString` bağlı olduğu için eşlendiği `char`. Hangi bayt cinsinden belirlemenizi kadar olan bir `CString` ön baytlar ve baytlar olduğu. C çalışma zamanı kitaplığı bu belirlemenize yardımcı olması için işlevleri sağlar.  
  
 DBCS altında verilen bir dize tüm tek baytlı ANSI karakter, tüm çift baytlık karakterler veya iki bir birleşimini içerebilir. Bu olanakları dizeleri ayrıştırma sırasında özel dikkat gerektirir. Bu içerir `CString` nesneleri.  
  
> [!NOTE]
>  MFC'de Unicode dize serileştirme kullanmakta olduğunuz uygulamanın hangi sürümünün bakılmaksızın Unicode ve MBCS dizeleri okuyabilir. Veri dosyalarınızı programınızı Unicode ve MBCS sürümleri arasında taşınabilir.  
  
 `CString`üye işlevleri çağrıda buldukları C çalışma zamanı işlevleri özel "genel metin" sürümleri veya Unicode uyumlu işlevleri kullanın. Bu nedenle, örneğin, bir `CString` işlevi genellikle çağrısı `strcmp`, karşılık gelen genel metin işlevi çağırır `_tcscmp` yerine. Nasıl bağlı olarak simgeleri `_MBCS` ve `_UNICODE` tanımlanan `_tcscmp` gibi eşler:  
  
|||  
|-|-|  
|`_MBCS`tanımlı|`_mbscmp`|  
|`_UNICODE`tanımlı|`wcscmp`|  
|Tanımlanan hiçbiri simgesi|`strcmp`|  
  
> [!NOTE]
>  Simgeler `_MBCS` ve `_UNICODE` karşılıklı olarak birbirini dışlar.  
  
 Genel metin işlev eşlemeleri tüm çalışma zamanı dize işleme yordamları açıklanmıştır [C çalışma zamanı kitaplığı başvurusu](../c-runtime-library/c-run-time-library-reference.md). Özellikle, bkz: [uluslararası hale getirme](../c-runtime-library/internationalization.md).  
  
 Benzer şekilde, `CString` yöntemleri, "Genel" veri türü eşlemeleri kullanılarak uygulanır. Kullanan MFC MBCS ve Unicode etkinleştirmek için `TCHAR` için `char`, `LPTSTR` için `char*`, ve `LPCTSTR` için `const char*`. Bunlar MBCS veya Unicode için doğru eşlemeleri emin olun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [Dize düzenlemesi](../c-runtime-library/string-manipulation-crt.md)

