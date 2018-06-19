---
title: CString işlemleri C tarzı dizelere ilgili | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CString objects, basic operations
- MFC [C++], string handling class
- string conversion [C++], C-style strings
- strings [C++], string operations
- standard run-time library string functions
- null values, Null-terminated string conversion
- string functions
- strings [C++], in C
- string arguments
- C-style strings
- strings [C++], class CString
- casting CString objects
ms.assetid: 5048de8a-5298-4891-b8a0-c554b5a3ac1b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d0683f82204b11d06b1952913d4dbdb1e4a468d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361820"
---
# <a name="cstring-operations-relating-to-c-style-strings"></a>C türü dizelere ilgili CString işlemleri
A [CString](../atl-mfc-shared/using-cstring.md) nesnesi karakter dizesi verileri içerir. `CString` kümesini devralır [yöntemleri ve işleçleri](../atl-mfc-shared/reference/cstringt-class.md) Sınıf şablonunda tanımlanan [CStringT](../atl-mfc-shared/reference/cstringt-class.md) dize verilerle çalışmak için. (`CString` olan bir `typedef` , uzmanlaşmış `CStringT` karakter veri türü ile çalışmak için `CString` destekler.)  
  
 `CString` karakter veri C türü null ile sonlandırılmış dize olarak dahili olarak depolamaz. Bunun yerine, `CString` böylece veriler ve bu alanı daha güvenli bir şekilde izleyebilirsiniz karakter veri uzunluğu izler.  
  
 `CString` C stilinde dizeleri kabul etmez ve C stili dize olarak karakter verilere erişmek için yöntemler sağlar. Bu konu, nasıl kullanılacağını açıklayan aşağıdaki bölümleri içerir. bir `CString` C türü null sonlandırılmış bir dize değilmiş gibi nesne.  
  
- [C türü null ile sonlandırılmış dizelere dönüştürme](#_core_using_cstring_as_a_c.2d.style_null.2d.terminated_string)  
  
- [Standart çalışma zamanı kitaplığı dize işlevleri ile çalışma](#_core_working_with_standard_run.2d.time_library_string_functions)  
  
- [CString içeriği doğrudan değiştirme](#_core_modifying_cstring_contents_directly)  
  
- [CString nesneleri değişken bağımsız değişken işlevleri ile kullanma](#_core_using_cstring_objects_with_variable_argument_functions)  
  
- [CString resmi parametrelerini belirtme](#_core_specifying_cstring_formal_parameters)  
  
##  <a name="_core_using_cstring_as_a_c.2d.style_null.2d.terminated_string"></a> CString C türü Null ile sonlandırılmış dize olarak kullanma  
 Kullanılacak bir `CString` nesne C stili dize olarak, nesnenin `LPCTSTR`. Aşağıdaki örnekte, `CString` bir işaretçi bir salt okunur C türü null ile sonlandırılmış dizeyi döndürür. `strcpy` İşlevi değişkende C stili dize bir kopyasını koyar `myString`.  
  
```  
CString aCString = "A string";  
char myString[256];  
strcpy(myString, (LPCTSTR)aCString);
```  
  
 Kullanabileceğiniz `CString` yöntemleri, örneğin, `SetAt`dize nesnesi tek tek karakter değiştirmek için. Ancak, `LPCTSTR` işaretçi geçicidir ve herhangi bir değişiklik yapıldığında geçersiz hale gelir `CString`. `CString` Kapsamının dışına de gidebilir ve otomatik olarak silinir. Baştan elde etmenizi öneririz `LPCTSTR` işaretçisi bir `CString` nesne her birini kullanın.  
  
 Bazen bir kopyasını gerektirebilir `CString` doğrudan değiştirmek için veri. Daha güvenli işlevini `strcpy_s` (veya Unicode/MBCS-taşınabilir `_tcscpy_s`) kopyalamak için `CString` ayrı bir arabellek nesnesine. Karakter güvenle değiştirilebildiği, aşağıdaki örnekte gösterildiği gibi budur.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#189](../atl-mfc-shared/codesnippet/cpp/cstring-operations-relating-to-c-style-strings_1.cpp)]  
  
> [!NOTE]
>  Üçüncü bağımsız değişkeni `strcpy_s` (veya Unicode/MBCS-taşınabilir `_tcscpy_s`) herhangi bir `const wchar_t*` (Unicode) veya bir `const char*` (ANSI). Geçişleri Yukarıdaki örnek bir `CString` bu bağımsız değişken için. C++ derleyicisi için tanımlanan dönüştürme işlevi otomatik olarak uygular `CString` dönüştürür sınıfı bir `CString` için bir `LPCTSTR`. Başka bir türden diğerine atama işlemleri tanımlama yeteneği C++ en kullanışlı özelliklerinden biridir.  
  
##  <a name="_core_working_with_standard_run.2d.time_library_string_functions"></a> Standart çalışma zamanı kitaplığı dize işlevleri ile çalışma  
 Bulamıyor olması gereken bir `CString` yöntemi için değerlendirmeniz standart C çalışma zamanı kitaplığı dize işlevleri gibi kullanarak herhangi bir dize işlemi gerçekleştirmek için `strcmp` (veya Unicode/MBCS-taşınabilir `_tcscmp`).  
  
 C çalışma zamanı dize işlevleri kullanmanız gerekiyorsa, _core_using_cstring_as_a_c.2d.style_null.2d.terminated_string içinde açıklanan teknikleri kullanabilirsiniz. Kopyalayabilirsiniz `CString` nesne bir eşdeğer C stili dize arabellek, arabellek ve sonuçta elde edilen C stili dize başa sonra Ata işlemleri bir `CString` nesnesi.  
  
##  <a name="_core_modifying_cstring_contents_directly"></a> CString içeriği doğrudan değiştirme  
 Çoğu durumda, kullanmanız gereken `CString` içeriğini değiştirmek için üye işlevleri bir `CString` nesne veya dönüştürmek için `CString` C stili karakter dizesi.  
  
 Burada anlamlı doğrudan değiştirmek için bazı durumlar vardır `CString` , bir karakter arabellek gerektiren işletim sistemi işlevleri ile çalışırken, örneğin, içeriği.  
  
 `GetBuffer` Ve `ReleaseBuffer` yöntemleri sunar iç karakter arabelleğin erişimi bir `CString` nesne ve doğrudan değiştirmenize olanak tanır. Aşağıdaki adımlar bu amaç için bu işlevler kullanmayı gösterir.  
  
#### <a name="to-use-getbuffer-and-releasebuffer-to-access-the-internal-character-buffer-of-a-cstring-object"></a>CString nesnesinin iç karakter arabellek erişmek için GetBuffer ve ReleaseBuffer kullanmak için  
  
1.  Çağrı `GetBuffer` için bir `CString` nesne ve ihtiyaç duyduğunuz arabellek uzunluğu belirtin.  
  
2.  Tarafından döndürülen işaretçiyi kullanın `GetBuffer` doğrudan karakterleri yazmak için `CString` nesnesi.  
  
3.  Çağrı `ReleaseBuffer` için `CString` tüm iç güncelleştirmek için nesne `CString` durum bilgisi, örneğin, dize uzunluğu. İçeriğini değiştirdikten sonra bir `CString` doğrudan çağırmanız gerekir nesne `ReleaseBuffer` diğer çağırmadan önce `CString` üye işlevleri.  
  
##  <a name="_core_using_cstring_objects_with_variable_argument_functions"></a> CString nesneleri değişken bağımsız değişken işlevleri ile kullanma  
 Değişken sayıda bağımsız değişken bazı C işlevlerini alın. Önemli bir örnek `printf_s`. Bu tür bir işlev bildirilen şekilde nedeniyle derleyici bağımsız değişken türü emin olamaz ve her bağımsız gerçekleştirmek için hangi dönüştürme işlemi belirleyemiyor. Bu nedenle, geçirilirken cast açık bir tür kullanın önemli bir `CString` nesne değişken sayıda bağımsız değişken alan bir işlev.  
  
 Kullanılacak bir `CString` açıkça cast bir değişken bağımsız değişken işlevi nesnesinde `CString` için bir `LPCTSTR` , aşağıdaki örnekte gösterildiği gibi dize.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#190](../atl-mfc-shared/codesnippet/cpp/cstring-operations-relating-to-c-style-strings_2.cpp)]  
  
##  <a name="_core_specifying_cstring_formal_parameters"></a> CString resmi parametrelerini belirtme  
 Dize bağımsız değişkeni gereksinim çoğu işlevleri için biçimsel parametresi işlev prototipi belirtmek iyi bir `const` bir karakter işaretçisine (`LPCTSTR`) yerine bir `CString`. Olarak biçimsel parametresi belirtildiğinde bir `const` işaretçi bir karakter ya da bir işaretçi iletebilir bir `TCHAR` sabit değerli bir dize dizisi [`"hi there"`], veya bir `CString` nesnesi. `CString` Nesne otomatik olarak dönüştürülür bir `LPCTSTR`. Kullanabileceğiniz herhangi bir yeri bir `LPCTSTR`, aynı zamanda bir `CString` nesnesi.  
  
 Biçimsel parametresi bir sabit dize başvuru olarak belirtebilirsiniz (diğer bir deyişle, `const CString&`) bağımsız değişkeni değiştirilmeyecek durumunda. Bırakma `const` dize işlevi tarafından değiştirilecek varsa değiştiricisi. Varsayılan bir null değer istenirse, boş bir dize başlatma [`""`], aşağıda gösterildiği gibi:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#191](../atl-mfc-shared/codesnippet/cpp/cstring-operations-relating-to-c-style-strings_3.cpp)]  
  
 Çoğu işlevi sonuçları almak için yalnızca dönebilirsiniz bir `CString` değeriyle nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [CString Bağımsız Değişken Geçirme](../atl-mfc-shared/cstring-argument-passing.md)

