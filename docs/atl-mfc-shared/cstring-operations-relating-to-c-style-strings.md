---
title: C Stili Dizelerle İlgili CString İşlemleri
ms.date: 11/04/2016
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
ms.openlocfilehash: 406a934d3691c7787085cc319770074ac2ee5926
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317944"
---
# <a name="cstring-operations-relating-to-c-style-strings"></a>C Stili Dizelerle İlgili CString İşlemleri

[CString nesnesi](../atl-mfc-shared/using-cstring.md) karakter dize verileri içerir. `CString`dize verileriyle çalışmak üzere [CStringT](../atl-mfc-shared/reference/cstringt-class.md) sınıfı şablonunda tanımlanan [yöntem ve işleçler](../atl-mfc-shared/reference/cstringt-class.md) kümesini devralır. (`CString` `CString` destekleyen karakter verileri `CStringT` türü ile çalışmak için uzmanlaşmış bir **typedef** olduğunu.)

`CString`karakter verilerini c stili null-sonlandırılan dize olarak dahili olarak depolamaz. Bunun `CString` yerine, karakter verilerinin uzunluğunu izler, böylece verileri ve gerektirdiği alanı daha güvenli bir şekilde izleyebilir.

`CString`C stili dizeleri kabul eder ve c stili dize olarak karakter verilerine erişmek için yollar sağlar. Bu konu, c stili null-sonlandırılan dize gibi bir `CString` nesnenin nasıl kullanılacağını açıklayan aşağıdaki bölümleri içerir.

- [C stili null-sonlandırılan dizeleri dönüştürme](#_core_using_cstring_as_a_c.2d.style_null.2d.terminated_string)

- [Standart çalışma zamanı kitaplık dize işlevleriyle çalışma](#_core_working_with_standard_run.2d.time_library_string_functions)

- [CString içeriğini doğrudan değiştirme](#_core_modifying_cstring_contents_directly)

- [Değişken bağımsız değişken işlevleri olan CString nesnelerini kullanma](#_core_using_cstring_objects_with_variable_argument_functions)

- [CString resmi parametrelerini belirtme](#_core_specifying_cstring_formal_parameters)

## <a name="using-cstring-as-a-c-style-null-terminated-string"></a><a name="_core_using_cstring_as_a_c.2d.style_null.2d.terminated_string"></a>C String'i C Stili Null-Sonlandırılan Dize olarak kullanma

C stili `CString` dize olarak bir nesne kullanmak için, lpctstr için nesne döküm. Aşağıdaki örnekte, `CString` bir işaretçiyi salt okunur C stili null-sonlandırılan dizedöndürür. İşlev, `strcpy` C stili dizesinin bir `myString`kopyasını değişkene koyar.

```cpp
CString aCString = "A string";
char myString[256];
strcpy(myString, (LPCTSTR)aCString);
```

Dize `CString` nesnesindeki `SetAt`karakterleri tek tek değiştirmek için yöntemleri kullanabilirsiniz, örneğin. Ancak, LPCTSTR işaretçisi geçicidir ve `CString`'de değişiklik yapıldığında geçersiz olur. Ayrıca `CString` kapsam dışına çıkabilir ve otomatik olarak silinebilir. Her kullandığınızda bir nesnenin yeni bir `CString` LPCTSTR işaretçisini almanızı öneririz.

Bazen doğrudan değiştirmek için `CString` bir veri kopyası gerekebilir. Nesneyi ayrı bir `strcpy_s` arabelleğe kopyalamak için daha `_tcscpy_s`güvenli işlevi (veya Unicode/MBCS-taşınabilir) kullanın. `CString` Bu, aşağıdaki örnekte gösterildiği gibi karakterlerin güvenli bir şekilde değiştirilebileceği yerdir.

[!code-cpp[NVC_ATLMFC_Utilities#189](../atl-mfc-shared/codesnippet/cpp/cstring-operations-relating-to-c-style-strings_1.cpp)]

> [!NOTE]
> Üçüncü bağımsız `strcpy_s` değişken (veya Unicode/MBCS-taşınabilir) `_tcscpy_s` `const wchar_t*` ya (Unicode) `const char*` ya da (ANSI) 'dir. Yukarıdaki örnek bu `CString` bağımsız değişken için geçer. C++ derleyicisi, `CString` a'yı `CString` bir `LPCTSTR`. Döküm işlemlerini bir türden diğerine tanımlama yeteneği C++'ın en kullanışlı özelliklerinden biridir.

## <a name="working-with-standard-run-time-library-string-functions"></a><a name="_core_working_with_standard_run.2d.time_library_string_functions"></a>Standart Çalışma Zamanı Kitaplığı Dize Fonksiyonları yla Çalışma

(veya Unicode/MBCS-taşınabilir) `CString` `strcmp` `_tcscmp`gibi standart C çalışma zamanı kitaplık dize işlevlerini kullanmayı düşünabileceğiniz herhangi bir dize işlemini gerçekleştirmek için bir yöntem bulabilmelisin.

C çalışma zamanı dize işlevlerini kullanmanız gerekiyorsa, _core_using_cstring_as_a_c.2d.style_null.2d.terminated_string'da açıklanan teknikleri kullanabilirsiniz. Nesneyi `CString` eşdeğer bir C stili dize arabelleğine kopyalayabilir, işlemlerinizi arabellekte gerçekleştirebilir ve ardından `CString` ortaya çıkan C stili dizesini nesneye geri atayabilirsiniz.

## <a name="modifying-cstring-contents-directly"></a><a name="_core_modifying_cstring_contents_directly"></a>CString İçeriklerini Doğrudan Değiştirme

Çoğu durumda, bir `CString` `CString` nesnenin içeriğini değiştirmek veya C stili `CString` karakter dizesini dönüştürmek için üye işlevleri kullanmanız gerekir.

Örneğin, karakter arabelleği gerektiren işletim `CString` sistemi işlevleriyle çalışırken içeriği doğrudan değiştirmenin mantıklı olduğu bazı durumlar vardır.

Ve `GetBuffer` `ReleaseBuffer` yöntemler, bir `CString` nesnenin iç karakter arabellesine erişim sağlar ve doğrudan değiştirmenize izin verebilmiştir. Aşağıdaki adımlar, bu işlevlerin bu amaç için nasıl kullanılacağını gösterir.

### <a name="to-use-getbuffer-and-releasebuffer-to-access-the-internal-character-buffer-of-a-cstring-object"></a>Bir CString nesnesinin iç karakter arabelleği erişmek için GetBuffer ve ReleaseBuffer kullanmak için

1. Bir `GetBuffer` `CString` nesne çağırın ve istediğiniz arabelleğe uzunluklarını belirtin.

1. Karakterleri doğrudan `GetBuffer` `CString` nesneye yazmak için döndürülen işaretçiyi kullanın.

1. Nesnenin, `CString` dize uzunluğu `CString` gibi tüm iç durum bilgilerini güncelleştirmesini çağırın. `ReleaseBuffer` Bir `CString` nesnenin içeriğini doğrudan değiştirdikten sonra, diğer `ReleaseBuffer` `CString` üye işlevleri çağırmadan önce aramanız gerekir.

## <a name="using-cstring-objects-with-variable-argument-functions"></a><a name="_core_using_cstring_objects_with_variable_argument_functions"></a>Değişken Bağımsız değişken işlevleri olan CString Nesnelerini Kullanma

Bazı C işlevleri değişken sayıda bağımsız değişken alır. Önemli bir `printf_s`örnek . Bu tür bir işlevin beyan edilme biçimi nedeniyle, derleyici bağımsız değişkenlerin türünden emin olamaz ve her bağımsız değişkende hangi dönüştürme işleminin gerçekleştirileceğini belirleyemez. Bu nedenle, bir `CString` nesneyi değişken sayıda bağımsız değişken alan bir işleve geçirirken açık bir tür döküm kullanmanız esastır.

Değişken bağımsız `CString` değişken işlevinde bir nesneyi `CString` kullanmak için, aşağıdaki örnekte gösterildiği gibi açıkça bir LPCTSTR dizesini atın.

[!code-cpp[NVC_ATLMFC_Utilities#190](../atl-mfc-shared/codesnippet/cpp/cstring-operations-relating-to-c-style-strings_2.cpp)]

## <a name="specifying-cstring-formal-parameters"></a><a name="_core_specifying_cstring_formal_parameters"></a>CString Biçimsel Parametrelerin Belirtilmesi

Dize bağımsız değişkeni gerektiren çoğu işlev için, işlev prototipindeki resmi `const` parametreyi`LPCTSTR`bir karaktere `CString`işaretçi olarak belirtmek en iyisidir ( ) bir . Resmi bir parametre bir `const` karakteriçin işaretçi olarak belirtildiğinde, bir işaretçiyi Bir TCHAR`"hi there"`dizisine, `CString` bir gerçek dize [ ]]'e veya bir nesneye geçirebilirsiniz. Nesne `CString` otomatik olarak LPCTSTR dönüştürülür. LPCTSTR kullanabileceğiniz herhangi bir yerde, bir `CString` nesneyi de kullanabilirsiniz.

Bağımsız değişken değiştirilmezse, sabit bir dize başvurusu `const CString&`(diğer bir süre) olarak resmi bir parametre de belirtebilirsiniz. Dize işlev tarafından değiştirilecekse **const** değiştirici bırakın. Varsayılan null değeri istenirse, aşağıda gösterildiği gibi`""`[ ] null dizesine başharf:

[!code-cpp[NVC_ATLMFC_Utilities#191](../atl-mfc-shared/codesnippet/cpp/cstring-operations-relating-to-c-style-strings_3.cpp)]

Çoğu işlev sonucu için, bir `CString` nesneyi değere göre döndürmeniz yeterlidir.

## <a name="see-also"></a>Ayrıca bkz.

[Dizeleri (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[CString Bağımsız Değişken Geçirme](../atl-mfc-shared/cstring-argument-passing.md)
