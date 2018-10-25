---
title: C stili dizelerle ilgili CString işlemleri | Microsoft Docs
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
ms.openlocfilehash: 765cb6ccf24415c174761c57268dc79e1fc6845b
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50062567"
---
# <a name="cstring-operations-relating-to-c-style-strings"></a>C stili dizelerle ilgili CString işlemleri

A [CString](../atl-mfc-shared/using-cstring.md) nesnesi karakter dizesi verileri içerir. `CString` kümesini devralan [yöntemleri ve işleçleri](../atl-mfc-shared/reference/cstringt-class.md) Sınıf şablonunda tanımlanan [CStringT](../atl-mfc-shared/reference/cstringt-class.md) dize verilerle çalışmak için. (`CString` olduğu bir **typedef** uzmanlaşmış `CStringT` karakter veri türü ile çalışmak için `CString` destekler.)

`CString` karakter verileri, C stili null ile sonlandırılmış dize olarak dahili olarak depolamaz. Bunun yerine, `CString` böylece veriler ve gerektirdiği alanın daha güvenli bir şekilde izleyebilirsiniz karakter verileri uzunluğunu izler.

`CString` C stili dizeler kabul etmez ve C stili dize olarak karakter verilerine erişmek için yöntemler sağlar. Bu konu, nasıl kullanılacağını açıklayan aşağıdaki bölümleri içerir. bir `CString` C stili null ile sonlandırılmış bir dize gibi nesne.

- [C stili null ile sonlandırılmış dizeleri için dönüştürme](#_core_using_cstring_as_a_c.2d.style_null.2d.terminated_string)

- [Dize işlevleri standart çalışma zamanı kitaplığı ile çalışma](#_core_working_with_standard_run.2d.time_library_string_functions)

- [CString içeriği doğrudan değiştirme](#_core_modifying_cstring_contents_directly)

- [CString nesneleri değişken bağımsız değişken işlevleri ile kullanma](#_core_using_cstring_objects_with_variable_argument_functions)

- [CString biçimsel parametreler belirtme](#_core_specifying_cstring_formal_parameters)

##  <a name="_core_using_cstring_as_a_c.2d.style_null.2d.terminated_string"></a> C stili Null ile sonlandırılmış dize olarak CString kullanma

Kullanılacak bir `CString` nesnesi C stili dize olarak, LPCTSTR nesnesi. Aşağıdaki örnekte, `CString` salt okunur C stili null ile sonlandırılmış dizeye bir işaretçi döndürür. `strcpy` İşlevi C stili dizenin bir kopyasını değişkeninde koyar `myString`.

```cpp
CString aCString = "A string";
char myString[256];
strcpy(myString, (LPCTSTR)aCString);
```

Kullanabileceğiniz `CString` yöntemleri, örneğin, `SetAt`dize nesnesindeki karakterlerin tek tek değiştirmek için. Ancak, LPCTSTR işaretçi geçicidir ve herhangi bir değişiklik yapıldığında geçersiz hale `CString`. `CString` Kapsam dışına de gidebilir ve otomatik olarak silinecek. Yeni bir LPCTSTR işaretçisinin alma öneririz bir `CString` nesne her birini kullanın.

Bazen bir kopyasını gerektirebilir `CString` doğrudan değiştirmek için veri. Daha güvenli işlevini `strcpy_s` (veya Unicode/MBCS-taşınabilir `_tcscpy_s`) kopyalamak için `CString` ayrı arabelleğine nesne. Burada karakterleri güvenli bir şekilde değiştirilebilir, aşağıdaki örnekte gösterildiği gibi budur.

[!code-cpp[NVC_ATLMFC_Utilities#189](../atl-mfc-shared/codesnippet/cpp/cstring-operations-relating-to-c-style-strings_1.cpp)]

> [!NOTE]
> Üçüncü bağımsız değişkeni `strcpy_s` (veya Unicode/MBCS-taşınabilir `_tcscpy_s`) ya da bir `const wchar_t*` (Unicode) veya bir `const char*` (ANSI). Geçişleri yukarıdaki örnekte bir `CString` bu bağımsız değişkeni. C++ derleyicisi, otomatik olarak tanımlanmış dönüştürme işlevi uygulanır `CString` dönüştürür sınıfı bir `CString` için bir `LPCTSTR`. Başka bir türden atama işlemleri tanımlama yeteneği C++'ın en kullanışlı özellikler biridir.

##  <a name="_core_working_with_standard_run.2d.time_library_string_functions"></a> Standart çalışma zamanı kitaplığı dize işlevleri ile çalışma

Bulma olmalıdır bir `CString` kendisi için düşündüğünüz gibi standart C çalışma zamanı kitaplığı dize işlevleri kullanarak herhangi bir dize işlemi gerçekleştirmek için gereken yöntemini `strcmp` (veya Unicode/MBCS-taşınabilir `_tcscmp`).

C çalışma zamanı dize işlevleri kullanmanız gerekiyorsa, içinde _core_using_cstring_as_a_c.2d.style_null.2d.terminated_string açıklanan teknikleri kullanabilirsiniz. Kopyalayabilirsiniz `CString` nesne eşdeğer bir C tarzı dize arabelleğine, arabellek ve sonuç C stili dizesi başa sonra atama işlemleri bir `CString` nesne.

##  <a name="_core_modifying_cstring_contents_directly"></a> CString içeriği doğrudan değiştirme

Çoğu durumda, kullanmanız gereken `CString` içeriğini değiştirmek için üye işlevleri bir `CString` nesne veya dönüştürülecek `CString` C stili bir karakter dizesi.

Burada anlamlı doğrudan değiştirmek için bazı durumlarda `CString` karakter arabelleği gereken işletim sistemi işlevleri ile çalışırken, örneğin, içeriği.

`GetBuffer` Ve `ReleaseBuffer` yöntemleri iç karakter arabelleği erişim sunan bir `CString` nesne ve doğrudan değiştirmenize izin verir. Aşağıdaki adımlar, bu işlevler, bu amaçla kullanabileceğiniz gösterilmektedir.

### <a name="to-use-getbuffer-and-releasebuffer-to-access-the-internal-character-buffer-of-a-cstring-object"></a>GetBuffer ve ReleaseBuffer CString nesnenin iç karakter arabelleğine erişmek için kullanılacak

1. Çağrı `GetBuffer` için bir `CString` nesne ve ihtiyaç duyduğunuz arabellek uzunluğu belirtin.

1. Tarafından döndürülen işaretçi kullanın `GetBuffer` karakterlere doğrudan yazma `CString` nesne.

1. Çağrı `ReleaseBuffer` için `CString` tüm iç güncelleştirmek için nesne `CString` durum bilgileri, örneğin, dize uzunluğu. İçeriğini değiştirdikten sonra bir `CString` doğrudan çağırmanız nesne `ReleaseBuffer` diğer çağırmadan önce `CString` üye işlevleri.

##  <a name="_core_using_cstring_objects_with_variable_argument_functions"></a> CString nesneleri değişken bağımsız değişken işlevleri ile kullanma

Bazı C İşlevler, değişken sayıda bağımsız değişken alır. Önemli bir örnektir `printf_s`. Bu tür bir işlev bildirildiği şekilde nedeniyle derleyici bağımsız değişken türü emin olamaz ve her bağımsız değişken üzerinde gerçekleştirmek için dönüştürme işlemi belirlenemiyor. Bu nedenle, geçerken dönüştürme açık bir tür kullanan temel bir `CString` değişken sayıda bağımsız değişken alan bir işlev nesnesi.

Kullanılacak bir `CString` türüne açıkça bir bağımsız değişken işlev nesnesi `CString` aşağıdaki örnekte gösterildiği gibi bir LPCTSTR dizesi.

[!code-cpp[NVC_ATLMFC_Utilities#190](../atl-mfc-shared/codesnippet/cpp/cstring-operations-relating-to-c-style-strings_2.cpp)]

##  <a name="_core_specifying_cstring_formal_parameters"></a> CString resmi parametrelerini belirtme

Bir dize bağımsız değişkeni gereken çoğu işlev için biçimsel parametre işlev prototipi belirtmek en iyi bir `const` karaktere bir işaretçi (`LPCTSTR`) yerine bir `CString`. Olarak biçimsel parametre belirtildiğinde bir `const` karaktere bir işaretçi, bir sabit dizesi, bir TCHAR dizi ya da bir işaretçi iletebilir [`"hi there"`], veya bir `CString` nesne. `CString` Nesne için bir LPCTSTR otomatik olarak da dönüştürülür. Bir LPCTSTR kullanabileceğiniz herhangi bir yerde de kullanabilirsiniz bir `CString` nesne.

Biçimsel parametre bir sabit dize başvuru belirtebilirsiniz (diğer bir deyişle, `const CString&`), bağımsız değişken değiştirilmeyecek. DROP **const** işlevi tarafından değiştirilecek olan dize, değiştirici. Varsayılan null değer isterseniz, boş bir dize için başlatılamıyor. [`""`], aşağıda gösterildiği gibi:

[!code-cpp[NVC_ATLMFC_Utilities#191](../atl-mfc-shared/codesnippet/cpp/cstring-operations-relating-to-c-style-strings_3.cpp)]

Çoğu işlev sonuçları almak için basitçe dönebilirsiniz bir `CString` değer nesnesi.

## <a name="see-also"></a>Ayrıca Bkz.

[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[CString Bağımsız Değişken Geçirme](../atl-mfc-shared/cstring-argument-passing.md)
