---
description: 'Daha fazla bilgi edinin: dizeler (C++/CX)'
title: Dizeler (C++/CX)
ms.date: 01/22/2017
ms.assetid: 5b34e1df-7c2b-4269-aba8-b767d36c49d9
ms.openlocfilehash: 83ea4cd86b57e8bfd81968cbb617b7b8af81b978
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307619"
---
# <a name="strings-ccx"></a>Dizeler (C++/CX)

Windows Çalışma Zamanı metin, C++/CX ile [Platform:: String sınıfı](../cppcx/platform-string-class.md)tarafından temsil edilir. `Platform::String Class`Dizeleri Windows çalışma zamanı sınıflardaki yöntemlere geri ve ileri geçirdiğinizde veya uygulama ikili arabirimi (ABI) sınırları genelinde diğer Windows çalışma zamanı bileşenleriyle etkileşim kurarken kullanın. , `Platform::String Class` Birkaç yaygın dize işlemi için yöntemler sağlar, ancak tam özellikli bir dize sınıfı olacak şekilde tasarlanmamıştır. C++ modülünüzün herhangi bir önemli metin işleme için [wstring](../standard-library/basic-string-class.md) gibi standart C++ dize türlerini kullanın ve ardından son sonucu, genel arabirime veya ortak bir arabirimden geçirmeden önce [Platform:: String ^](../cppcx/platform-string-class.md) olarak dönüştürün. Veya arasında dönüştürme kolay ve verimlidir `wstring` `wchar_t*` `Platform::String` .

**Hızlı geçiş**

Bazı durumlarda, derleyici, `Platform::String` `String` temel alınan dize verilerini kopyalamadan bir işleve güvenle bir şekilde bir şekilde veri kurabilecebildiğini veya geçirebildiğini doğrulayabilirler. Bu gibi işlemler *Hızlı geçiş* olarak bilinir ve saydam olarak oluşur.

## <a name="string-construction"></a>Dize oluşturma

Bir nesnenin değeri, `String` `char16` (16 bit Unicode) karakterlerinden oluşan sabit bir (salt okunurdur) dizidir. Bir `String` nesne sabit olduğundan, bir değişkene yeni bir dize sabit değeri atanması `String` aslında özgün `String` nesnenin yerini yeni bir `String` nesneyle değiştirir. Birleştirme işlemleri özgün nesnenin yok edilmesini `String` ve yeni bir nesne oluşturulmasını içerir.

**Değişmez Değerler**

*Sabit karakter* , tek tırnak işareti içine alınmış bir karakterdir ve *sabit dize* , çift tırnak işareti içine alınmış bir karakter dizisidir. Dize ^ değişkenini başlatmak için bir değişmez değer kullanırsanız, derleyici değişmez değerin karakterlerden oluştuğunu varsayar `char16` . Diğer bir deyişle, ' L ' dize değiştiricisiyle veya değişmez değeri bir **_T ()** ya da **metin ()** makrosunda almanız gerekmez. Unicode için C++ desteği hakkında daha fazla bilgi için bkz. [Unicode Programlama Özeti](../text/unicode-programming-summary.md).

Aşağıdaki örnek, nesneleri oluşturmak için çeşitli yollar gösterir `String` .

[!code-cpp[cx_strings#01](../cppcx/codesnippet/CPP/cppcx_strings/class1.cpp#01)]

## <a name="string-handling-operations"></a>Dize işleme işlemleri

`String`Sınıfı, dizeleri ve diğer temel dize işlemlerini bitişme, karşılaştırma için yöntemler ve işleçler sağlar. Daha kapsamlı dize düzenlemeleri gerçekleştirmek için `String::Data()` üye işlevini kullanarak `String^` nesnesinin değerini bir olarak alın `const wchar_t*` . Daha sonra bu değeri kullanarak `std::wstring` , zengin dize işleme işlevleri sağlayan bir ' ı başlatın.

[!code-cpp[cx_strings#03](../cppcx/codesnippet/CPP/cppcx_strings/class1.cpp#03)]

## <a name="string-conversions"></a>Dize dönüştürmeleri

`Platform::String` `char16` , Yalnızca karakter veya `NULL` karakter içerebilir. Uygulamanızın 8 bitlik karakterlerle çalışması gerekiyorsa, metni bir olarak ayıklamak için [::D ata dizesini](../cppcx/platform-string-class.md#data) kullanın `const wchar_t*` . Daha sonra, veriler üzerinde işlem yapmak ve bunu bir veya wstring 'e dönüştürmek için uygun Windows işlevleri veya standart kitaplık işlevlerini kullanabilir ve bunu `wchar_t*` Yeni bir oluşturmak için [](../standard-library/basic-string-class.md)kullanabilirsiniz `Platform::String` .

Aşağıdaki kod parçası, bir `String^` değişkenin bir değişkene ve bir değişkene nasıl dönüştürüleceğini gösterir `wstring` . Bu örnekte kullanılan dize düzenlemesi hakkında daha fazla bilgi için, bkz. [basic_string:: Replace](../standard-library/basic-string-class.md#replace).

[!code-cpp[cx_strings#04](../cppcx/codesnippet/CPP/cppcx_strings/class1.cpp#04)]

## <a name="string-length-and-embedded-null-values"></a>Dize uzunluğu ve gömülü NULL değerleri

[Dize:: length](../cppcx/platform-string-class.md#length) , bayt sayısını değil dizedeki karakter sayısını döndürür. Bir dize oluşturmak için yığın semantiğini kullandığınızda onu açıkça belirtmediğiniz müddetçe, Sonlandırıcı NULL karakteri sayılmaz.

`Platform::String`Yalnızca null bir birleştirme işleminin sonucu olduğunda, gömülü null değerler içerebilir. Gömülü null değerler dize sabit değerlerinde desteklenmez; Bu nedenle, öğesini başlatmak için gömülü null değerleri bu şekilde kullanamazsınız `Platform::String` . Bir öğesine gömülü NULL değerler `Platform::String` dize görüntülenirken yok sayılır, örneğin, bir `TextBlock::Text` özelliğe atandığında. Dize değeri özelliği tarafından döndürüldüğünde gömülü null değerler kaldırılır `Data` .

## <a name="stringreference"></a>StringReference

Bazı durumlarda, kodunuz (a) bir std:: wstring veya wchar_t String ya da L "" dize sabit değeri alır ve bunu yalnızca giriş parametresi olarak ^ dizesi alan başka bir yönteme geçirir. Özgün dize arabelleğinin kendisi geçerli kaldığı ve işlevin döndürdüğü bir zaman olmadığı sürece, `wchar_t*` String veya String değişmez değerini bir [Platform:: stringreference](../cppcx/platform-stringreference-class.md)öğesine dönüştürebilir ve yerine bunu geçirebilirsiniz `Platform::String^` . `StringReference`İçin Kullanıcı tanımlı bir dönüştürmesi olduğundan buna izin verilir `Platform::String^` . Kullanarak, `StringReference` dize verilerinin fazladan bir kopyasını yapmaktan kaçınabilirsiniz. Çok sayıda dizeyi geçirdiğiniz veya çok büyük dizeleri geçirirken Döngülerde, kullanarak önemli bir performans geliştirmesi elde edebilirsiniz `StringReference` . Ancak `StringReference` asıl dize arabelleğini temel alarak, bellek bozulmasını önlemek için çok dikkatli olmanız gerekir. `StringReference`Özgün dizenin, bu yöntemin döndürdüğü zaman kapsamda olması garanti edilmediği takdirde, bir zaman uyumsuz metoda geçirmemelisiniz. Bir StringReference 'dan başlatılan ^ dizesi, ikinci bir atama işlemi gerçekleşirse dize verilerinin bir ayırmasını ve kopyasını zorlar. Bu durumda, ' nin performans avantajını kaybedersiniz `StringReference` .

`StringReference`Bir başvuru sınıfı değil, standart bir C++ sınıf türü olduğunu unutmayın, bunu tanımladığınız başvuru sınıflarının ortak arabiriminde kullanamazsınız.

Aşağıdaki örnek, StringReference 'ın nasıl kullanılacağını gösterir:

```cpp
void GetDecodedStrings(std::vector<std::wstring> strings)
{
    using namespace Windows::Security::Cryptography;
    using namespace Windows::Storage::Streams;

    for (auto&& s : strings)
    {
        // Method signature is IBuffer^ CryptographicBuffer::DecodeFromBase64String (Platform::String^)
        // Call using StringReference:
        IBuffer^ buffer = CryptographicBuffer::DecodeFromBase64String(StringReference(s.c_str()));

        //...do something with buffer
    }
}
```
