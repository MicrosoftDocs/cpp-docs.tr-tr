---
title: Koleksiyonlar (C + +/ CX)
ms.date: 11/19/2018
ms.assetid: 914da30b-aac5-4cd7-9da3-a5ac08cdd72c
ms.openlocfilehash: 850ac0f4801a13a5407f8fe008740bbfa21cc02c
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57745424"
---
# <a name="collections-ccx"></a>Koleksiyonlar (C + +/ CX)

C + +/ CX programı, standart Şablon kitaplığı (STL) kapsayıcıları veya herhangi bir kullanıcı tanımlı toplama türü ücretsiz kullanımını yapabilirsiniz. Ancak, gönderdiğinizde koleksiyonları ve geriye Windows çalışma zamanı uygulama ikili arabiriminde (ABI) — Örneğin, bir XAML denetimi veya JavaScript istemci — Windows çalışma zamanı koleksiyon türleri kullanmanız gerekir.

Windows çalışma zamanı tanımlar arabirimleri koleksiyonları ve ilgili türleri ve C + +/ CX collection.h üstbilgi dosyasında somut C++ uygulamalarını sağlar. Bu çizimde, koleksiyon türleri arasındaki ilişkiler gösterilmektedir:

![C&#43;&#43;&#47;CX koleksiyon türleri için devralma ağacı](../cppcx/media/cppcxcollectionsinheritancetree.png "C&#43;&#43;&#47;CX koleksiyon türleri için devralma ağacı")

- [Platform::Collections:: Vector sınıfı](../cppcx/platform-collections-vector-class.md) benzer [std::vector sınıfı](../standard-library/vector-class.md).

- [Platform::Collections:: Map sınıfı](../cppcx/platform-collections-map-class.md) sınıfına benzer [std::map sınıfı](../standard-library/map-class.md).

- [Platform::Collections:: vectorview sınıfı](../cppcx/platform-collections-vectorview-class.md) ve[Platform::Collections:: mapview sınıfı](../cppcx/platform-collections-mapview-class.md) salt okunur sürümleri `Vector` ve `Map`.

- Yineleyiciler tanımlanmış [Platform::Collections Namespace](../cppcx/platform-collections-namespace.md). Bu yineleyiciler STL yineleyici için gereksinimleri karşılaması ve kullanımını etkinleştirmek [std::find](../standard-library/algorithm-functions.md#find), [std::count_if](../standard-library/algorithm-functions.md#count_if)ve herhangi başka bir STL algoritmaları [Windows::Foundation:: Collections](/uwp/api/windows.foundation.collections) arabirimi türüne veya [Platform::Collections](../cppcx/platform-collections-namespace.md) somut türü. Örneğin, bu bir koleksiyonda bir STL algoritması uygulamak ve C# içinde oluşturulan bir Windows çalışma zamanı bileşeni yineleyebilirsiniz anlamına gelir.

   > [!IMPORTANT]
   > Proxy yineleyiciler `VectorIterator` ve `VectorViewIterator` proxy nesneleri kullanan `VectoryProxy<T>` ve `ArrowProxy<T>` STL kapsayıcıları ile kullanımını etkinleştirmek için. Daha fazla bilgi için bu makalenin sonraki bölümlerinde yer alan "VectorProxy öğeler" bkz.

- C + +/ CX koleksiyon türleri desteği aynı iş parçacığı güvenliği garanti eder, STL kapsayıcıları destekler.

- [Windows::Foundation::Collections::IObservableVector](/uwp/api/Windows.Foundation.Collections.IObservableVector_T_) ve [Windows::Foundation::Collections::IObservableMap](/uwp/api/Windows.Foundation.Collections.IObservableMap_K_V_) çeşitli şekillerde koleksiyonu değiştiğinde tetikleyen olayları tanımlayın. Bu arabirimler uygulayarak [Platform::Collections:: Map](../cppcx/platform-collections-map-class.md) ve [Platform::Collections:: Vector](../cppcx/platform-collections-vector-class.md) XAML koleksiyonları ile veri bağlama desteği. Örneğin, bir `Vector` , veri bağlama için bir `Grid`olduğunda, bir koleksiyona bir öğe eklemek, bu değişiklik kılavuz kullanıcı Arabiriminde yansıtılır.

## <a name="vector-usage"></a>Vektör kullanımı

Başka bir Windows çalışma zamanı bileşeni için bir sıralı kapsayıcı geçirilecek sınıfınız varsa kullanın [Windows::Foundation:: Collections:: Ivector\<T >](/uwp/api/Windows.Foundation.Collections.IVector_T_) parametre veya dönüş türü olarak ve [Platform::Collections:: Vector\<T >](../cppcx/platform-collections-vector-class.md) somut bir uygulama olarak. Kullanmayı denerseniz bir `Vector` türü ortak dönüş değeri veya parametre, derleyici hatası C3986 yükseltilir. Hata değiştirerek düzeltebilirsiniz `Vector` için bir `IVector`.

> [!IMPORTANT]
> Kendi programında bir dizisini geçiriyorsanız, ya da kullanmak `Vector` veya `std::vector` daha verimlidir çünkü `IVector`. Kullanım `IVector` yalnızca kapsayıcı arasında ABI gönderdiğinizde.
>
> Windows çalışma zamanı tür sistemi, düzensiz diziler kavramını desteklemiyor ve bu nedenle bir Ivector geçirilemez < Platform::Array\<T >> dönüş değeri veya yöntemin parametre olarak. Basit bir dizi veya sıralarının ABI arasında geçirmek için kullanmak `IVector<IVector<T>^>`.

`Vector<T>` Koleksiyonda öğe ekleme, kaldırma ve erişme ve örtük olarak dönüştürülebilir için gerekli olan yöntemler sunar `IVector<T>`. STL algoritmaları örneklerinde kullanabilirsiniz `Vector<T>`. Aşağıdaki örnek, bazı temel kullanım gösterir. [Begin işlevi](../cppcx/begin-function.md) ve [end işlevi](../cppcx/end-function.md) aşağıda verilmiştir `Platform::Collections` ad alanı değil `std` ad alanı.

[!code-cpp[cx_collections#01](../cppcx/codesnippet/CPP/collections/class1.cpp#01)]

Kullanan mevcut kodu varsa `std::vector` istediğiniz bir Windows çalışma zamanı bileşeni yeniden kullanmak için yalnızca birini kullanın ve `Vector` alan oluşturucular bir `std::vector` veya oluşturmak için Yineleyicilerin bir çiftini bir `Vector` burada geçirdiğiniz bir noktada ABI koleksiyonunda. Aşağıdaki örnek nasıl kullanılacağını gösterir `Vector` taşıma Oluşturucu verimli başlatmadan için bir `std::vector`. Özgün taşıma işlemi sonrasında `vec` değişken artık geçerli değil.

[!code-cpp[cx_collections#02](../cppcx/codesnippet/CPP/collections/class1.cpp#02)]

Gelecekte bir noktada ABI üzerinden geçmelidir dizelerden oluşan bir vektörü varsa, dizeleri oluşturmak karar vermeniz gerekir başlangıçta olarak `std::wstring` türleri veya as `Platform::String^` türleri. Çok fazla işleme dizelerde yapmanız gerekiyorsa, ardından kullanmak `wstring`. Aksi takdirde, dize olarak oluşturun `Platform::String^` türlerini ve bunları daha sonra dönüştürme maliyeti kaçının. Ayrıca bu dizelere koymak karar vermeniz gerekir bir `std:vector` veya `Platform::Collections::Vector` dahili olarak. Genel bir uygulama olarak kullanın `std::vector` ve oluşturup bir `Platform::Vector` ABI arasında kapsayıcı geçirdiğinizde ait.

## <a name="value-types-in-vector"></a>Vektör içindeki değer türleri

Depolanması için herhangi bir öğenin bir [Platform::Collections:: Vector](../cppcx/platform-collections-vector-class.md) eşitlik karşılaştırması, örtük olarak ya da özel bir kullanarak desteklemelidir [std::equal_to](../standard-library/equal-to-struct.md) sağladığınız karşılaştırıcı. Tüm başvuru türleri ve tüm skaler türleri eşitlik karşılaştırmaları örtülü olarak destekler. Skaler olmayan için değer türleri gibi [Windows::Foundation::DateTime](/uwp/api/windows.foundation.datetime), ya da özel karşılaştırmalar için — örneğin, `objA->UniqueID == objB->UniqueID`— bir özel işlev nesnesini sağlamanız gerekir.

## <a name="vectorproxy-elements"></a>VectorProxy öğeleri

[Platform::Collections:: vectorıterator](../cppcx/platform-collections-vectoriterator-class.md) ve [Platform::Collections:: vectorviewıterator](../cppcx/platform-collections-vectorviewiterator-class.md) kullanımını etkinleştirmek `range for` döngüler ve algoritmaları gibi [std::sort](../standard-library/algorithm-functions.md#sort) bir ile[ Ivector\<T >](/uwp/api/Windows.Foundation.Collections.IVector_T_) kapsayıcı. Ancak `IVector` öğeleri C++ erişilemez bir işaretçiye; yalnızca aracılığıyla erişilebilen [GetAt](/uwp/api/windows.foundation.collections.ivector-1.getat) ve [SetAt](/uwp/api/windows.foundation.collections.ivector-1.setat) yöntemleri. Bu nedenle, bu Yineleyicilerde proxy sınıfları kullanması `Platform::Details::VectorProxy<T>` ve `Platform::Details::ArrowProxy<T>` tek tek öğelerine erişim sağlamak için __\*__, __->__ ve  __\[]__ işleçleri, standart kitaplık gerektirdiği gibi. NET olarak söylemek gerekirse, verilen bir `IVector<Person^> vec`, türü `*begin(vec)` olduğu `VectorProxy<Person^>`. Ancak, proxy neredeyse her zaman kodunuza saydam nesnedir. Yineleyiciler tarafından iç kullanım için yalnızca olduklarından, ancak mekanizması nasıl çalıştığını bilmek yararlıdır çünkü bu proxy nesneleri açıklanmamıştır.

Kullandığınızda, bir `range for` üzerinden döngü `IVector` kapsayıcılarını, `auto&&` doğru olarak bağlamak için yineleyici değişken etkinleştirmek için `VectorProxy` öğeleri. Kullanırsanız `auto` veya `auto&`, derleyici uyarısı C4239 oluşturulur ve `VectoryProxy` uyarı metinde açıklanan.

Aşağıdaki çizimde gösterildiği bir `range for` üzerinden döngü bir `IVector<Person^>`. Yürütme 64 satırında bir kesme noktasında durdurulduğunu dikkat edin. **QuickWatch** penceresi gösterir, yineleyici değişkeni `p` aslında bir `VectorProxy<Person^>` olan `m_v` ve `m_i` üye değişkenleri. Ancak, çağırdığınızda `GetType` isteğe bağlı olarak bu değişken için aynı türde döndürür `Person` örneği `p2`. Ancak olan takeaway `VectorProxy` ve `ArrowProxy` görünebilir **QuickWatch**, hata ayıklayıcı belirli derleyici hataları veya diğer yerler genellikle bunlar için kod gerekmez.

![Aralıktaki VectorProxy&#45;tabanlı for döngüsü](../cppcx/media/vectorproxy-1.png "aralıktaki VectorProxy&#45;tabanlı for döngüsü")

Sahip olduğunuz koda proxy nesne çevresinde bir senaryo gerçekleştirmek için sahip olduğunda bir `dynamic_cast` öğelerde — Örneğin, ne zaman aradığınız XAML nesneleri belirli bir türün bir `UIElement` öğe koleksiyonu. Bu durumda, ilk öğeye dönüştürmelisiniz [Platform::Object](../cppcx/platform-object-class.md)^ ve dinamik atama gerçekleştirin:

```cpp
void FindButton(UIElementCollection^ col)
{
    // Use auto&& to avoid warning C4239
    for (auto&& elem : col)
    {
        Button^ temp = dynamic_cast<Button^>(static_cast<Object^>(elem));
        if (nullptr != temp)
        {
            // Use temp...
        }
    }
}
```

## <a name="map-usage"></a>Eşleme kullanımı

Bu örnek, aramak ve öğeleri eklemek nasıl gösterir bir [Platform::Collections:: Map](../cppcx/platform-collections-map-class.md)ve ardından dönün `Map` olarak bir salt okunur [Windows::Foundation::Collections::IMapView] / uwp/api / Windows.Foundation.Collections.IMapView_K_V_) türü.

[!code-cpp[cx_collections#04](../cppcx/codesnippet/CPP/collections/class1.cpp#04)]

Genel olarak, iç eşleme işlevselliği için tercih ettiğiniz `std::map` Performans nedeniyle türü. ABI arasında kapsayıcı geçirmek zorundaysanız, oluşturun bir [Platform::Collections:: Map](../cppcx/platform-collections-map-class.md) gelen [std::map](../standard-library/map-class.md) ve dönüş `Map` olarak bir [Windows::Foundation:: Collections::IMap](/uwp/api/Windows.Foundation.Collections.IMap_K_V_). Kullanmayı denerseniz bir `Map` türü ortak dönüş değeri veya parametre, derleyici hatası C3986 yükseltilir. Hata değiştirerek düzeltebilirsiniz `Map` için bir `IMap`. Bazı durumlarda — Örneğin, çok sayıda aramaları veya eklemeler yaparak değil ve koleksiyon sık ABI geçirdiğinizden — kullanmak daha ucuz olabilir `Platform::Collections::Map` baştan ve dönüştürmemaliyetiönlemek`std::map`. Herhangi bir durumda, arama önlemek ve üzerinde ekleme işlemlerinin bir `IMap` çünkü bunlar en yüksek performanslı üç tür. Dönüştürme `IMap` yalnızca kapsayıcı ABI arasında geçirmek noktada.

## <a name="value-types-in-map"></a>Eşlem içindeki değer türleri

Öğeleri bir [Platform::Collections:: Map](../cppcx/platform-collections-map-class.md) sıralanır. Depolanması için herhangi bir öğenin bir `Map` daha az desteklemesi gerekir-örtük olarak ya da özel bir kullanarak sıralama katı zayıf ile karşılaştırması [stl::less](../standard-library/less-struct.md) sağladığınız karşılaştırıcı. Skaler türleri, karşılaştırma dolaylı olarak destekler. Skaler olmayan için değer türleri gibi `Windows::Foundation::DateTime`, ya da özel karşılaştırmalar için — örneğin, `objA->UniqueID < objB->UniqueID`— özel bir karşılaştırıcı sağlamanız gerekir.

## <a name="collection-types"></a>Koleksiyon türleri

Koleksiyonlar, dört kategoriye ayrılır: salt okunur sürümleri sıra koleksiyonlar ve ilişkili koleksiyonlar ve değiştirilebilir. Ayrıca, C + +/ CX koleksiyonları erişme basitleştiren üç yineleyici sınıflar sağlayarak koleksiyonları geliştirir.

Değiştirilebilir bir koleksiyonun öğeleri değiştirilebilir, ancak olarak bilinen bir salt okunur koleksiyon öğelerini bir *görünümü*, salt okunur. Öğeleri bir [Platform::Collections:: Vector](../cppcx/platform-collections-vector-class.md) veya[Platform::Collections:: vectorview](../cppcx/platform-collections-vectorview-class.md) koleksiyonu, bir yineleyici veya koleksiyonun kullanarak erişilebilir [Vector::GetAt](../cppcx/platform-collections-vector-class.md#getat) ve dizin. İlişkili bir koleksiyon öğelerini koleksiyonun kullanarak erişilebilir [Map::Lookup](../cppcx/platform-collections-map-class.md#lookup) ve bir anahtar.

[Platform::Collections::Map Sınıfı](../cppcx/platform-collections-map-class.md)<br/>
Değiştirilebilir, ilişkili bir koleksiyon. Harita öğelerine anahtar-değer çiftleridir. İlişkili değerini ve tüm anahtar-değer çiftleri yineleme almak için bir anahtar arama, her ikisi de desteklenir.

`Map` ve `MapView` şablonlu üzerinde olan `<K, V, C = std::less<K>>`; bu nedenle karşılaştırıcı özelleştirebilirsiniz.  Ayrıca, `Vector` ve `VectorView` şablonlu üzerinde olan `<T, E = std::equal_to<T>>` davranışını özelleştirebilmeniz için `IndexOf()`. Bu çoğunlukla için önemlidir `Vector` ve `VectorView` değeri yapılar. Örneğin, bir vektör oluşturmak için\<Windows::Foundation::DateTime >, DateTime aşırı yüklenebilir değil çünkü özel bir karşılaştırıcı sağlamalısınız == işleci.

[Platform::Collections::MapView Sınıfı](../cppcx/platform-collections-mapview-class.md)<br/>
Salt okunur bir sürümünü bir `Map`.

[Platform::Collections::Vector Sınıfı](../cppcx/platform-collections-vector-class.md)<br/>
Değiştirilebilir dizisi koleksiyonu. `Vector<T>` sabiti zamanı rastgele erişim ve amorti edilmiş-sabit zamanlı destekler [ekleme](../cppcx/platform-collections-vector-class.md#append) işlemleri...

[Platform::Collections::VectorView Sınıfı](../cppcx/platform-collections-vectorview-class.md)<br/>
Salt okunur bir sürümünü bir `Vector`.

[Platform::Collections::InputIterator Sınıfı](../cppcx/platform-collections-inputiterator-class.md)<br/>
Bir STL giriş yineleyici gereksinimlerini karşılayan bir STL yineleyici.

[Platform::Collections::VectorIterator Sınıfı](../cppcx/platform-collections-vectoriterator-class.md)<br/>
STL değişebilir rastgele erişim yineleyici gereksinimlerini karşılayan bir STL yineleyici.

[Platform::Collections::VectorViewIterator Sınıfı](../cppcx/platform-collections-vectorviewiterator-class.md)<br/>
Bir STL gereksinimlerini karşılayan bir STL yineleyici `const` rasgele erişim yineleyicisi.

### <a name="begin-and-end-functions"></a>const_iterator ve end() işlevleri

İşlenecek STL kullanımını basitleştirmek için `Vector`, `VectorView`, `Map`, `MapView`ve rastgele `Windows::Foundation::Collections` nesneleri, C + +/ CX aşırı yüklemeleri destekler [begin işlevi](../cppcx/begin-function.md) ve [bitiş İşlev](../cppcx/end-function.md) üye harici işlevleri.

Aşağıdaki tabloda kullanılabilir yineleyiciler ve işlevleri listeler.

|Yineleyiciler|İşlevler|
|---------------|---------------|
|[Platform::Collections:: vectorıterator\<T >](../cppcx/platform-collections-vectoriterator-class.md)<br /><br /> (Dahili olarak depolayan [Windows::Foundation:: Collections:: Ivector\<T >](/uwp/api/Windows.Foundation.Collections.IVector_T_) ve tamsayı)|[başlamak](../cppcx/begin-function.md)/ [son](../cppcx/end-function.md)([Windows::Foundation:: Collections:: Ivector\<T >](/uwp/api/Windows.Foundation.Collections.IVector_T_))|
|[Platform::Collections:: vectorviewıterator\<T >](../cppcx/platform-collections-vectorviewiterator-class.md)<br /><br /> (Dahili olarak depolayan [IVectorView\<T >](/uwp/api/Windows.Foundation.Collections.IVectorView_T_)^ ve tamsayı)|[başlamak](../cppcx/begin-function.md)/ [son](../cppcx/end-function.md) ([IVectorView\<T >](/uwp/api/Windows.Foundation.Collections.IVectorView_T_)^)|
|[Platform::Collections:: ınputıterator\<T >](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> (Dahili olarak depolayan [IIterator\<T >](/uwp/api/Windows.Foundation.Collections.IIterator_T_)^ ve t)|[başlamak](../cppcx/begin-function.md)/ [son](../cppcx/end-function.md) ([Iıterable\<T >](/uwp/api/Windows.Foundation.Collections.IIterable_T_))|
|[Platform::Collections:: ınputıterator < IKeyValuePair\<K, V > ^ >](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> (Dahili olarak depolayan [IIterator\<T >](/uwp/api/Windows.Foundation.Collections.IIterator_T_)^ ve t)|[başlamak](../cppcx/begin-function.md)/ [son](../cppcx/end-function.md) ([IMAP\<K, V >](/uwp/api/Windows.Foundation.Collections.IMap_K_V_).|
|[Platform::Collections:: ınputıterator < IKeyValuePair\<K, V > ^ >](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> (Dahili olarak depolayan [IIterator\<T >](/uwp/api/Windows.Foundation.Collections.IIterator_T_)^ ve t)|[başlamak](../cppcx/begin-function.md)/ [son](../cppcx/end-function.md) ([Windows:: Foundation::Collections::IMapView]/uwp/api/Windows.Foundation.Collections.IMapView_K_V_))|

### <a name="collection-change-events"></a>Toplama değişiklik olayları

`Vector` ve `Map` koleksiyon nesnesi değiştirildiğinde meydana gelen olayları veya sıfırlama uygulayarak XAML koleksiyonları'nda veri bağlama desteği veya bir koleksiyonun herhangi bir öğe eklendiğinde, kaldırıldı veya değiştirildi. Öğesinden devralamaz olsa da bu destek veri bağlama kendi türlerinizi yazabilirsiniz `Map` veya `Vector` türlerine korumalı olduğundan.

[Windows::Foundation::Collections::VectorChangedEventHandler](/uwp/api/windows.foundation.collections.vectorchangedeventhandler) ve [Windows::Foundation::Collections::MapChangedEventHandler](/uwp/api/windows.foundation.collections.mapchangedeventhandler) temsilcileri belirtmek için olay işleyicileri imzaları değişiklik olayları koleksiyonu. [Windows::Foundation::Collections::CollectionChange](/uwp/api/windows.foundation.collections.collectionchange) genel sabit listesi sınıfı ve `Platform::Collection::Details::MapChangedEventArgs` ve `Platform::Collections::Details::VectorChangedEventArgs` başvuru sınıfları depolamak olay nedenini belirlemek için olay bağımsız değişkenleri. `*EventArgs` Türleri `Details` ad alanı oluşturmak veya bunları açıkça kullandığınızda kullanmak durumunda olmadığınızdan dolayı `Map` veya `Vector`.

## <a name="see-also"></a>Ayrıca bkz.

[Tür Sistemi](../cppcx/type-system-c-cx.md)<br/>
[Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)
