---
title: Dizeler (C + +/ CX)
ms.date: 01/22/2017
ms.assetid: 5b34e1df-7c2b-4269-aba8-b767d36c49d9
ms.openlocfilehash: 350c6133b9f910a067f760681832b81bac24f4e7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50556461"
---
# <a name="strings-ccx"></a>Dizeler (C + +/ CX)

Windows çalışma zamanı içinde metin temsil C + +/ CX tarafından [Platform::String sınıfı](../cppcx/platform-string-class.md). Kullanım `Platform::String Class` dizeleri ve geriye Windows çalışma zamanı sınıflar yöntemlere geçirdiğinizde veya uygulama ikili arabiriminde (ABI) sınırında diğer Windows çalışma zamanı bileşenleri ile etkileşim kurarken. `Platform::String Class` Dize tam özellikli bir sınıf olması için tasarlanmamış birkaç yaygın dize işlemleri ancak onun için yöntemler sağlar. C++ modülünüzde standart C++ dize türleri gibi kullanın [wstring](../standard-library/basic-string-class.md) tüm önemli metin işleme ve son sonucu için sonra dönüştürme [Platform::String ^](../cppcx/platform-string-class.md) için veya genel geçirmeden önce arabirim. Kolay ve verimli arasında dönüştürmek için `wstring` veya `wchar_t*` ve `Platform::String`.

**Hızlı geçiş**

Bazı durumlarda, derleyicinin güvenli bir şekilde gerçekleştirebilmesi doğrulayabilirsiniz bir `Platform::String` veya bir `String` temel alınan dize verileri kopyalama olmadan bir işlev. Bu işlemler olarak bilinen *hızlı geçişi* ve şeffaf bir şekilde gerçekleşir.

## <a name="string-construction"></a>Dize oluşturma

Değerini bir `String` nesnesi olan bir sabit (salt okunur) dizisi `char16` (16-bit Unicode) karakter. Çünkü bir `String` nesnedir değişmezse, yeni bir dize sabit atama bir `String` değişkeni aslında özgün değiştirir `String` yeni bir nesne `String` nesne. Birleştirme işlemleri içeren özgün yok edilmesini `String` nesne ve yeni bir nesne oluşturma.

**Değişmez Değerler**

A *değişmez değer* tek tırnak işaretleri içine alınmış bir karakterse ve *değişmez değer dize* , çift tırnak içine alınmış bir karakter dizisidir. Bir dizeyi başlatmak için bir sabit değer kullanırsanız ^ değişken, derleyici değişmez değer oluşturan varsayar `char16` karakter. Diğer bir deyişle, değişmez değer dize 'L' değiştiricisi önünde veya sabit listesinde değişmez içine yoksa bir **_T()** veya **TEXT()** makrosu. Unicode için C++ desteği hakkında daha fazla bilgi için bkz. [Unicode Programlama Özeti](../text/unicode-programming-summary.md).

Aşağıdaki örnek oluşturmak için çeşitli yollar gösterir `String` nesneleri.

[!code-cpp[cx_strings#01](../cppcx/codesnippet/CPP/cppcx_strings/class1.cpp#01)]

## <a name="string-handling-operations"></a>Dize işlemleri işleme

`String` SAX yöntemleri ve işleçleri bitiştirmek için dizeleri ve diğer temel dize işlemleri karşılaştırma. Daha geniş dize işlemeleri gerçekleştirme kullanın `String::Data()` değerini almak için üye işlevi `String^` nesnesinin bir `const wchar_t*`. Ardından başlatmak için bu değeri kullanan bir `std::wstring`, işleme işlevleri zengin dize sağlar.

[!code-cpp[cx_strings#03](../cppcx/codesnippet/CPP/cppcx_strings/class1.cpp#03)]

## <a name="string-conversions"></a>Dize dönüştürme

A `Platform::String` yalnızca içerebilir `char16` karakter veya `NULL` karakter. 8 bitlik karakterleri ile çalışmak uygulamanızı olması durumunda kullanmanız [String::Data](../cppcx/platform-string-class.md#data) olarak ayıklamak için bir `const wchar_t*`. Daha sonra uygun Windows işlevleri kullanabilirsiniz veya veriler üzerinde çalışır ve dönüştürmek için standart kitaplık işlevlerini yeniden bir `wchar_t*` veya [wstring](../standard-library/basic-string-class.md), yeni bir oluşturmak için kullanabileceğiniz `Platform::String`.

Aşağıdaki kod parçası nasıl dönüştürüleceğini gösterir bir `String^` ve değişken bir `wstring` değişkeni. Bu örnekte kullanılan dize düzenleme hakkında daha fazla bilgi için bkz. [basic_string::replace](../standard-library/basic-string-class.md#replace).

[!code-cpp[cx_strings#04](../cppcx/codesnippet/CPP/cppcx_strings/class1.cpp#04)]

## <a name="string-length-and-embedded-null-values"></a>Dize uzunluğu ve katıştırılmış NULL değerler

[String::Length](../cppcx/platform-string-class.md#length) bayt sayısını değil gibi dize karakter sayısını döndürür. Bir dizeyi oluşturmak için yığın anlamları kullandığınızda, onu açıkça belirtmediğiniz sürece sondaki NULL karakter sayılmaz.

A `Platform::String` ancak yalnızca bir birleştirme işleminin bir sonucu NULL olduğunda, gömülü NULL değerler içerebilir. Gömülü null dize değişmez değerlerine desteklenmez; gömülü null değerlere bu şekilde başlatmak için bu nedenle, kullanamazsınız bir `Platform::String`. NULL değerler katıştırılmış bir `Platform::String` için atandığında dize, örneğin, görüntülendiğinde göz ardı edilir bir `TextBlock::Text` özelliği. Gömülü null dize değeri döndürdüğünde kaldırılır `Data` özelliği.

## <a name="stringreference"></a>StringReference

Bazı durumlarda, std::wstring veya wchar_t dize veya L (a), kodunuzu alır"" dize sabit değeri ve yalnızca geçirir, bir dize alan başka bir yöntem ^ giriş parametresi olarak. Özgün dize arabelleğin kendisini geçerli kalır ve işlev dönüşleri önce değiştirmediğini sürece dönüştürebilirsiniz `wchar_t*` dize veya dize sabit değeri için bir [Platform::StringReference](../cppcx/platform-stringreference-class.md)ve, bir yerinegeçme`Platform::String^`. Bu olduğundan izin `StringReference` sahip kullanıcı tanımlı dönüştürme `Platform::String^`. Kullanarak `StringReference` dize verileri ek kopyalayarak önleyebilirsiniz. Burada, kaçı çok sayıda dize veya çok büyük dizelerin geçerken Döngülerde, potansiyel olarak önemli bir performans geliştirmesi kullanarak elde edebileceğiniz `StringReference`. Ancak `StringReference` aslında özgün dize arabelleğindeki çözümümüz bellek bozulmasını önlemek için son derece dikkatli olunmalıdır kullanmanız gerekir. Değil geçmelidir bir `StringReference` Zamanuyumsuz bir yönteme sürece özgün dizeye bu yöntem döndürüldüğünde, kapsam içinde olması sağlanır. Bir String ^ dan başlatılan bir ikinci atama işlemi oluşursa bir StringReference bir ayırma ve dize veri kopyası zorlar. Bu durumda, performans avantajlarını kaybedersiniz `StringReference`.

Unutmayın `StringReference` standart bir C++ sınıf türü başvuru sınıfı değil, tanımladığınız başvuru sınıfları ortak arabiriminde kullanamazsınız.

Aşağıdaki örnek, StringReference kullanma işlemini gösterir:

```
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

