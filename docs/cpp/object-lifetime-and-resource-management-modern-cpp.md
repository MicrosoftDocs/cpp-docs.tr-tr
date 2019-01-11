---
title: Nesne Yaşam Süresi ve Kaynak Yönetimi (Modern C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 8aa0e1a1-e04d-46b1-acca-1d548490700f
ms.openlocfilehash: 5964078960a5b241cb5af369aeddba45a06e48ad
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220640"
---
# <a name="object-lifetime-and-resource-management-modern-c"></a>Nesne Yaşam Süresi ve Kaynak Yönetimi (Modern C++)

Yönetilen dillerden farklı olarak, C++, bir program çalışırken, otomatik olarak bellek yok-uzun-kullanılan kaynakları serbest bırakır, çöp toplama (GC) sahip değil. C++'da, kaynak yönetimi için nesne ömrü doğrudan ilgilidir. Bu belgede, c++ nesne yaşam süresi ve bunları yönetme etkileyen faktörler açıklanmaktadır.

Bellek içi kaynaklar öncelikli olarak işlemiyor için C++ GC sahip. Yalnızca c++ gelenler belirleyici yok ediciler, bellek ve bellek içi kaynaklarını eşit olarak işleyebilir. GC, bellek ve CPU tüketimi ve Yerleşim Yeri yükü daha fazladır gibi diğer sorunlara da vardır. Ancak universality akıllı iyileştirmeler sayesinde azaltılamaz temel bir sorundur.

## <a name="concepts"></a>Kavramlar

Nesne ömrü Yönetimi önemli bir şeyi kapsülleme olan — kişi bir nesne kullanıyor ne nesne kaynakları sahibi, veya bunları kurtulmak nasıl veya hatta olup herhangi bir kaynağa hiç sahibi bilmeniz gerekmez. Nesneyi yok etmek yalnızca sahiptir. C++ çekirdek dil nesneler doğru zamanlarda, diğer bir deyişle, yok emin olmak için tasarlanan blokları, ters sırada yapımı çıkıldı gibi. Bir nesne kaldırıldığında, bu belirli bir sırada kendi tabanları ve üyeleri yok edilir.  Yığın ayırma ya da yeni yerleştirme gibi özel şeyler sürece dil nesneleri otomatik olarak yok eder.  Örneğin, [akıllı işaretçileri](../cpp/smart-pointers-modern-cpp.md) gibi `unique_ptr` ve `shared_ptr`, ve C++ Standart Kitaplığı kapsayıcıları `vector`, kapsülleyen **yeni** /  **silme** ve `new[]` / `delete[]` nesnelerde, Yıkıcılar sahip. İşte bu akıllı işaretçiler ve C++ Standart Kitaplığı kapsayıcıları kullanmak bu kadar önemlidir.

Başka bir önemli kavramı ömrü Yönetimi: yıkıcı. Yıkıcılar, kaynak sürüm kapsüller.  (Kullanılan anımsatıcı RRID, kaynak sürüm olan yok etme içindir.)  Bir kaynak "" sistemden ve daha sonra tekrar sağlamak zorunda değildir.  Bellek en yaygın bir kaynaktır girmeyecek olsak da dosyaları, yuva, dokuları ve diğer bellek içi kaynaklar. "Bir kaynağa sahip olan", ihtiyaç duyduğunuz ancak onunla tamamladığınızda serbest bırakmak de kullanabileceğiniz anlamına gelir.  Bir nesne kaldırıldığında, bu yok edici bu ait kaynakları serbest bırakır.

Son (yönlendirilmiş Çevrimsiz graf) DAG kavramdır.  Bir DAG sahipliği programında yapısını oluşturur. Hiçbir nesne kendisine sahip olabilir; bu değil yalnızca imkansız ancak aynı zamanda kendiliğinden anlamsız. Ancak, iki nesne üçüncü nesne sahipliğini paylaşabilirsiniz.  Böyle bir DAG içindeki bağlantılar çeşitli türlerde desteklenir: A B üyesidir (B sahibi A) C depoları bir `vector<D>` (C D her öğenin sahibi), E depoları bir `shared_ptr<F>` (E paylaşır sahipliğini F, büyük olasılıkla diğer nesnelerle), ve benzeri.  Hiçbir döngü vardır ve her bir bağlantının DAG içindeki bir nesne tarafından temsil edilen sürece (yerine, bir ham işaretçi, tanıtıcı veya başka bir mekanizma) bir yok Edicisi olan ve ardından bunları dil önlediği için kaynak sızıntılarını mümkün. Hemen bunlar artık, çalışan bir çöp toplayıcı ihtiyaç duyulan sonra kaynakları serbest bırakılır. Yığın kapsamı, tabanları, üyeleri ve ilgili örnekler için ek yükü ücretsiz ve hesaplı için izleme ömrü `shared_ptr`.

### <a name="heap-based-lifetime"></a>Yığın temelli ömrü

Yığın nesnesi ömrü boyunca kullanın [akıllı işaretçileri](../cpp/smart-pointers-modern-cpp.md). Kullanım `shared_ptr` ve `make_shared` varsayılan işaretçi ve ayırıcı olarak. Kullanım `weak_ptr` döngüleri kesme, önbelleğe alma yapmak ve nesneleri etkileyen veya yaşam ilgili hiçbir şeyi varsayılarak olmadan gözlemleyin.

```cpp
void func() {

auto p = make_shared<widget>(); // no leak, and exception safe
...
p->draw();

} // no delete required, out-of-scope triggers smart pointer destructor
```

Kullanım `unique_ptr` benzersiz sahipliği için örneğin *derleme pimpl* deyimidir. (Bkz [derleme zamanı kapsüllemesi için Pimpl](../cpp/pimpl-for-compile-time-encapsulation-modern-cpp.md).) Olun bir `unique_ptr` tüm açık birincil hedefinin **yeni** ifadeler.

```cpp
unique_ptr<widget> p(new widget());
```

Ham işaretçilerin sahiplik olmayan ve gözlem için kullanabilirsiniz. Sahip olmayan bir işaretçi dangle, ancak sızıntı olamaz.

```cpp
class node {
  ...
  vector<unique_ptr<node>> children; // node owns children
  node* parent; // node observes parent, which is not a concern
  ...
};
node::node() : parent(...) { children.emplace_back(new node(...) ); }
```

Performans iyileştirmesi gerektiğinde kullanmanız gerekebilir *iyi kapsüllenmiş* işaretçiler ve silmek için açık çağrılar sahip. Kendi alt düzey veri yapısı uygularken bir örnektir.

### <a name="stack-based-lifetime"></a>Yığın tabanlı ömrü

Modern C++ ' ta *yığın tabanlı kapsam* otomatik olarak birleştirir çünkü sağlam kod yazmak için güçlü bir araçtır *yığın ömrü* ve *veri üyesi ömrü* yüksek verimlilik ile — yaşam süresi izleme yükünü temelde ücretsizdir. Yığın nesne ömrü dikkatli el ile yönetim gerektirir ve özellikle, ham işaretçilerle çalışırken kaynak sızıntılarını ve verimsiz, kaynağı olabilir. Yığın tabanlı kapsam gösterir. Bu kodu göz önünde bulundurun:

```cpp
class widget {
private:
    gadget g;   // lifetime automatically tied to enclosing object
public:
    void draw();
};

void functionUsingWidget () {
    widget w;   // lifetime automatically tied to enclosing scope
                // constructs w, including the w.g gadget member
    // ...
    w.draw();
    // ...
} // automatic destruction and deallocation for w and w.g
  // automatic exception safety,
  // as if "finally { w.dispose(); w.g.dispose(); }"
```

Statik ömrü tedbirli şekilde kullanın (genel statik, işlev yerel statik) çünkü sorunlar ortaya çıkabilir. Bir genel nesnesinin Oluşturucusu bir özel durum oluşturduğunda ne olur? Genellikle, uygulama hatalarını hata ayıklaması zor olan şekilde. Oluşturma sırası statik ömrü nesneler için sorun yaratır ve eşzamanlılık açısından güvenli değildir. Yalnızca nesne oluşturmayı bir sorunu olduğunu, özellikle çok biçimlilik söz konusu olduğunda yok etme sırası karmaşık olabilir. Nesne veya değişkenin çok biçimli değil ve karmaşık oluşturma/sıralama yok etme sahip olsa da hala iş parçacığı eşzamanlılık ilgili bir sorun yoktur. Çok iş parçacıklı bir uygulama, iş parçacığı yerel depolama, kaynak kilitleri ve diğer özel önlemler zorunda kalmadan statik nesneler verileri güvenli bir şekilde değiştiremezsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[C++'a (Modern C++) Tekrar Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)
