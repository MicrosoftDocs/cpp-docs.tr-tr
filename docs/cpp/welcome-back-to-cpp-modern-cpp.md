---
title: C++'a (Modern C++) Tekrar Hoş Geldiniz
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 1cb1b849-ed9c-4721-a972-fd8f3dab42e2
ms.openlocfilehash: 5b2868d20c047eef7762256ff8c9bf43de7a0de0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209534"
---
# <a name="welcome-back-to-c-modern-c"></a>C++'a (Modern C++) Tekrar Hoş Geldiniz

C++ dünyada en yaygın olarak kullanılan programlama dilleri biridir. İyi yazılmış C++ programları hızlı ve verimlidir. Çok çeşitli uygulamalar oluşturmak için kullanın dil diğer dillerden daha esnektir çünkü — eğlenceli ve heyecan verici oyunlardan yüksek performanslı bilimsel yazılımlara, cihaz sürücüleri, katıştırılmış programlara ve Windows istemci uygulamaları için. 20 yıldan fazla, C++ ve diğer birçok gibi sorunları çözmek için kullanıldı. Değil bilmeniz, artan sayıda C++ programcıları dün belki C stili programlamada yukarı Katlanmış ve modern C++ yerine donned olmasıdır.

C++ için orijinal gereksinimlerden C diliyle geriye dönük uyumluluk biriydi. O zamandan bu yana, C++ birkaç yineleme boyunca gelişmiştir — sınıflar, ardından orijinal C++ dil belirtimi ve sonra çok sayıda alt geliştirme ile C. Bu kalıtım nedeniyle, C++ genellikle bir çoklu paradigma programlama dili adlandırılır. C++'da, ham işaretçileri, dizileri, null ile sonlandırılmış dizeleri, özel veri yapıları ve harika performans sağlayan ancak aynı zamanda hataları ve karmaşıklık düzeyini artırabilen diğer özellikleri içeren tam olarak yordama dayalı C stili programlama yapabilirsiniz.  C stili programlamada amaçlardan kaybolduğu olduğundan, kuruluş hedeflerinden c++ programları hem tür kullanımı uyumlu hem de yazma, genişletmeyi ve sürdürmeyi daha kolay hale getirmektir. İlk C++ nesne yönelimli programlama gibi programlama paradigmalarını benimsemekteydi. Yıllar içinde dile, yüksek oranda test edilen standart kitaplıkları veri yapıları ve algoritmaları ile birlikte özellik eklenmiştir. Modern C++ stilinin olası yapmış olduğunuz bu eklemelerdir.

Modern C++ şunları vurgular:

- Yığın veya statik genel kapsam yerine yığın tabanlı kapsam.

- Açık tür adları yerine otomatik tür çıkarımı.

- Ham işaretçiler yerine akıllı işaretçiler.

- `std::string` ve `std::wstring` türleri (bkz [ \<dizesi >](../standard-library/string.md)) ham yerine `char[]` dizileri.

- [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-header-files.md) kapsayıcıları ister `vector`, `list`, ve `map` ham diziler veya özel kapsayıcılar yerine. Bkz: [ \<vektör >](../standard-library/vector.md), [ \<listesi >](../standard-library/list.md), ve [ \<harita >](../standard-library/map.md).

- C++ Standart Kitaplığı [algoritmaları](../standard-library/algorithm.md) el ile kodlanmışlar yerine.

- Özel durumlar, hata koşullarını raporlamak ve işlemek için.

- Kilit içermeyen C++ Standart Kitaplığı kullanarak iş parçacıkları arası iletişim `std::atomic<>` (bkz [ \<atomik >](../standard-library/atomic.md)) diğer iş parçacıkları arası iletişim mekanizmaları yerine.

- Satır içi [lambda işlevleri](../cpp/lambda-expressions-in-cpp.md) küçük işlevlerin ayrı ayrı uygulanması yerine.

- Aralık tabanlı for biçiminde koleksiyonları diziler, C++ Standart Kitaplığı kapsayıcıları ve Windows çalışma zamanı ile çalışan daha güçlü döngüler yazılmasını `for ( for-range-declaration : expression )`. Bu çekirdek dil desteğinin bir parçasıdır. Daha fazla bilgi için [aralık tabanlı for deyimi (C++)](../cpp/range-based-for-statement-cpp.md).

C++ dili de gelişmiştir. Aşağıdaki kod parçacıklarını karşılaştırın. Bu, c++'ta olması için öğeleri nasıl kullanılacağını gösterir:

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

Modern C++'da aynı şeyi nasıl gerçekleştirilir aşağıda verilmiştir:

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

Modern C++ programlamada, new/delete veya explicit özel durum bunun yerine akıllı işaretçiler kullanabileceğinizden işlemelerini kullanmak zorunda değilsiniz. Kullanırken **otomatik** ifadeden tür çıkarma ve [lambda işlevi](../cpp/lambda-expressions-in-cpp.md), daha hızlı kod yazabileceğiniz, kısaltabilir ve daha iyi anlayabilirsiniz. Hem de aralık tabanlı **için** döngü daha net, daha kolay ve hata potansiyeli daha az istenmeyen C stili daha **için** döngü. Uygulamanızı yazmak için Demirbaş ve birkaç satır kod kullanabilirsiniz. Ve kod özel durum açısından güvenli ve bellek-güvenli hale getirmek ve uğraşmanız hiçbir ayırma uğraşmazsınız veya hata kodlarıyla.

Modern C++ iki türde çok biçimlilik içerir: Şablonlar aracılığıyla derleme zamanı ve devralma ve sanallaştırmayla çalışma zamanı. Çok biçimlilik harika etkili olması için iki tür karıştırabilirsiniz. C++ Standart kitaplığı şablonu `shared_ptr` kendi görünüşe göre kolay tür silme işlemini gerçekleştirmek için iç sanal yöntemler kullanır. Ancak, bir şablon daha iyi bir seçimdir, sanallaştırmayı çok biçimlilik için aşırı kullanmayın. Şablonlar çok güçlü olabilir.

Başka bir dil içindeki türlerin çoğu başvuru türleridir ve çok az sayıda değer türü olduğu özellikle yönetilen bir dil için C++ geldiği varsa C++ sınıflarının varsayılan değer türleri olduğunu bilirsiniz. Ancak, nesne odaklı programlamayı destekleyen çok biçimli davranışları etkinleştirmek için başvuru türleri olarak belirtebilirsiniz. Yararlı bir perspektif: değer türleri olan temel sınıflar ve çok biçimlilik destekleyen sanal işlevleri hakkında daha fazla bellek ve düzen denetimi, başvuru türleri hakkında daha fazla. Varsayılan olarak, değer türleri kopyalanabilirdir — her bir kopya oluşturucu ve kopya atama işlecine sahip. Bir başvuru türü belirttiğinizde, sınıfı kopyalanamaz yapın — kopya oluşturucu ve kopya atama işleci devre dışı — ve çok biçimlilik destekleyen sanal bir yıkıcı kullanın. Değer Ayrıca bunlar kopyalandığında, ayrı ayrı değiştirebileceğiniz iki bağımsız değer erişmenizi sağlayan içeriği hakkında türleridir. Ancak başvuru türleri hakkında daha fazla kimlik — ne tür bir nesne olduğuyla — ve bu nedenle çok biçimli türler olarak adlandırılır.

Güç yeniden revaçta olduğundan, C++ bir Rönesans devri yaşıyor. Java ve C# gibi diller Programcı verimliliğinin önemli olduğu, ancak güç ve performans en önemli olduğunda bazı sınırlamalara gösterdikleri iyidir. Yüksek verimlilik ve güç, özellikle sınırlı donanımı olan cihazlarda için hiçbir şey modern C++ programlamadan daha iyi değildir.

Yalnızca dil, geliştirme araçları da moderndir. Visual Studio geliştirme döngüsünün tüm bölümlerini sağlam ve verimli hale getirir. Uygulama Yaşam Döngüsü Yönetimi (ALM) araçları, IntelliSense gibi IDE geliştirmelerini, XAML ve hata ayıklama, oluşturma, gibi araç dostu mekanizmaları içerdiğinden ve birçok diğer aracı.

Belgelerin bu bölümündeki makaleler, üst düzey yönergeler ve en önemli özellikleri için en iyi uygulamalar ve modern C++ programları yazmak için teknikleri sağlar.

- [C++ tür sistemi](../cpp/cpp-type-system-modern-cpp.md)

- [Tek Düzen Başlatma ve Oluşturucuları Temsilci Olarak Görevlendirme](../cpp/uniform-initialization-and-delegating-constructors.md)

- [Nesne yaşam süresi ve kaynak yönetimi](../cpp/object-lifetime-and-resource-management-modern-cpp.md)

- [Nesnelerin Kaynakları (RAII)](../cpp/objects-own-resources-raii.md)

- [Smart Pointers](../cpp/smart-pointers-modern-cpp.md)

- [Derleme zamanı kapsüllemesi için Pimpl](../cpp/pimpl-for-compile-time-encapsulation-modern-cpp.md)

- [Kapsayıcılar](../cpp/containers-modern-cpp.md)

- [Algoritmalar](../cpp/algorithms-modern-cpp.md)

- [Dize ve g/ç biçimlendirme (Modern C++)](../cpp/string-and-i-o-formatting-modern-cpp.md)

- [Hatalar ve özel durum işleme](../cpp/errors-and-exception-handling-modern-cpp.md)

- [ABI sınırlarında taşınabilirlik](../cpp/portability-at-abi-boundaries-modern-cpp.md)

Daha fazla bilgi için Stack Overflow bkz [C ++ 11'de, C++ deyimleri kullanım dışı](https://stackoverflow.com/questions/9299101/which-c-idioms-are-deprecated-in-c11).

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[Lambda İfadeleri](../cpp/lambda-expressions-in-cpp.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)<br/>
[Visual C++ dil uyumluluğu](../overview/visual-cpp-language-conformance.md)