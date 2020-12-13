---
description: 'Daha fazla bilgi edinin: Basic CString Operations'
title: Temel CString Işlemleri
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, basic operations
- string literals, CString operations
- literal strings, CString operations
- CString objects
- string comparison, CString operations
- characters, accessing in CStrings
ms.assetid: 41db66b2-9427-4bb3-845a-9b6869159a6c
ms.openlocfilehash: abd64445efbfd6afb26dc023b3a0451bedcc1e5e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142526"
---
# <a name="basic-cstring-operations"></a>Temel CString Işlemleri

Bu konu başlığı altında, aşağıdaki temel [CString](../atl-mfc-shared/reference/cstringt-class.md) işlemleri açıklanmaktadır:

- [Standart C değişmez dizelerinden CString nesneleri oluşturma](#_core_creating_cstring_objects_from_standard_c_literal_strings)

- [Bir CString içindeki tek tek karakterlere erişme](#_core_accessing_individual_characters_in_a_cstring)

- [İki CString nesnesini bitiştirme](#_core_concatenating_two_cstring_objects)

- [CString nesnelerini karşılaştırma](#_core_comparing_cstring_objects)

- [CString nesnelerini dönüştürme](#_core_converting_cstring_objects)

`Class CString` sınıf şablonu [CStringT sınıfına](../atl-mfc-shared/reference/cstringt-class.md)dayalıdır. `CString` , ' **`typedef`** dır `CStringT` . Daha açık olarak, bir `CString` **`typedef`** sınıf tanımlamak için bir sınıf şablonu kullanmanın yaygın bir yolu olan *açık bir özelleşmenin* bir `CStringT` yoludur. Benzer şekilde tanımlanmış sınıflar `CStringA` ve ' dir `CStringW` .

`CString`, `CStringA` ve, `CStringW` atlstr. h içinde tanımlanır. `CStringT` CStringT. h içinde tanımlanır.

`CString`, `CStringA` ve `CStringW` her biri, desteklediği `CStringT` dize verileriyle kullanılmak üzere tarafından tanımlanan yöntemlerin ve işleçlerin bir kümesini alır. Yöntemlerin bazıları yineleniyor ve bazı durumlarda C çalışma zamanı kitaplıklarının dize hizmetlerini ortaya geçirin.

Note: `CString` yerel bir sınıftır. C++/CLı tarafından yönetilen bir projede kullanılmak üzere olan bir dize sınıfı için kullanın `System.String` .

## <a name="creating-cstring-objects-from-standard-c-literal-strings"></a><a name="_core_creating_cstring_objects_from_standard_c_literal_strings"></a> Standart C değişmez dizelerinden CString nesneleri oluşturma

`CString`Tek bir nesneyi başka bir nesneye atayabilmeniz için, yalnızca bir öğesine C stili değişmez dizeler atayabilirsiniz `CString` .

- Bir C sabit dizesinin değerini bir `CString` nesnesine atayın.

   [!code-cpp[NVC_ATLMFC_Utilities#183](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_1.cpp)]

- Bir öğesinin değerini `CString` başka bir nesneye atayın `CString` .

   [!code-cpp[NVC_ATLMFC_Utilities#184](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_2.cpp)]

   Bir nesne başka bir `CString` nesne atandığında bir nesnenin içeriği `CString` kopyalanır. Bu nedenle, iki dize, dizeyi oluşturan gerçek karakterlere bir başvuru paylaşmaz. Nesnelerin değer olarak nasıl kullanılacağı hakkında daha fazla bilgi için `CString` bkz. [CString semantiği](../atl-mfc-shared/cstring-semantics.md).

   > [!NOTE]
   > Uygulamanızı, Unicode veya ANSI için derlenebilecek şekilde yazmak için _T makrosunu kullanarak kod sabiti dizelerini kodlayın. Daha fazla bilgi için bkz. [Unicode ve çok baytlı karakter kümesi (MBCS) desteği](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).

## <a name="accessing-individual-characters-in-a-cstring"></a><a name="_core_accessing_individual_characters_in_a_cstring"></a> Bir CString içindeki tek tek karakterlere erişme

`CString`Ve yöntemlerini kullanarak bir nesnedeki tek tek karakterlere erişebilirsiniz `GetAt` `SetAt` . Tek tek karakterleri almak için yerine Array öğesi veya alt simge, işleç ([]) de kullanabilirsiniz `GetAt` . (Bu, standart C stili dizelerde olduğu gibi dizi öğelerine dizine göre erişilmesine benzer.) Karakterlerin Dizin değerleri `CString` sıfır tabanlıdır.

## <a name="concatenating-two-cstring-objects"></a><a name="_core_concatenating_two_cstring_objects"></a> Iki CString nesnesini bitiştirme

İki nesneyi birleştirmek için `CString` aşağıdaki gibi birleştirme işleçlerini (+ veya + =) kullanın.

[!code-cpp[NVC_ATLMFC_Utilities#185](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_3.cpp)]

Birleştirme işleçleri (+ veya + =) için en az bir bağımsız değişken bir nesne olmalıdır `CString` , ancak diğer bağımsız değişken için sabit bir karakter dizesi (örneğin, `"big"` ) veya bir **`char`** (örneğin, ' x ') kullanabilirsiniz.

## <a name="comparing-cstring-objects"></a><a name="_core_comparing_cstring_objects"></a> CString nesnelerini karşılaştırma

`Compare`İçin yöntemi ve = = işleci `CString` eşdeğerdir. `Compare`, **işleç = =** ve `CompareNoCase` MBCS ve Unicode ile uyumlu; `CompareNoCase` büyük/küçük harfe duyarsızdır. `Collate`Yöntemi, `CString` yerel ayara duyarlıdır ve genellikle daha yavaştır `Compare` . `Collate`Yalnızca geçerli yerel ayar tarafından belirtilen sıralama kurallarına göre her yerde bilmeniz gereken yeri kullanın.

Aşağıdaki tabloda, C çalışma zamanı kitaplığındaki kullanılabilir [CString](../atl-mfc-shared/reference/cstringt-class.md) karşılaştırma işlevleri ve bunların eşdeğer UNICODE/MBCS-taşınabilir işlevleri gösterilmektedir.

|CString işlevi|MBCS işlevi|Unicode işlevi|
|----------------------|-------------------|----------------------|
|`Compare`|`_mbscmp`|`wcscmp`|
|`CompareNoCase`|`_mbsicmp`|`_wcsicmp`|
|`Collate`|`_mbscoll`|`wcscoll`|

`CStringT`Sınıf şablonu, tarafından kullanılabilecek İlişkisel işleçleri (<, \<=, > =, >, = = ve! =) tanımlar `CString` . `CStrings`Aşağıdaki örnekte gösterildiği gibi bu işleçleri kullanarak ikisini de karşılaştırabilirsiniz.

[!code-cpp[NVC_ATLMFC_Utilities#186](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_4.cpp)]

## <a name="converting-cstring-objects"></a><a name="_core_converting_cstring_objects"></a> CString nesnelerini dönüştürme

CString nesnelerini diğer dize türlerine dönüştürme hakkında daha fazla bilgi için bkz. [nasıl yapılır: çeşitli dize türleri arasında dönüştürme](../text/how-to-convert-between-various-string-types.md).

## <a name="using-cstring-with-wcout"></a>Wcout ile CString kullanma

İle CString kullanmak için `wcout` , `const wchar_t*` Aşağıdaki örnekte gösterildiği gibi nesneyi açıkça öğesine atamalısınız:

```cpp
CString cs("meow");

wcout << (const wchar_t*) cs << endl;
```

Atama olmadan, `cs` bir olarak değerlendirilir **`void*`** ve `wcout` nesnesinin adresini yazdırır. Bu davranış, şablon bağımsız değişken kesintisi ve kendi üzerinde olan ve C++ standardı ile uyumlu olan aşırı yükleme çözümlemesi arasındaki hafif etkileşimler nedeniyle oluşur.

## <a name="see-also"></a>Ayrıca bkz.

[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[CStringT sınıfı](../atl-mfc-shared/reference/cstringt-class.md)<br/>
[Şablon özelleştirmesi](../cpp/template-specialization-cpp.md)<br/>
[Nasıl yapılır: çeşitli dize türleri arasında dönüştürme](../text/how-to-convert-between-various-string-types.md)
