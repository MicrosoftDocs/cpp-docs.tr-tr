---
title: Koleksiyonlar (C++/CX)
ms.date: 11/19/2018
ms.assetid: 914da30b-aac5-4cd7-9da3-a5ac08cdd72c
ms.openlocfilehash: ff3fb9899355ec05083dc15c16d74c9aa1d3fd8f
ms.sourcegitcommit: 8178d22701047d24f69f10d01ba37490e3d67241
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2019
ms.locfileid: "70740325"
---
# <a name="collections-ccx"></a>Koleksiyonlar (C++/CX)

Bir C++/CX programında standart şablon KITAPLıĞı (STL) kapsayıcılarından veya Kullanıcı tanımlı başka bir koleksiyon türünden ücretsiz kullanım sağlayabilirsiniz. Ancak, koleksiyonları Windows Çalışma Zamanı uygulama ikili arabiriminde (ABı) (örneğin, bir XAML denetimine veya bir JavaScript istemcisine) geri ve ileri geçirdiğinizde, Windows Çalışma Zamanı koleksiyon türlerini kullanmanız gerekir.

Windows Çalışma Zamanı koleksiyonlar ve ilgili türlerin arabirimlerini tanımlar ve C++/CX, koleksiyon. h üstbilgi dosyasında somut C++ uygulamalar sağlar. Bu çizimde, koleksiyon türleri arasındaki ilişkiler gösterilmektedir:

![Koleksiyon&#43;&#43;&#47;türleri için C CX devralma ağacı](../cppcx/media/cppcxcollectionsinheritancetree.png "Koleksiyon&#43;&#43;&#47;türleri için C CX devralma ağacı")

- [Platform:: Collections:: Vector sınıfı](../cppcx/platform-collections-vector-class.md) [std:: vector sınıfına](../standard-library/vector-class.md)benzer.

- [Platform:: Collections:: Map sınıf](../cppcx/platform-collections-map-class.md) sınıfı, [std:: Map sınıfına](../standard-library/map-class.md)benzer.

- [Platform:: Collections:: VectorView sınıfı](../cppcx/platform-collections-vectorview-class.md) ve[Platform:: Collections:: mapview sınıfı](../cppcx/platform-collections-mapview-class.md) , `Vector` ve `Map` salt okuma sürümleridir.

- Yineleyiciler [Platform:: Collections ad alanında](../cppcx/platform-collections-namespace.md)tanımlanmıştır. Bu yineleyiciler STL yineleyiciler için gereksinimleri karşılar ve herhangi bir [Windows:: Foundation:: Collections](/uwp/api/windows.foundation.collections) arabirim türü veya [Platform:: Collections](../cppcx/platform-collections-namespace.md) üzerinde [std:: Find](../standard-library/algorithm-functions.md#find), [std:: count_if](../standard-library/algorithm-functions.md#count_if)ve diğer stl algoritmalarının kullanılmasını sağlar somut tür. Örneğin, bu, içinde C# oluşturulan bir Windows çalışma zamanı bileşeninde bir koleksiyonu yineleyebilir ve kendısıne bir STL algoritması uygulayabilir.

   > [!IMPORTANT]
   > Proxy yineleyiciler `VectorIterator` ve `VectorViewIterator`, STL kapsayıcılarıyla kullanımı etkinleştirmek için `VectoryProxy<T>` ve `ArrowProxy<T>` proxy nesneleri kullanır. Daha fazla bilgi için bu makalenin devamındaki "VectorProxy öğeleri" başlığına bakın.

- C++/CX koleksiyon TÜRLERI, STL kapsayıcılarının desteklediği iş parçacığı güvenliği garantisi destekler.

- [Windows:: Foundation:: Collections:: IObservableVector](/uwp/api/Windows.Foundation.Collections.IObservableVector_T_) ve [Windows:: Foundation:: Collections:: ıobservablemap](/uwp/api/Windows.Foundation.Collections.IObservableMap_K_V_) , koleksiyon çeşitli şekillerde değiştiğinde harekete geçirilen olayları tanımlar. Bu arabirimleri uygulayarak [Platform:: Collections:: Map](../cppcx/platform-collections-map-class.md) ve [Platform:: Collections:: vector](../cppcx/platform-collections-vector-class.md) ' ı xaml koleksiyonlarıyla veri bağlamayı destekler. Örneğin, bir `Grid` veri ile bağlantılı bir `Vector` varsa, bir koleksiyona bir öğe eklediğinizde, değişiklik kılavuz Kullanıcı arabirimine yansıtılır.

## <a name="vector-usage"></a>Vektör kullanımı

Sınıfınız, bir dizi kapsayıcısını başka bir Windows Çalışma Zamanı bileşenine iletmeniz gerektiğinde, parametre veya dönüş türü olarak [Windows:: Foundation:: Collections:: ıvector \<T >](/uwp/api/Windows.Foundation.Collections.IVector_T_) ve [Platform:: Collections:: vector \<T >](../cppcx/platform-collections-vector-class.md) somut uygulama. Ortak dönüş değeri veya parametresinde bir `Vector` türü kullanmaya çalışırsanız, derleyici hatası C3986 tetiklenir. @No__t_0 bir `IVector` değiştirerek hatayı çözebilirsiniz.

> [!IMPORTANT]
> Kendi programınız dahilinde bir sıra geçirçalışıyorsanız, `IVector` daha verimli olduklarından `Vector` veya `std::vector` kullanın. Yalnızca kapsayıcıyı ABı üzerinden geçirdiğinizde `IVector` kullanın.
>
> Windows Çalışma Zamanı tür sistemi pürüzlü Diziler kavramını desteklemez ve bu nedenle bir IVector < Platform:: Array \<T > > dönüş değeri veya yöntem parametresi olarak geçiremezsiniz. ABı genelinde pürüzlü bir diziyi veya dizi dizilerini geçirmek için `IVector<IVector<T>^>` kullanın.

`Vector<T>` koleksiyondaki öğeleri eklemek, kaldırmak ve bunlara erişmek için gereken yöntemleri sağlar ve `IVector<T>` örtülü olarak dönüştürülebilir. Ayrıca, `Vector<T>` örneklerinde STL algoritmaları da kullanabilirsiniz. Aşağıdaki örnekte, bazı temel kullanımlar gösterilmektedir. Burada [BEGIN Function](../cppcx/begin-function.md) ve [end işlevi](../cppcx/end-function.md) , `std` ad alanından değil `Platform::Collections` ad alanıdır.

[!code-cpp[cx_collections#01](../cppcx/codesnippet/CPP/collections/class1.cpp#01)]

@No__t_0 kullanan mevcut kodunuz varsa ve onu Windows Çalışma Zamanı bir bileşende yeniden kullanmak istiyorsanız, koleksiyonu geçirdiğiniz noktada bir `Vector` oluşturmak için `std::vector` veya yineleyiciler çifti alan `Vector` oluşturuculardan birini kullanmanız yeterlidir ABı genelinde. Aşağıdaki örnek, `std::vector` bir `Vector` taşıma oluşturucusunun etkin başlatma için nasıl kullanılacağını gösterir. Taşıma işleminden sonra, özgün `vec` değişkeni artık geçerli değildir.

[!code-cpp[cx_collections#02](../cppcx/codesnippet/CPP/collections/class1.cpp#02)]

Gelecekteki bir noktada ABı üzerinde geçiş yapmanız gereken bir dize vektörünün varsa, başlangıçta `std::wstring` türler olarak veya `Platform::String^` türler olarak dize oluşturup oluşturmayacağınıza karar vermelisiniz. Dizelerde çok fazla işlem yapmanız gerekiyorsa `wstring` kullanın. Aksi takdirde, dizeleri `Platform::String^` türleri olarak oluşturun ve daha sonra dönüştürme maliyetinden kaçının. Ayrıca, bu dizeleri bir `std:vector` mi yoksa dahili olarak `Platform::Collections::Vector` mı koyacağınıza karar vermelisiniz. Genel bir uygulama olarak, `std::vector` kullanın ve sonra yalnızca kapsayıcıyı ABı arasında geçirdiğinizde bir `Platform::Vector` oluşturun.

## <a name="value-types-in-vector"></a>Vektördeki değer türleri

[Platform:: Collections:: vector](../cppcx/platform-collections-vector-class.md) içinde depolanacak herhangi bir öğe, örtük olarak veya sağladığınız özel bir [std:: equal_to](../standard-library/equal-to-struct.md) karşılaştırıcısı kullanarak eşitlik karşılaştırmayı desteklemelidir. Tüm başvuru türleri ve tüm skaler türler, eşitlik karşılaştırmaları örtülü olarak destekler. [Windows:: Foundation::D ateTime](/uwp/api/windows.foundation.datetime)veya özel karşılaştırmalar gibi skaler olmayan değer türleri için, örneğin, `objA->UniqueID == objB->UniqueID` — özel bir işlev nesnesi sağlamanız gerekir.

## <a name="vectorproxy-elements"></a>VectorProxy öğeleri

[Platform:: Collections:: VectorIterator](../cppcx/platform-collections-vectoriterator-class.md) ve [Platform:: Collections:: Vectorviewwiterator](../cppcx/platform-collections-vectorviewiterator-class.md) , `range for` döngülerin ve [std:: Sort](../standard-library/algorithm-functions.md#sort) gibi algoritmaların bir [IVector \<T >](/uwp/api/Windows.Foundation.Collections.IVector_T_) kapsayıcısı ile kullanılmasını sağlar. Ancak `IVector` öğelerine işaretçi başvurusu üzerinden C++ erişilemez; bunlara yalnızca [GetAt](/uwp/api/windows.foundation.collections.ivector-1.getat) ve [SetAt](/uwp/api/windows.foundation.collections.ivector-1.setat) yöntemleri aracılığıyla erişilebilir. Bu nedenle, bu yineleyiciler, standart kitaplığın gerektirdiği şekilde __\*__ , __->__ ve __\[]__ işleçleriyle tek tek öğelere erişim sağlamak için `Platform::Details::VectorProxy<T>` ve `Platform::Details::ArrowProxy<T>` ara sunucu sınıflarını kullanır. @No__t_0 verildiğinde, `*begin(vec)` türü `VectorProxy<Person^>`, kesinlikle konuşuyor. Ancak, proxy nesnesi neredeyse her zaman kodunuz için saydamdır. Bu proxy nesneleri yalnızca yineleyiciler tarafından iç kullanım için olduklarından belgelenmemiştir, ancak mekanizmanın nasıl çalıştığını öğrenmek faydalı olur.

@No__t_1 kapsayıcıları üzerinde `range for` döngüsü kullandığınızda, yineleyici değişkeninin `VectorProxy` öğelerine doğru şekilde bağlanması için `auto&&` kullanın. @No__t_0 veya `auto&` kullanırsanız, derleyici uyarısı C4239 oluşturulur ve uyarı metninde `VectoryProxy` bahsedilir.

Aşağıdaki çizimde bir `IVector<Person^>` `range for` döngüsü gösterilmektedir. Yürütmenin 64. satırdaki kesme noktasında durdurulduğuna dikkat edin. **QuickWatch** penceresinde, yineleyici değişkeninin `p` aslında `m_v` ve `m_i` üye değişkenleri olan bir `VectorProxy<Person^>` olduğunu gösterir. Ancak, bu değişkende `GetType` çağırdığınızda, `Person` örnek `p2` aynı türü döndürür. Bu, `VectorProxy` ve `ArrowProxy` **hızlı**bir şekilde, hata ayıklayıcı belirli derleyici hatalarının veya başka yerlerde görünebilse de, genellikle açıkça kod yazmanız gerekmez.

![Döngü tabanlı aralıktaki&#45;VectorProxy](../cppcx/media/vectorproxy-1.png "Döngü tabanlı aralıktaki&#45;VectorProxy")

Proxy nesnesi etrafında kod yazmanız gereken bir senaryo (örneğin, `UIElement` bir öğe koleksiyonundaki belirli bir türün XAML nesnelerini ararken), öğeler üzerinde `dynamic_cast` gerçekleştirmeniz gerektiğinde. Bu durumda, önce öğeyi [Platform:: Object](../cppcx/platform-object-class.md)^ olarak atamalısınız ve sonra dinamik cast işlemini gerçekleştirmelisiniz:

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

Bu örnek, öğelerin nasıl ekleneceğini ve bir [Platform:: Collections:: Map](../cppcx/platform-collections-map-class.md)dosyasında nasıl görüneceğini gösterir ve ardından `Map` salt okunurdur bir [Windows:: Foundation:: Collections:: ımapview]/UWP/api/Windows.Foundation.Collections.IMapView_K_V_) türü olarak döndürür.

[!code-cpp[cx_collections#04](../cppcx/codesnippet/CPP/collections/class1.cpp#04)]

Genel olarak, iç eşleme işlevselliği için performans nedenleriyle `std::map` türünü tercih edin. Kapsayıcıyı ABı arasında geçirmeniz gerekiyorsa, [std:: map](../standard-library/map-class.md) ' ten bir [Platform:: Collections:: map](../cppcx/platform-collections-map-class.md) oluşturun ve `Map` bir [Windows:: Foundation:: Collections::](/uwp/api/Windows.Foundation.Collections.IMap_K_V_)Map olarak döndürün. Ortak dönüş değeri veya parametresinde bir `Map` türü kullanmaya çalışırsanız, derleyici hatası C3986 tetiklenir. @No__t_0 bir `IMap` değiştirerek hatayı çözebilirsiniz. Bazı durumlarda — örneğin, çok sayıda arama veya ekleme gerçekleştirmeyin ve koleksiyonu ABı sıklıkla geçirdiğinize göre — bu, baştan `Platform::Collections::Map` kullanımı daha pahalı olabilir ve `std::map` dönüştürme maliyetinden kaçınabilirsiniz. Her durumda, bir `IMap` arama ve ekleme işlemlerinden kaçının, çünkü bunlar üç türün en düşük performantlardır. Yalnızca kapsayıcıyı ABı üzerinden geçirdiğiniz noktada `IMap` dönüştürün.

## <a name="value-types-in-map"></a>Eşlemedeki değer türleri

[Platform:: Collections:: Map](../cppcx/platform-collections-map-class.md) içindeki öğeler sıralanmıştır. Bir `Map` depolanacak her öğe, örtük olarak veya sağladığınız özel bir [STL:: less](../standard-library/less-struct.md) karşılaştırıcısı kullanarak, katı zayıf sıralamaya sahip küçüktür karşılaştırmayı desteklemelidir. Skaler türler karşılaştırmayı örtülü olarak destekler. @No__t_0 gibi skalar olmayan değer türleri veya özel karşılaştırmalar için — örneğin, `objA->UniqueID < objB->UniqueID` — özel bir karşılaştırıcı sağlamanız gerekir.

## <a name="collection-types"></a>Koleksiyon türleri

Koleksiyonlar dört kategoriye ayrılır: değiştirilebilir sürümler ve dizi koleksiyonlarının ve ilişkilendirilebilir koleksiyonların salt okunurdur. Ayrıca, C++/CX koleksiyonlara erişimi basitleştiren üç Yineleyici sınıfı sağlayarak koleksiyonları geliştirir.

Değiştirilebilir bir koleksiyonun öğeleri değiştirilebilir, ancak *Görünüm*olarak bilinen bir salt okuma koleksiyonunun öğeleri yalnızca okunabilir. Platform:: [Collections:: vector](../cppcx/platform-collections-vector-class.md) veya[Platform:: Collections:: vectorview](../cppcx/platform-collections-vectorview-class.md) koleksiyonunun öğelerine bir yineleyici veya koleksiyonun [vector:: GetAt](../cppcx/platform-collections-vector-class.md#getat) ve bir dizin kullanılarak erişilebilir. İlişkilendirilebilir bir koleksiyonun öğelerine, koleksiyonun [map:: Lookup](../cppcx/platform-collections-map-class.md#lookup) ve bir anahtar kullanılarak erişilebilir.

[Platform::Collections::Map Sınıfı](../cppcx/platform-collections-map-class.md)<br/>
Değiştirilebilir, ilişkilendirilebilir bir koleksiyon. Eşleme öğeleri anahtar-değer çiftleridir. İlişkili değerini almak için bir anahtar aranıyor ve tüm anahtar-değer çiftlerine yineleme, her ikisi de desteklenir.

`Map` ve `MapView` `<K, V, C = std::less<K>>` üzerinde şablonlanır; Bu nedenle, karşılaştırıcısı özelleştirebilirsiniz.  Ayrıca, `IndexOf()` davranışını özelleştirebilmeniz için `Vector` ve `VectorView` `<T, E = std::equal_to<T>>` şablonu oluşturulur. Bu, çoğunlukla değer yapıların `Vector` ve `VectorView` için önemlidir. Örneğin, bir vektör \<Windows oluşturmak için:: Foundation::D ateTime >, DateTime = = işlecini aşırı yükmediği için özel bir karşılaştırıcı sağlamanız gerekir.

[Platform::Collections::MapView Sınıfı](../cppcx/platform-collections-mapview-class.md)<br/>
Bir `Map` salt okunurdur.

[Platform::Collections::Vector Sınıfı](../cppcx/platform-collections-vector-class.md)<br/>
Değiştirilebilir sıralı bir koleksiyon. `Vector<T>`, sabit zamanlı rasgele erişimi ve itfası sabit zamanlı [ekleme](../cppcx/platform-collections-vector-class.md#append) işlemlerini destekler.

[Platform::Collections::VectorView Sınıfı](../cppcx/platform-collections-vectorview-class.md)<br/>
Bir `Vector` salt okunurdur.

[Platform::Collections::InputIterator Sınıfı](../cppcx/platform-collections-inputiterator-class.md)<br/>
STL giriş yineleyicisinin gereksinimlerini karşılayan bir STL Yineleyici.

[Platform::Collections::VectorIterator Sınıfı](../cppcx/platform-collections-vectoriterator-class.md)<br/>
STL kesilebilir bir rastgele erişim Yineleyici gereksinimini karşılayan bir STL Yineleyici.

[Platform::Collections::VectorViewIterator Sınıfı](../cppcx/platform-collections-vectorviewiterator-class.md)<br/>
STL `const` rastgele erişim yineleyicisinin gereksinimlerini karşılayan bir STL Yineleyici.

### <a name="begin-and-end-functions"></a>Begin () ve End () işlevleri

C++/Cx, `Vector`, `VectorView`, `Map`, `MapView` ve rastgele `Windows::Foundation::Collections` nesnelerini işlemek için kullanmayı basitleştirmek amacıyla [BEGIN Function](../cppcx/begin-function.md) ve [End Function](../cppcx/end-function.md) üye olmayan işlevlerin aşırı yüklerini destekler.

Aşağıdaki tabloda, kullanılabilir yineleyiciler ve işlevler listelenmektedir.

|Yineleyiciler|İşlevler|
|---------------|---------------|
|[Platform:: Collections:: Vectorterator \<T >](../cppcx/platform-collections-vectoriterator-class.md)<br /><br /> ( [Windows:: Foundation:: Collections:: IVector \<T >](/uwp/api/Windows.Foundation.Collections.IVector_T_) ve int 'i dahili olarak depolar.)|[başlangıç](../cppcx/begin-function.md) / [bitişi](../cppcx/end-function.md)([Windows:: Foundation:: Collections:: IVector \<T >](/uwp/api/Windows.Foundation.Collections.IVector_T_))|
|[Platform:: Collections:: VectorViewIterator \<T >](../cppcx/platform-collections-vectorviewiterator-class.md)<br /><br /> ( [Ivectorview \<T >](/uwp/api/Windows.Foundation.Collections.IVectorView_T_)^ ve int olarak depolanır.)|[başlangıç](../cppcx/begin-function.md) / [bitiş](../cppcx/end-function.md) ([ıvectorview \<T >](/uwp/api/Windows.Foundation.Collections.IVectorView_T_)^)|
|[Platform:: Collections:: InputIterator \<T >](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> ( [Iıterator \<T >](/uwp/api/Windows.Foundation.Collections.IIterator_T_)^ ve t olarak depolanır.)|/ [sona](../cppcx/end-function.md) [başla](../cppcx/begin-function.md) ([ıiterable \<T >](/uwp/api/Windows.Foundation.Collections.IIterable_T_))|
|[Platform:: Collections:: InputIterator < IKeyValuePair \<K, V > ^ >](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> ( [Iıterator \<T >](/uwp/api/Windows.Foundation.Collections.IIterator_T_)^ ve t olarak depolanır.)|[/ ](../cppcx/begin-function.md) [bitiş](../cppcx/end-function.md) ([IMAP \<K, V >](/uwp/api/Windows.Foundation.Collections.IMap_K_V_).|
|[Platform:: Collections:: InputIterator < IKeyValuePair \<K, V > ^ >](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> ( [Iıterator \<T >](/uwp/api/Windows.Foundation.Collections.IIterator_T_)^ ve t olarak depolanır.)|[başlangıç](../cppcx/begin-function.md) / [bitişi](../cppcx/end-function.md) ([Windows:: Foundation:: Collections:: ımapview]/UWP/api/Windows.Foundation.Collections.IMapView_K_V_))|

### <a name="collection-change-events"></a>Koleksiyon değişiklik olayları

`Vector` ve `Map`, bir koleksiyon nesnesi değiştirildiğinde veya sıfırlandığında ya da bir koleksiyonun herhangi bir öğesi eklendiğinde, kaldırıldığında veya değiştirildiğinde oluşan olayları uygulayarak XAML koleksiyonlarında veri bağlamayı destekler. Veri bağlamayı destekleyen kendi türlerinizi yazabilirsiniz, ancak `Map` veya `Vector` kalýtýmla, bu türler mühürlenmiş.

[Windows:: Foundation:: Collections:: VectorChangedEventHandler](/uwp/api/windows.foundation.collections.vectorchangedeventhandler) ve [Windows:: Foundation:: Collections:: MapChangedEventHandler](/uwp/api/windows.foundation.collections.mapchangedeventhandler) Delegates, koleksiyon değişiklik olayları için olay işleyicilerine yönelik imzaları belirler. [Windows:: Foundation:: Collections:: CollectionChange](/uwp/api/windows.foundation.collections.collectionchange) public enum class ve `Platform::Collection::Details::MapChangedEventArgs` ve `Platform::Collections::Details::VectorChangedEventArgs` başvuru sınıfları, olaya neyin neden olduğunu belirlemek için olay bağımsız değişkenlerini depolar. @No__t_0 türler, `Map` veya `Vector` kullandığınızda bunları açıkça oluşturmak veya kullanmak zorunda olmadığınızdan, `Details` ad alanında tanımlanır.

## <a name="see-also"></a>Ayrıca bkz.

[Tür Sistemi](../cppcx/type-system-c-cx.md)<br/>
[C++/CX Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad Alanları Başvurusu](../cppcx/namespaces-reference-c-cx.md)
