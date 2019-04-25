---
title: Temel CString işlemleri
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, basic operations
- string literals, CString operations
- literal strings, CString operations
- CString objects
- string comparison, CString operations
- characters, accessing in CStrings
ms.assetid: 41db66b2-9427-4bb3-845a-9b6869159a6c
ms.openlocfilehash: 08c496038efc9e24e1c1610da07b6824c3a50b64
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62216863"
---
# <a name="basic-cstring-operations"></a>Temel CString işlemleri

Bu konu, aşağıdaki temel açıklar [CString](../atl-mfc-shared/reference/cstringt-class.md) işlemleri:

- [Standart C değişmez değer dizeleri CString nesneleri oluşturma](#_core_creating_cstring_objects_from_standard_c_literal_strings)

- [Tek bir CString karakterler erişme](#_core_accessing_individual_characters_in_a_cstring)

- [Birleştirme iki CString nesneleri](#_core_concatenating_two_cstring_objects)

- [CString nesneleri karşılaştırma](#_core_comparing_cstring_objects)

- [CString nesneleri dönüştürme](#_core_converting_cstring_objects)

`Class CString` sınıf şablonu temel alan [CStringT sınıfı](../atl-mfc-shared/reference/cstringt-class.md). `CString` olan bir **typedef** , `CStringT`. Daha fazla tam olarak `CString` olduğu bir **typedef** , bir *açık özelleştirme* , `CStringT`, bir sınıf tanımlamak için bir sınıf şablonu kullanmak için yaygın bir yolu olan. Benzer şekilde tanımlanan sınıflar `CStringA` ve `CStringW`.

`CString`, `CStringA`, ve `CStringW` yönelik baskılamayı kaldırma içinde tanımlanır. `CStringT` cstringt.h içinde tanımlanır.

`CString`, `CStringA`, ve `CStringW` bir dizi yöntem ve işleçleri tarafından tanımlanan her alma `CStringT` destekledikleri dize verileri ile kullanmak için. Bazı yöntemlere yinelenen ve bazı durumlarda, C çalışma zamanı kitaplıklarının dize Hizmetleri aşan.

Not: `CString` yerel bir sınıftır. C + kullanım için bir dize sınıfı için +/ CLI yönetilen proje, kullanım `System.String`.

##  <a name="_core_creating_cstring_objects_from_standard_c_literal_strings"></a> Standart C değişmez değer dizeleri CString nesneleri oluşturma

C stili değişmez değer dizeleri için atayabileceğiniz bir `CString` atayabilirsiniz gibi `CString` başka bir nesne.

- Bir C değişmez değer dize değerini atayın bir `CString` nesne.

   [!code-cpp[NVC_ATLMFC_Utilities#183](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_1.cpp)]

- Bir değer atamak `CString` diğerine `CString` nesne.

   [!code-cpp[NVC_ATLMFC_Utilities#184](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_2.cpp)]

   İçeriği bir `CString` bir nesne kopyalanır `CString` nesne diğerine atanır. Bu nedenle, iki dizeyi dizesini oluşturan gerçek karakterleri başvuru paylaşmayın. Nasıl kullanılacağı hakkında daha fazla bilgi için `CString` değerleri olarak bkz [CString semantiği](../atl-mfc-shared/cstring-semantics.md).

   > [!NOTE]
   > Böylece ANSI veya Unicode için derlenebilir uygulamanızı yazmak için değişmez değer dizeleri _T makrosu kullanarak kod. Daha fazla bilgi için [Unicode ve çok baytlı karakter kümesi (MBCS) desteği](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).

##  <a name="_core_accessing_individual_characters_in_a_cstring"></a> Tek bir CString karakterler erişme

Tek karakterler erişebileceğiniz bir `CString` kullanarak nesne `GetAt` ve `SetAt` yöntemleri. Dizi öğesi veya alt simge işleci ([]) yerine kullanabilirsiniz `GetAt` karakterlerin tek tek almak için. (Bu erişimi dizi öğeleri, standart C stili dizeler olduğu gibi bir dizine göre benzer.) Dizin değerlerini `CString` sıfır tabanlı karakter.

##  <a name="_core_concatenating_two_cstring_objects"></a> Birleştirme iki CString nesneleri

İki birleştirmek için `CString` nesneleri, birleştirme işleçleri kullanın (+ veya +=) aşağıdaki gibi.

[!code-cpp[NVC_ATLMFC_Utilities#185](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_3.cpp)]

Birleştirme işleçleri için en az bir bağımsız değişken (+ veya +=) olmalıdır bir `CString` nesne, ancak bir sabit karakter dizesi kullanabilirsiniz (örneğin, `"big"`) veya bir **char** (örneğin, ' x'), diğer bağımsız değişkeni.

##  <a name="_core_comparing_cstring_objects"></a> CString nesneleri karşılaştırma

`Compare` Yöntemi ve == işleci için `CString` eşdeğerdir. `Compare`, **işleç ==**, ve `CompareNoCase` MBCS ve Unicode; farkında `CompareNoCase` ayrıca büyük küçük harfe duyarlıdır. `Collate` Yöntemi `CString` yerel ayar duyarlı ve genellikle daha yavaş ise `Compare`. Kullanım `Collate` yalnızca burada, sıralama uymanız gerekir kuralları belirtildiği gibi geçerli yerel ayar tarafından.

Aşağıdaki tabloda kullanılabilir gösterilmektedir [CString](../atl-mfc-shared/reference/cstringt-class.md) karşılaştırma işlevleri ve eşdeğer MBCS/Unicode-taşınabilir işlevlerini C Çalışma Zamanı Kitaplığı'nda.

|CString işlevi|MBCS işlevi|Unicode işlevi|
|----------------------|-------------------|----------------------|
|`Compare`|`_mbscmp`|`wcscmp`|
|`CompareNoCase`|`_mbsicmp`|`_wcsicmp`|
|`Collate`|`_mbscoll`|`wcscoll`|

`CStringT` Sınıf şablonu ilişkisel işleçlerini tanımlar (<, \<=, > =, >, ==, ve! =), tarafından kullanılmak üzere sağlanan `CString`. İki karşılaştırabilirsiniz `CStrings` aşağıdaki örnekte gösterildiği gibi bu işleçleri kullanarak.

[!code-cpp[NVC_ATLMFC_Utilities#186](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_4.cpp)]

##  <a name="_core_converting_cstring_objects"></a> CString nesneleri dönüştürme

CString nesneleri diğer dize türlerine dönüştürme hakkında daha fazla bilgi için bkz: [nasıl yapılır: Çeşitli dize türleri arasında dönüştürme](../text/how-to-convert-between-various-string-types.md).

## <a name="using-cstring-with-wcout"></a>Wcout ile CString kullanma

Bir CString ile kullanılacak `wcout` nesneyi açıkça dönüştürmelisiniz bir `const wchar_t*` aşağıdaki örnekte gösterildiği gibi:

```cpp
CString cs("meow");

wcout << (const wchar_t*) cs << endl;
```

Tür dönüştürme olmadan `cs` olarak kabul bir `void*` ve `wcout` nesnenin adresi yazdırır. Bu davranış, C++ standardı ile doğru kendileri şablon bağımsız değişkeni kesintisi ve aşırı yükleme çözümlemesi uyumlu arasındaki Zarif etkileşimler kaynaklanır.

## <a name="see-also"></a>Ayrıca bkz.

[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[CStringT Sınıfı](../atl-mfc-shared/reference/cstringt-class.md)<br/>
[Şablon Uzmanlığı](../cpp/template-specialization-cpp.md)<br/>
[Nasıl yapılır: Çeşitli Dize Türleri Arasında Dönüştürme](../text/how-to-convert-between-various-string-types.md)
