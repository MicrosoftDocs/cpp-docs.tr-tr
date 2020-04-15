---
title: Temel CString İşlemleri
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, basic operations
- string literals, CString operations
- literal strings, CString operations
- CString objects
- string comparison, CString operations
- characters, accessing in CStrings
ms.assetid: 41db66b2-9427-4bb3-845a-9b6869159a6c
ms.openlocfilehash: 68947dc37e5398ac7caa4754e9af40223cec7bf2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317955"
---
# <a name="basic-cstring-operations"></a>Temel CString İşlemleri

Bu konu aşağıdaki temel [CString](../atl-mfc-shared/reference/cstringt-class.md) işlemlerini açıklar:

- [Standart C harfi dizelerinden CString nesneleri oluşturma](#_core_creating_cstring_objects_from_standard_c_literal_strings)

- [CString'te tek tek karakterlere erişim](#_core_accessing_individual_characters_in_a_cstring)

- [İki CString nesnesi bağlama](#_core_concatenating_two_cstring_objects)

- [CString nesnelerini karşılaştırma](#_core_comparing_cstring_objects)

- [CString nesnelerini dönüştürme](#_core_converting_cstring_objects)

`Class CString`sınıf şablonu [CStringT Sınıfı'nı](../atl-mfc-shared/reference/cstringt-class.md)temel alınmaktadır. `CString`bir **typedef** `CStringT`olduğunu . Daha `CString` doğrusu, bir sınıf tanımlamak için `CStringT`bir sınıf şablonu kullanmak için ortak bir yoldur , *açık* bir uzmanlık **bir typedef** olduğunu. Benzer şekilde tanımlanmış `CStringA` `CStringW`sınıflar ve .

`CString`, `CStringA`ve `CStringW` atlstr.h tanımlanır. `CStringT`cstringt.h tanımlanır.

`CString`, `CStringA`ve `CStringW` her biri destekledikleri dize `CStringT` verileriyle kullanılmak üzere tanımlanan yöntem ve işleçlerden oluşan bir küme alır. Bazı yöntemler yinelenen ve bazı durumlarda, C çalışma zamanı kitaplıklarının dize hizmetlerini aşar.

Not: `CString` yerel bir sınıftır. C++/CLI yönetilen bir projede kullanılmak üzere olan `System.String`bir dize sınıfı için.

## <a name="creating-cstring-objects-from-standard-c-literal-strings"></a><a name="_core_creating_cstring_objects_from_standard_c_literal_strings"></a>Standart C Literal Dizelerden CString Nesneleri Oluşturma

C stili edebi dizeleri bir `CString` `CString` nesneyi diğerine atayabileceğiniz gibi atayabilirsiniz.

- C harfi dizesinin değerini bir `CString` nesneye atayın.

   [!code-cpp[NVC_ATLMFC_Utilities#183](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_1.cpp)]

- Bir nesnenin `CString` değerini başka `CString` bir nesneye atayın.

   [!code-cpp[NVC_ATLMFC_Utilities#184](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_2.cpp)]

   Bir `CString` nesnenin içeriği, bir `CString` nesne diğerine atandığında kopyalanır. Bu nedenle, iki dize dize oluşturan gerçek karakterler için bir başvuru paylaşmaz. Nesnelerin değer olarak nasıl `CString` kullanılacağı hakkında daha fazla bilgi için [Bkz. CString Semantics.](../atl-mfc-shared/cstring-semantics.md)

   > [!NOTE]
   > Uygulamanızı Unicode veya ANSI için derlenebilecek şekilde yazmak için, _T makroyu kullanarak gerçek dizeleri kodlayın. Daha fazla bilgi için [Unicode ve Multibyte Karakter Kümesi (MBCS) Desteği'ne](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)bakın.

## <a name="accessing-individual-characters-in-a-cstring"></a><a name="_core_accessing_individual_characters_in_a_cstring"></a>CString'te tek tek karakterlere erişme

Bir `CString` nesnedeki tek tek karakterlere, `GetAt` `SetAt` yöntemleri ve yöntemleri kullanarak erişebilirsiniz. Ayrıca, tek tek karakterler almak yerine `GetAt` dizi öğesini veya alt yazıyı ( [ ] ) operatörde de kullanabilirsiniz. (Bu, standart C stili dizeleri gibi dizi öğelerine dizin tarafından erişmebenzer.) Karakterler için `CString` dizin değerleri sıfır tabanlıdır.

## <a name="concatenating-two-cstring-objects"></a><a name="_core_concatenating_two_cstring_objects"></a>İki CString Nesnesi Bağlama

İki `CString` nesneyi birleştirmek için, aşağıdaki gibi birluzasyon işleçlerini (+ veya +=) kullanın.

[!code-cpp[NVC_ATLMFC_Utilities#185](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_3.cpp)]

Concatenation işleçleri için en az bir bağımsız değişken `CString` (+ veya +=) bir nesne `"big"`olmalıdır, ancak diğer bağımsız değişken için sabit bir karakter dizesi (örneğin, ) veya **bir char** (örneğin, 'x') kullanabilirsiniz.

## <a name="comparing-cstring-objects"></a><a name="_core_comparing_cstring_objects"></a>CString Nesnelerini Karşılaştırma

Yöntem `Compare` ve == işleci `CString` eşdeğerdir. `Compare`, **operator==** `CompareNoCase` , ve MBCS ve Unicode farkında; `CompareNoCase` da büyük/küçük harf duyarsız. Yöntem `Collate` yerel `CString` duyarlıdır ve genellikle `Compare`daha yavaştır. Yalnızca `Collate` geçerli yerel olarak belirtilen sıralama kurallarına uymanız gereken yerlerde kullanın.

Aşağıdaki tablo, C çalışma zamanı kitaplığında kullanılabilir [CString](../atl-mfc-shared/reference/cstringt-class.md) karşılaştırma işlevlerini ve bunların eşdeğeruna ait Unicode/MBCS-taşınabilir işlevlerini gösterir.

|CString fonksiyonu|MBCS fonksiyonu|Unicode fonksiyonu|
|----------------------|-------------------|----------------------|
|`Compare`|`_mbscmp`|`wcscmp`|
|`CompareNoCase`|`_mbsicmp`|`_wcsicmp`|
|`Collate`|`_mbscoll`|`wcscoll`|

Sınıf `CStringT` şablonu, >, ==ve \<!=) tarafından `CString`kullanılabilen ilişkisel işleçleri (<, =, >, >, ==ve !=) tanımlar. Aşağıdaki örnekte `CStrings` gösterildiği gibi, bu işleçleri kullanarak iki karşılaştırabilirsiniz.

[!code-cpp[NVC_ATLMFC_Utilities#186](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_4.cpp)]

## <a name="converting-cstring-objects"></a><a name="_core_converting_cstring_objects"></a>CString Nesnelerini Dönüştürme

CString nesnelerini diğer dize türlerine dönüştürme hakkında bilgi için [bkz.](../text/how-to-convert-between-various-string-types.md)

## <a name="using-cstring-with-wcout"></a>Wcout ile CString kullanma

Bir CString'i `wcout` kullanmak için nesneyi aşağıdaki `const wchar_t*` örnekte gösterildiği gibi açıkça bir nesneye atmalısınız:

```cpp
CString cs("meow");

wcout << (const wchar_t*) cs << endl;
```

Döküm olmadan, `cs` bir `void*` olarak `wcout` kabul edilir ve nesnenin adresini yazdırır. Bu davranış, şablon bağımsız değişken tümlemesi ve c++ standardına uygun kendi içinde doğru ve uyumlu aşırı yükleme çözünürlüğü arasındaki ince etkileşimlerden kaynaklanır.

## <a name="see-also"></a>Ayrıca bkz.

[Dizeleri (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[CStringT Sınıfı](../atl-mfc-shared/reference/cstringt-class.md)<br/>
[Şablon Uzmanlığı](../cpp/template-specialization-cpp.md)<br/>
[Nasıl yapılır: Çeşitli Dize Türleri Arasında Dönüştürme Yapma](../text/how-to-convert-between-various-string-types.md)
