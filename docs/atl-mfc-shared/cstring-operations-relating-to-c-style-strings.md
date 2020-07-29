---
title: C stili dizeleriyle Ilgili CString Işlemleri
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
ms.openlocfilehash: bbf483703b04c26c9462e4fe6adb08b614e440f7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222049"
---
# <a name="cstring-operations-relating-to-c-style-strings"></a>C stili dizeleriyle Ilgili CString Işlemleri

Bir [CString](../atl-mfc-shared/using-cstring.md) nesnesi karakter dizesi verisi içerir. `CString`dize verileriyle çalışmak için [CStringT](../atl-mfc-shared/reference/cstringt-class.md) Sınıf şablonunda tanımlanan [yöntemlerin ve işleçlerin](../atl-mfc-shared/reference/cstringt-class.md) kümesini devralır. (tarafından `CString` **`typedef`** `CStringT` Desteklenen karakter verisi türüyle çalışmayı uzmanlaşmış bir türüdür `CString` .)

`CString`karakter verilerini dahili olarak C stili null ile sonlandırılmış bir dize olarak depolamaz. Bunun yerine, `CString` veri ve gereken alanı daha güvenli bir şekilde izleyebilmesi için karakter verilerinin uzunluğunu izler.

`CString`C stili dizeler kabul eder ve karakter verilerine C stili dize olarak erişmek için yollar sağlar. Bu konu, bir `CString` nesnenin C stili null ile sonlandırılmış bir dize gibi nasıl kullanılacağını açıklayan aşağıdaki bölümleri içerir.

- [C stili null ile sonlandırılmış dizelere dönüştürme](#_core_using_cstring_as_a_c.2d.style_null.2d.terminated_string)

- [Standart çalışma zamanı kitaplık dizesi işlevleriyle çalışma](#_core_working_with_standard_run.2d.time_library_string_functions)

- [CString içeriğini doğrudan değiştirme](#_core_modifying_cstring_contents_directly)

- [Değişken bağımsız değişken işlevleriyle CString nesnelerini kullanma](#_core_using_cstring_objects_with_variable_argument_functions)

- [CString biçimsel parametrelerini belirtme](#_core_specifying_cstring_formal_parameters)

## <a name="using-cstring-as-a-c-style-null-terminated-string"></a><a name="_core_using_cstring_as_a_c.2d.style_null.2d.terminated_string"></a>C stili null ile sonlandırılmış bir dize olarak CString kullanma

Bir `CString` nesneyi C stili dize olarak kullanmak için, NESNEYI LPCTSTR öğesine atayın. Aşağıdaki örnekte, bir `CString` salt okunurdur C stili null ile sonlandırılmış dizeye bir işaretçi döndürür. `strcpy`İşlevi, değişkenine C stili dizenin bir kopyasını koyar `myString` .

```cpp
CString aCString = "A string";
char myString[256];
strcpy(myString, (LPCTSTR)aCString);
```

`CString` `SetAt` Dize nesnesindeki tek karakterleri değiştirmek için, örneğin, yöntemlerini kullanabilirsiniz. Ancak, LPCTSTR işaretçisi geçicidir ve üzerinde herhangi bir değişiklik yapıldığında geçersiz hale gelir `CString` . `CString`Ayrıca kapsam dışı geçebilir ve otomatik olarak silinebilir. Her kullandığınızda bir nesne için yeni bir LPCTSTR işaretçisi almanızı öneririz `CString` .

Bazen `CString` doğrudan değiştirmek üzere verilerin bir kopyasının olmasını isteyebilirsiniz. `strcpy_s` `_tcscpy_s` Nesneyi ayrı bir arabelleğe kopyalamak için daha güvenli bir işlev (veya UNICODE/MBCS-taşınabilir) kullanın `CString` . Bu, aşağıdaki örnekte gösterildiği gibi karakterlerin güvenli bir şekilde değiştirilebileceği yerdir.

[!code-cpp[NVC_ATLMFC_Utilities#189](../atl-mfc-shared/codesnippet/cpp/cstring-operations-relating-to-c-style-strings_1.cpp)]

> [!NOTE]
> `strcpy_s`(Veya Unicode/mbcs-taşınabilir) için üçüncü bağımsız değişken `_tcscpy_s` bir `const wchar_t*` (Unicode) ya da `const char*` (ANSI). Yukarıdaki örnekte `CString` Bu bağımsız değişken için bir geçirilir. C++ derleyicisi, ' a dönüştüren sınıf için tanımlanan dönüştürme işlevini otomatik olarak uygular `CString` `CString` `LPCTSTR` . Tek bir türden diğerine atama işlemlerini tanımlama özelliği, C++ ' ın en faydalı özelliklerinden biridir.

## <a name="working-with-standard-run-time-library-string-functions"></a><a name="_core_working_with_standard_run.2d.time_library_string_functions"></a>Standart çalışma zamanı kitaplık dizesi Işlevleriyle çalışma

`CString` `strcmp` (Veya UNICODE/MBCS-taşınabilir) gibi standart C çalışma zamanı kitaplık dizesi işlevlerini kullanmayı düşünebileceğiniz herhangi bir dize işlemini gerçekleştirmek için bir yöntem bulabilmelisiniz `_tcscmp` .

C çalışma zamanı dize işlevlerini kullanmanız gerekiyorsa _core_using_cstring_as_a_c. 2D. style_null. 2D. terminated_string bölümünde açıklanan teknikleri kullanabilirsiniz. `CString`Nesneyi eşdeğer bir C stili dize arabelleğine kopyalayabilir, işlemlerinizi arabellekte gerçekleştirebilir ve sonra elde edilen C stili dizesini bir nesneye geri atayabilirsiniz `CString` .

## <a name="modifying-cstring-contents-directly"></a><a name="_core_modifying_cstring_contents_directly"></a>CString Içeriğini doğrudan değiştirme

Çoğu durumda, `CString` bir nesnenin içeriğini değiştirmek `CString` veya öğesini `CString` C stili karakter dizesine dönüştürmek için üye işlevlerini kullanmanız gerekir.

`CString`Örneğin, bir karakter arabelleği gerektiren işletim sistemi işlevleriyle çalışırken, içeriği doğrudan değiştirmek için anlamlı olduğu bazı durumlar vardır.

`GetBuffer`Ve `ReleaseBuffer` yöntemleri bir nesnenin iç karakter arabelleğine erişim sağlar `CString` ve bunu doğrudan değiştirmenize izin verir. Aşağıdaki adımlarda bu işlevlerin bu amaçla nasıl kullanılacağı gösterilmektedir.

### <a name="to-use-getbuffer-and-releasebuffer-to-access-the-internal-character-buffer-of-a-cstring-object"></a>Bir CString nesnesinin iç karakter arabelleğine erişmek için GetBuffer ve ReleaseBuffer kullanmak için

1. `GetBuffer`Bir nesnesi için çağrı yapın `CString` ve ihtiyacınız olan arabelleğin uzunluğunu belirtin.

1. `GetBuffer`Karakterleri doğrudan nesneye yazmak için tarafından döndürülen işaretçiyi kullanın `CString` .

1. `ReleaseBuffer` `CString` Tüm iç durum bilgilerini güncelleştirmek için nesnesi için çağrı `CString` yapın, örneğin, dizenin uzunluğu. Bir nesnenin içeriğini doğrudan değiştirdikten sonra `CString` , `ReleaseBuffer` başka bir üye işlevi çağırmadan önce öğesini çağırmanız gerekir `CString` .

## <a name="using-cstring-objects-with-variable-argument-functions"></a><a name="_core_using_cstring_objects_with_variable_argument_functions"></a>Değişken bağımsız değişken Işlevleriyle CString nesnelerini kullanma

Bazı C işlevleri değişken sayıda bağımsız değişken alır. Bir önemli örneği `printf_s` . Bu tür bir işlevin bildirildiği gibi, derleyici bağımsız değişkenlerin türünden emin olamaz ve her bağımsız değişkende hangi dönüştürme işleminin gerçekleştirileceğini belirleyemez. Bu nedenle, bir `CString` nesneyi değişken sayıda bağımsız değişken alan bir işleve geçirirken açık tür dönüştürme kullanmanız gereklidir.

`CString`Değişken bağımsız değişken işlevinde bir nesne kullanmak için, `CString` Aşağıdaki örnekte gösterildiği gibi, öğesini açıkça bir LPCTSTR dizesine atayın.

[!code-cpp[NVC_ATLMFC_Utilities#190](../atl-mfc-shared/codesnippet/cpp/cstring-operations-relating-to-c-style-strings_2.cpp)]

## <a name="specifying-cstring-formal-parameters"></a><a name="_core_specifying_cstring_formal_parameters"></a>CString biçimsel parametrelerini belirtme

Bir dize bağımsız değişkenine ihtiyacı olan çoğu işlev için, işlev prototipinde biçimsel parametresini, **`const`** yerine bir karakter () işaretçisi olarak belirtmek en iyisidir `LPCTSTR` `CString` . Biçimsel bir parametre **`const`** bir karakter işaretçisi olarak belirtildiğinde, BIR TCHAR dizisine, sabit dize [ `"hi there"` ] veya bir nesneye işaretçi geçirebilirsiniz `CString` . `CString`Nesne otomatik olarak BIR LPCTSTR olarak dönüştürülecek. Herhangi bir yerde bir LPCTSTR kullanabilirsiniz, bir nesnesi de kullanabilirsiniz `CString` .

Bağımsız değişken değiştirilmemişse, bir sabit dize başvurusu (yani,) olarak bir biçimsel parametre da belirtebilirsiniz `const CString&` . **`const`** Dize işlev tarafından değiştirilirse değiştiriciyi bırakın. Varsayılan bir null değer isteniyorsa, bunu aşağıda gösterildiği gibi null dize [] olarak başlatın `""` :

[!code-cpp[NVC_ATLMFC_Utilities#191](../atl-mfc-shared/codesnippet/cpp/cstring-operations-relating-to-c-style-strings_3.cpp)]

Çoğu işlev sonucu için yalnızca `CString` değere göre bir nesne döndürebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[CString bağımsız değişken geçirme](../atl-mfc-shared/cstring-argument-passing.md)
