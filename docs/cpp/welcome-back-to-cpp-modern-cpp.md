---
title: C++'a (Modern C++) Tekrar Hoş Geldiniz
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 1cb1b849-ed9c-4721-a972-fd8f3dab42e2
ms.openlocfilehash: 1f59395001722244cb407ef07ed8a301f08df85b
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73624756"
---
# <a name="welcome-back-to-c-modern-c"></a>C++'a (Modern C++) Tekrar Hoş Geldiniz

C++, dünyanın en yaygın olarak kullanılan programlama dillerinden biridir. İyi yazılmış C++ programlar hızlı ve verimlidir. Dil, eğlenceli ve heyecan verici oyunlardan, cihaz sürücülerine, katıştırılmış programlara ve Windows istemci uygulamalarına kadar çok çeşitli uygulamalar oluşturmak için kullanabileceğiniz diğer dillerden daha esnektir. 20 yıldan C++ daha uzun bir süredir bu ve diğerleri gibi sorunları çözümlemek için kullanılmıştır. Bilmeyebilirsiniz, daha fazla sayıda C++ programcı, Dünün C stili programlamayı dün ve bunun yerine modern C++ bir şekilde katmış.

İçin C++ özgün gereksinimlerinden biri, C diliyle geriye dönük uyumlulukta. Daha sonra, C++ birkaç yineleme (sınıflar ile C), ardından özgün C++ dil belirtimi ve daha sonra yapılan birçok gelişmeye sahip. Bu Mirada, C++ genellikle multi-kip programlama dili olarak adlandırılır. İçinde C++, ham işaretçiler, diziler, null ile sonlandırılmış karakter dizeleri, özel veri yapıları ve ayrıca hata ve karmaşıklık sağlayan diğer özellikleri içeren, tamamen yordamsal bir C stili programlama yapabilirsiniz.  C stili programlama bu gibi perıls içerdiğinden, ' ın temel amaçlarından C++ biri, programları hem tür kullanımı güvenli hem de yazmayı, genişletmeyi ve bakımını daha kolay hale getirmeye yöneliktir. Erken on, C++ nesne odaklı programlama gibi programlama paradigmalarına. Yılların üzerinde özellikler, yüksek düzeyde test edilmiş standart kitaplıklar ve algoritmalarla birlikte dile eklenmiştir. Bu, modern C++ stili mümkün hale getirilen bu eklemelere sahiptir.

Modern C++ vurgular:

- Yığın veya statik genel kapsam yerine yığın tabanlı kapsam.

- Açık tür adları yerine otomatik tür çıkarımı.

- Ham işaretçiler yerine akıllı işaretçiler.

- `std::string` ve `std::wstring` türler (bkz. [\<string >](../standard-library/string.md)) ham `char[]` dizileri yerine.

- Ham diziler veya özel kapsayıcılar yerine `vector`, `list`ve `map` gibi standart kitaplık kapsayıcıları. [ C++ ](../standard-library/cpp-standard-library-header-files.md) Bkz. [\<vektör >](../standard-library/vector.md), [\<list >](../standard-library/list.md)ve [\<Map >](../standard-library/map.md).

- C++El ile kodlanması yerine standart kitaplık [algoritmaları](../standard-library/algorithm.md) .

- Hata koşullarını bildirmek ve işlemek için özel durumlar.

- Standart Kitaplık `std::atomic<>` (bkz. C++ [\<atomik >](../standard-library/atomic.md)) kullanarak, diğer iş parçacıkları arası iletişim mekanizmaları yerine, kilit zincirsiz iş parçacıkları arası iletişim.

- Küçük işlevler yerine satır içi [Lambda işlevleri](../cpp/lambda-expressions-in-cpp.md) ayrı olarak uygulanır.

- Aralık tabanlı, diziler, C++ standart kitaplık kapsayıcıları ve form `for ( for-range-declaration : expression )`Windows çalışma zamanı koleksiyonlarıyla çalışan daha güçlü döngüler yazmak için döngülere dayalıdır. Bu, çekirdek dil desteğinin bir parçasıdır. Daha fazla bilgi için bkz. [Aralık tabanlı for deyimleri (C++)](../cpp/range-based-for-statement-cpp.md).

C++ Dilin kendisi de geliştirilmiştir. Aşağıdaki kod parçacıklarını karşılaştırın. Bu, şu şekilde C++kullanılan şeyleri gösterir:

```cpp
#include <vector>

void f()
{
    // Assume circle and shape are user-defined types
    circle* p = new circle( 42 );
    vector<shape*> v = load_shapes();

    for( vector<circle*>::iterator i = v.begin(); i != v.end(); ++i ) {
        if( *i && **i == *p )
            cout << **i << " is a match\n";
    }

    // CAUTION: If v's pointers own the objects, then you
    // must delete them all before v goes out of scope.
    // If v's pointers do not own the objects, and you delete
    // them here, any code that tries to dereference copies
    // of the pointers will cause null pointer exceptions.
    for( vector<circle*>::iterator i = v.begin();
            i != v.end(); ++i ) {
        delete *i; // not exception safe
    }

    // Don't forget to delete this, too.
    delete p;
} // end f()
```

Modern C++' de aynı şey nasıl gerçekleştirilir:

```cpp
#include <memory>
#include <vector>

void f()
{
    // ...
    auto p = make_shared<circle>( 42 );
    vector<shared_ptr<shape>> v = load_shapes();

    for( auto& s : v )
    {
        if( s && *s == *p )
        {
            cout << *s << " is a match\n";
        }
    }
}
```

Modern C++bir sürümünde, bunun yerine akıllı işaretçiler kullanabileceğiniz yeni/Delete ya da açık özel durum işleme kullanmanız gerekmez. **Otomatik** tür kesintisi ve [Lambda işlevini](../cpp/lambda-expressions-in-cpp.md)kullandığınızda, daha hızlı kod yazabilir, onu açabilir ve daha iyi anlayabilirsiniz. Ve Aralık tabanlı bir **for** döngüsü temizleyici, kullanımı kolay ve bir for döngüsü **için** C stili olmayan istenmeden hatalara karşı daha az yol açmaya yöneliktir. Uygulamanızı yazmak için en az kod satırı ile ortak bir şekilde birlikte kullanabilirsiniz. Bu kod özel durum güvenli ve bellek açısından güvenli hale getirebilirsiniz ve ile başa çıkmak/ayırmayı kaldırma ya da hata kodu yoktur.

Modern C++ iki tür çok biçimlilik içerir: derleme zamanı, şablonlar ve çalışma zamanı, devralma ve sanallaştırma aracılığıyla. İki tür biçimliliği harika bir etkiye karıştırabilirsiniz. Standart C++ kitaplık `shared_ptr` şablonu, Görünüşe göre daha seyrek bir tür elde etmek için iç sanal yöntemleri kullanır. Ancak, bir şablon daha iyi bir seçenek olduğunda çok biçimlilik için sanallaştırmayı kullanmayın. Şablonlar çok güçlü olabilir.

Başka bir dilden geliyorsa C++ , özellikle türlerin çoğunun başvuru türleri olduğu ve çok az sayıda değer türü olduğu yönetilen bir dilden, sınıfların varsayılan olarak değer türleri olduğunu unutmayın. C++ Ancak, nesne odaklı programlamayı destekleyen polimorfik davranışı etkinleştirmek için bunları başvuru türleri olarak belirtebilirsiniz. Faydalı perspektif: değer türleri bellek ve düzen denetimi hakkında daha fazla bilgi için başvuru türleri temel sınıflar ve sanal işlevler hakkında çok biçimlilik desteği sağlar. Varsayılan olarak, değer türleri kopyalanabilir — her birinin bir kopya Oluşturucusu ve bir kopya atama işleci vardır. Bir başvuru türü belirttiğinizde, sınıfı kopyalanabilir dışı yapın — kopya oluşturucuyu ve kopya atamasını devre dışı bırakın — ve çok biçimliliği destekleyen bir sanal yıkıcı kullanın. Değer türleri aynı zamanda, kopyalandığı içerik hakkında, ayrı olarak değiştirebileceğiniz iki bağımsız değer sağlar. Ancak başvuru türleri kimlik ve ne tür bir nesne olduğunu — bu nedenle bazen çok biçimli türler olarak adlandırılır.

C++güç bir Renaissance yaşıyor. Java gibi diller ve C# programcı üretkenliği önemli olduğunda iyi, ancak güç ve performans paralandıklarında bunların sınırlamalarını gösterir. Özellikle sınırlı donanıma sahip cihazlarda yüksek verimlilik ve güç için, modern C++hiçbir şey olmaz.

Yalnızca dil modern değildir, geliştirme araçları da çok önemlidir. Visual Studio, geliştirme döngüsünün tüm parçalarını sağlam ve verimli hale getirir. Uygulama yaşam döngüsü yönetimi (ALM) araçlarını, IntelliSense gibi IDE geliştirmelerini, XAML gibi araç kullanımı kolay mekanizmalarını, oluşturma, hata ayıklamayı ve diğer birçok aracı içerir.

Belgelerinin bu bölümündeki makaleler, modern C++ programlar yazmak için en önemli özellikler ve teknikler için üst düzey yönergeler ve en iyi uygulamalar sağlar.

- [C++Tür sistemi](../cpp/cpp-type-system-modern-cpp.md)

- [Tek Düzen Başlatma ve Oluşturucuları Temsilci Olarak Görevlendirme](../cpp/uniform-initialization-and-delegating-constructors.md)

- [Nesne ömrü ve kaynak yönetimi](../cpp/object-lifetime-and-resource-management-modern-cpp.md)

- [Nesnelerin Kaynakları (RAII)](../cpp/objects-own-resources-raii.md)

- [Akıllı Işaretçiler](../cpp/smart-pointers-modern-cpp.md)

- [Derleme zamanı Kapsüllemesi Için pımpl](../cpp/pimpl-for-compile-time-encapsulation-modern-cpp.md)

- [Kapsayıcılar](../cpp/containers-modern-cpp.md)

- [Algoritmalar](../cpp/algorithms-modern-cpp.md)

- [Dize ve g/ç biçimlendirme (modern C++)](../cpp/string-and-i-o-formatting-modern-cpp.md)

- [Hatalar ve özel durum Işleme](../cpp/errors-and-exception-handling-modern-cpp.md)

- [ABı sınırlarındaki taşınabilirlik](../cpp/portability-at-abi-boundaries-modern-cpp.md)

Daha fazla bilgi için, [c++ 11 ' de C++ ıoms 'nin kullanım dışı olduğunu](https://stackoverflow.com/questions/9299101/which-c-idioms-are-deprecated-in-c11)Stack Overflow makalesine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[Lambda İfadeleri](../cpp/lambda-expressions-in-cpp.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)<br/>
[Microsoft C++ dil uygunluk tablosu](../overview/visual-cpp-language-conformance.md)