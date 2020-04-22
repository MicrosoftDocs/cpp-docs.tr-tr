---
title: Dizeler (C++/CX)
ms.date: 01/22/2017
ms.assetid: 5b34e1df-7c2b-4269-aba8-b767d36c49d9
ms.openlocfilehash: a67b9a4552dc83791c05029cca76f60fd83df0f1
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745356"
---
# <a name="strings-ccx"></a>Dizeler (C++/CX)

Windows Runtime'daki metin C++/CX'te [Platform:String Class](../cppcx/platform-string-class.md)ile temsil edilir. `Platform::String Class` Dizeleri Windows Runtime sınıflarında yöntemlere ileri geri aktarırken veya uygulama ikili arabirimi (ABI) sınırındaki diğer Windows Runtime bileşenleriyle etkileşimde bulunurken kullanın. Birkaç `Platform::String Class` yaygın dize işlemleri için yöntemler sağlar, ancak tam özellikli dize sınıfı olarak tasarlanmaz. C++ modülünüzde, önemli bir metin işleme için [wstring](../standard-library/basic-string-class.md) gibi standart C++ dize türlerini kullanın ve genel arabirime geçmeden önce nihai sonucu [Platform::String^](../cppcx/platform-string-class.md) olarak dönüştürün. Bu arasında `wstring` dönüştürmek için kolay `wchar_t*` ve `Platform::String`verimli ya da .

**Hızlı geçiş**

Bazı durumlarda, derleyici, temel dize verilerini `Platform::String` kopyalamadan `String` güvenli bir şekilde bir işlev oluşturabileceğini veya bir işleve geçebileceğini doğrulayabilir. Bu tür işlemler *hızlı geçiş* olarak bilinir ve saydam olarak gerçekleşir.

## <a name="string-construction"></a>Dize yapısı

Bir `String` nesnenin değeri( 16 bit Unicode) `char16` karakterden oluşan değişmez (salt okunur) bir dizidir. Bir `String` nesne değişmez olduğundan, yeni bir dize gerçek `String` bir değişkene `String` atanması aslında `String` özgün nesnenin yerine yeni bir nesne alır. Concatenation işlemleri özgün `String` nesnenin imha ve yeni bir nesnenin oluşturulması nı içerir.

**Sabit değerler**

*Gerçek karakter,* tek tırnak işaretleriyle çevrili bir karakterdir ve *edebi dize* çift tırnak işaretleriyle ekilen bir karakter dizisidir. String^ değişkenini initialiseleştirmek için bir literal kullanırsanız, derleyici, `char16` literal'ın karakterlerden oluştuğunu varsayar. Diğer bir deyişle, 'L' dize değiştirici ile literal önce veya **bir _T()** veya **TEXT()** makro içinde literal içine almak zorunda değilsiniz. Unicode için C++ desteği hakkında daha fazla bilgi için [Unicode Programlama Özeti'ne](../text/unicode-programming-summary.md)bakın.

Aşağıdaki örnek, nesneleri oluşturmak `String` için çeşitli yollar gösterir.

[!code-cpp[cx_strings#01](../cppcx/codesnippet/CPP/cppcx_strings/class1.cpp#01)]

## <a name="string-handling-operations"></a>Dize işleme işlemleri

Sınıf, `String` dizeleri ve diğer temel dize işlemleri karşılaştırma, koncatenating yöntemleri ve işleçleri sağlar. Daha kapsamlı dize manipülasyonları `String::Data()` gerçekleştirmek için, `String^` nesnenin değerini almak `const wchar_t*`için üye işlevi kullanın. Daha sonra zengin dize `std::wstring`işleme işlevleri sağlayan bir , baş harflerini almak için bu değeri kullanın.

[!code-cpp[cx_strings#03](../cppcx/codesnippet/CPP/cppcx_strings/class1.cpp#03)]

## <a name="string-conversions"></a>Dize dönüşümleri

A `Platform::String` yalnızca `char16` karakterleri veya `NULL` karakteri içerebilir. Uygulamanızın 8 bit karakterlerle çalışması gerekiyorsa, metni bir `const wchar_t*`' olarak ayıklamak için [String::Data'yı](../cppcx/platform-string-class.md#data) kullanın. Daha sonra veri üzerinde çalışmak ve yeni `wchar_t*` `Platform::String`bir oluşturmak için kullanabileceğiniz bir veya [wstring](../standard-library/basic-string-class.md), geri dönüştürmek için uygun Windows işlevleri veya Standart Kitaplık işlevleri kullanabilirsiniz .

Aşağıdaki kod parçası, bir `String^` değişkenin bir `wstring` değişkene nasıl dönüştürüldüğünü gösterir. Bu örnekte kullanılan dize işleme hakkında daha fazla bilgi için [basic_string bkz.](../standard-library/basic-string-class.md#replace)

[!code-cpp[cx_strings#04](../cppcx/codesnippet/CPP/cppcx_strings/class1.cpp#04)]

## <a name="string-length-and-embedded-null-values"></a>Dize uzunluğu ve gömülü NULL değerleri

[String::Uzunluk,](../cppcx/platform-string-class.md#length) bayt sayısını değil, dizedeki karakter sayısını döndürür. Bir dize oluşturmak için yığın semantiklerini kullandığınızda açıkça belirtmediğiniz sürece sonlandırıcı NULL karakteri sayılmaz.

A `Platform::String` katıştırılmış NULL değerlerini içerebilir, ancak yalnızca NULL bir bir birlikteleştirme işleminin sonucu olduğunda. Katıştılı NULL'ler dize gerçeklerinde desteklenmez; bu nedenle, gömülü NULL'leri bu şekilde `Platform::String`kullanarak bir . Bir özellik atandığında dize görüntülendiğinde, örneğin, bir `Platform::String` `TextBlock::Text` özellik için atandığında gömülü NULL değerleri yoksayılır. Dize değeri `Data` özellik tarafından döndürüldüğünde katıştırılmış NULL'ler kaldırılır.

## <a name="stringreference"></a>StringReference

Bazı durumlarda kodunuz (a) std alır::wstring veya wchar_t dize veya L"" dize literal ve sadece giriş parametresi olarak bir String^ alır başka bir yöntem üzerine geçer. Özgün dize arabelleği geçerli kaldığı ve işlev dönmeden önce mutasyona uğramadığı `wchar_t*` sürece, dize veya dizeyi bir [Platforma dönüştürebilirsiniz::StringReference](../cppcx/platform-stringreference-class.md), ve bir `Platform::String^`. Kullanıcı tanımlı `StringReference` bir dönüştürme olduğu `Platform::String^`için buna izin verilir. Kullanarak `StringReference` dize verilerinin ekstra bir kopyasını yapmaktan kaçınabilirsiniz. Çok sayıda dize geçtiğiniz döngülerde veya çok büyük dizeleri geçerken, potansiyel olarak kullanarak `StringReference`önemli bir performans artışı elde edebilirsiniz. Ancak `StringReference` özgün dize arabelleği ödünç aldığı için, bellek bozulmasını önlemek için aşırı özen kullanmanız gerekir. Özgün dize, `StringReference` yöntem döndürdüğünde kapsamda olacağı garanti edilmedikçe, bir eşzamanlı yönteme geçmemelisiniz. StringReference'dan başlatılan string^ ikinci bir atama işlemi gerçekleşirse, dize verilerinin bir ayırmasını ve kopyasını zorlar. Bu durumda, performans avantajı `StringReference`kaybedersiniz.

Standart `StringReference` bir C++ sınıfı türü olduğunu, ref sınıfı olmadığını unutmayın, bunu tanımladığınız ref sınıflarının ortak arabiriminde kullanamazsınız.

Aşağıdaki örnek, StringReference'ın nasıl kullanılacağını gösterir:

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
