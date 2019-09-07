---
title: Koleksiyonlar (C++/CX)
ms.date: 11/19/2018
ms.assetid: 914da30b-aac5-4cd7-9da3-a5ac08cdd72c
ms.openlocfilehash: ff3fb9899355ec05083dc15c16d74c9aa1d3fd8f
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740325"
---
# <a name="collections-ccx"></a>Koleksiyonlar (C++/CX)

Bir C++/CX programında standart şablon KITAPLıĞı (STL) kapsayıcılarından veya Kullanıcı tanımlı başka bir koleksiyon türünden ücretsiz kullanım sağlayabilirsiniz. Ancak, koleksiyonları Windows Çalışma Zamanı uygulama ikili arabiriminde (ABı) (örneğin, bir XAML denetimine veya bir JavaScript istemcisine) geri ve ileri geçirdiğinizde, Windows Çalışma Zamanı koleksiyon türlerini kullanmanız gerekir.

Windows Çalışma Zamanı koleksiyonlar ve ilgili türlerin arabirimlerini tanımlar ve C++/CX, koleksiyon. h üstbilgi dosyasında somut C++ uygulamalar sağlar. Bu çizimde, koleksiyon türleri arasındaki ilişkiler gösterilmektedir:

![Koleksiyon&#43;&#43;&#47;](../cppcx/media/cppcxcollectionsinheritancetree.png "türleri için&#43;c&#43;CX devralma ağacı için c cx&#47;") devralma ağacı

- [Platform:: Collections:: Vector sınıfı](../cppcx/platform-collections-vector-class.md) [std:: vector sınıfına](../standard-library/vector-class.md)benzer.

- [Platform:: Collections:: Map sınıf](../cppcx/platform-collections-map-class.md) sınıfı, [std:: Map sınıfına](../standard-library/map-class.md)benzer.

- [Platform:: Collections:: vectorview sınıfı](../cppcx/platform-collections-vectorview-class.md) ve[Platform:: Collections:: MapView Sınıfı](../cppcx/platform-collections-mapview-class.md) , ve ' `Vector` `Map`nin salt yazılır sürümleridir.

- Yineleyiciler [Platform:: Collections ad alanında](../cppcx/platform-collections-namespace.md)tanımlanmıştır. Bu yineleyiciler STL yineleyiciler için gereksinimleri karşılar ve herhangi bir [Windows:: Foundation:: Collections](/uwp/api/windows.foundation.collections) arabirim türü veya [Platform:: Collections](../cppcx/platform-collections-namespace.md) üzerinde [std:: Find](../standard-library/algorithm-functions.md#find), [std:: count_if](../standard-library/algorithm-functions.md#count_if)ve diğer stl algoritmalarının kullanılmasını sağlar somut tür. Örneğin, bu, içinde C# oluşturulan bir Windows çalışma zamanı bileşeninde bir koleksiyonu yineleyebilir ve kendısıne bir STL algoritması uygulayabilir.

   > [!IMPORTANT]
   > Proxy yineleyiciler `VectorIterator` ve `VectorViewIterator` IBU nesneleri `VectoryProxy<T>` `ArrowProxy<T>` kullanır ve STL kapsayıcılarıyla kullanımı etkinleştirir. Daha fazla bilgi için bu makalenin devamındaki "VectorProxy öğeleri" başlığına bakın.

- C++/CX koleksiyon TÜRLERI, STL kapsayıcılarının desteklediği iş parçacığı güvenliği garantisi destekler.

- [Windows:: Foundation:: Collections:: IObservableVector](/uwp/api/Windows.Foundation.Collections.IObservableVector_T_) ve [Windows:: Foundation:: Collections:: ıobservablemap](/uwp/api/Windows.Foundation.Collections.IObservableMap_K_V_) , koleksiyon çeşitli şekillerde değiştiğinde harekete geçirilen olayları tanımlar. Bu arabirimleri uygulayarak [Platform:: Collections:: Map](../cppcx/platform-collections-map-class.md) ve [Platform:: Collections:: vector](../cppcx/platform-collections-vector-class.md) ' ı xaml koleksiyonlarıyla veri bağlamayı destekler. Örneğin, bir öğesine veri bağlamış `Vector` `Grid`bir öğesi varsa, bir koleksiyona bir öğe eklediğinizde, değişiklik kılavuz Kullanıcı arabirimine yansıtılır.

## <a name="vector-usage"></a>Vektör kullanımı

Sınıfınız bir dizi kapsayıcısını başka bir Windows çalışma zamanı bileşenine iletmeniz gerektiğinde, [Windows:: Foundation:: Collections:: IVector\<t,](/uwp/api/Windows.Foundation.Collections.IVector_T_) parametre veya dönüş türü olarak > ve [Platform:: Collections::\<vector t](../cppcx/platform-collections-vector-class.md) , somut uygulama olarak >. Ortak dönüş değeri veya parametresinde bir `Vector` tür kullanmaya çalışırsanız, derleyici hatası C3986 tetiklenir. `Vector` Öğesini`IVector`olarak değiştirerek hatayı çözebilirsiniz.

> [!IMPORTANT]
> Kendi programınız dahilinde bir sıra geçirçalışıyorsanız, veya `Vector` `std::vector` ' den `IVector`daha verimli olduklarından, ya da kullanın. Yalnızca `IVector` kapsayıcıyı ABI arasında geçirdiğinizde kullanın.
>
> Windows çalışma zamanı tür sistemi pürüzlü Diziler kavramını desteklemez ve bu nedenle bir IVector < Platform:: array\<T > > bir dönüş değeri veya yöntem parametresi olarak geçirilemez. ABı arasında pürüzlü bir diziyi veya dizi dizilerini geçirmek için kullanın `IVector<IVector<T>^>`.

`Vector<T>`koleksiyondaki öğeleri eklemek, kaldırmak ve bunlara erişmek için gerekli olan ve örtülü olarak dönüştürülebilir `IVector<T>`olan yöntemleri sağlar. Ayrıca, örnekleri `Vector<T>`üzerinde stl algoritmaları da kullanabilirsiniz. Aşağıdaki örnekte, bazı temel kullanımlar gösterilmektedir. `std` Burada [BEGIN Function](../cppcx/begin-function.md) ve [End işlevi](../cppcx/end-function.md) ad alanından değil, adalanı.`Platform::Collections`

[!code-cpp[cx_collections#01](../cppcx/codesnippet/CPP/collections/class1.cpp#01)]

Tarafından kullanılan `std::vector` ve bir Windows çalışma zamanı bileşende yeniden kullanmak istediğiniz bir kodunuz varsa, bunu geçirdiğiniz noktada oluşturmak `Vector` için bir `std::vector` veya çift yineleyicisini alan `Vector` oluşturuculardan birini kullanmanız yeterlidir. ABı genelinde koleksiyon. Aşağıdaki örnek, ' `Vector` `std::vector`dan etkin başlatma için taşıma oluşturucusunun nasıl kullanılacağını gösterir. Taşıma işleminden sonra, özgün `vec` değişken artık geçerli değildir.

[!code-cpp[cx_collections#02](../cppcx/codesnippet/CPP/collections/class1.cpp#02)]

Daha sonraki bir noktada ABI üzerinde geçiş yapmanız gereken dizelerin vektörüne sahipseniz, dizeleri başlangıçta `std::wstring` tür `Platform::String^` veya tür olarak oluşturmaya karar vermelisiniz. Dizelerde çok sayıda işlem yapmanız gerekiyorsa kullanın `wstring`. Aksi takdirde, dizeleri türler olarak `Platform::String^` oluşturun ve daha sonra dönüştürme maliyetinden kaçının. Ayrıca, bu dizeleri bir `std:vector` veya `Platform::Collections::Vector` dahili olarak mı yerleştireceğinize karar vermelisiniz. Genel bir uygulama olarak, öğesini `std::vector` kullanın ve ardından yalnızca `Platform::Vector` kapsayıcıyı ABI arasında geçirdiğinizde bir oluşturun.

## <a name="value-types-in-vector"></a>Vektördeki değer türleri

[Platform:: Collections:: vector](../cppcx/platform-collections-vector-class.md) içinde depolanacak herhangi bir öğe, örtük olarak veya sağladığınız özel bir [std:: equal_to](../standard-library/equal-to-struct.md) karşılaştırıcısı kullanarak eşitlik karşılaştırmayı desteklemelidir. Tüm başvuru türleri ve tüm skaler türler, eşitlik karşılaştırmaları örtülü olarak destekler. [Windows:: Foundation::D atetime](/uwp/api/windows.foundation.datetime)gibi skalar olmayan değer türleri için veya özel karşılaştırmalar için — örneğin, `objA->UniqueID == objB->UniqueID`— özel bir işlev nesnesi sağlamanız gerekir.

## <a name="vectorproxy-elements"></a>VectorProxy öğeleri

[Platform:: Collections:: vectorterator](../cppcx/platform-collections-vectoriterator-class.md) ve [Platform:: Collections:: vectorviewwiterator](../cppcx/platform-collections-vectorviewiterator-class.md) `range for` , bir [IVector\<T >](/uwp/api/Windows.Foundation.Collections.IVector_T_) kapsayıcısı ile [std:: Sort](../standard-library/algorithm-functions.md#sort) gibi döngüler ve algoritmaların kullanımını etkinleştirir. Ancak `IVector` öğe, işaretçi başvurusu aracılığıyla C++ erişilemez; yalnızca [GetAt](/uwp/api/windows.foundation.collections.ivector-1.getat) ve [SetAt](/uwp/api/windows.foundation.collections.ivector-1.setat) yöntemleri aracılığıyla erişilebilir. Bu nedenle, bu yineleyiciler ara sunucu sınıflarını `Platform::Details::VectorProxy<T>` kullanır `Platform::Details::ArrowProxy<T>` ve standart kitaplığın gerektirdiği şekilde,, ve __\*__  __\[]__ işleçleriyle tek tek öğelere __->__ erişim sağlar. ,,,, ' `IVector<Person^> vec` `VectorProxy<Person^>`Nin `*begin(vec)` türü olarak tamamen konuşulur. Ancak, proxy nesnesi neredeyse her zaman kodunuz için saydamdır. Bu proxy nesneleri yalnızca yineleyiciler tarafından iç kullanım için olduklarından belgelenmemiştir, ancak mekanizmanın nasıl çalıştığını öğrenmek faydalı olur.

`range for` Kapsayıcılar üzerinde `IVector` bir döngü kullandığınızda, yineleyici değişkeninin `VectorProxy` öğelere `auto&&` doğru bir şekilde bağlanması için öğesini kullanın. `VectoryProxy` Veya `auto` kullanıyorsanız,derleyiciuyarısıC4239oluşturulurveuyarı`auto&`metninde bahsedilir.

Aşağıdaki çizimde bir `range for` döngüsü `IVector<Person^>`gösterilmektedir. Yürütmenin 64. satırdaki kesme noktasında durdurulduğuna dikkat edin. **QuickWatch** penceresi, yineleyici değişkeninin `p` `m_v` aslında `VectorProxy<Person^>` ve `m_i` üye değişkenleri olduğunu gösterir. Ancak, bu değişkeni çağırdığınızda `GetType` , `Person` örneğe `p2`özdeş türü döndürür. Bu, hızlı bir şekilde, `VectorProxy` hata ayıklayıcı bazı derleyicihatalarını veya başka yerlerde görünebilse de `ArrowProxy` , genellikle açıkça kod yazmanız gerekmez.

![&#45;](../cppcx/media/vectorproxy-1.png "Kapsama dayalı aralıktaki&#45;döngü Vektörleştiricisi") tabanlı aralıktaki vectorproxy

Proxy nesnesi etrafında kod yazmanız gereken bir senaryo (örneğin, `dynamic_cast` `UIElement` öğe koleksiyonundaki belirli bir türün xaml nesnelerini ararken) öğeleri üzerinde gerçekleştirmeniz gerektiğinde. Bu durumda, önce öğeyi [Platform:: Object](../cppcx/platform-object-class.md)^ olarak atamalısınız ve sonra dinamik cast işlemini gerçekleştirmelisiniz:

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

Bu örnek, `Map` öğelerin nasıl ekleneceğini ve bir [Platform:: Collections:: Map](../cppcx/platform-collections-map-class.md)dosyasında nasıl görüneceğini gösterir ve ardından salt okunurdur [Windows:: Foundation:: Collections:: ımapview]/UWP/api/Windows.Foundation.Collections.IMapView_K_V_) olarak döndürülür türüyle.

[!code-cpp[cx_collections#04](../cppcx/codesnippet/CPP/collections/class1.cpp#04)]

Genel olarak, iç eşleme işlevselliği için, `std::map` türü performans nedenleriyle tercih edin. Kapsayıcıyı ABI arasında geçirmeniz gerekiyorsa, [std:: map](../standard-library/map-class.md) ' ten `Map` bir [Platform:: Collections:: Map](../cppcx/platform-collections-map-class.md) oluşturun ve bir [Windows:: Foundation:: Collections::](/uwp/api/Windows.Foundation.Collections.IMap_K_V_)Map olarak döndürün. Ortak dönüş değeri veya parametresinde bir `Map` tür kullanmaya çalışırsanız, derleyici hatası C3986 tetiklenir. `Map` Öğesini`IMap`olarak değiştirerek hatayı çözebilirsiniz. Bazı durumlarda — örneğin, çok sayıda arama veya ekleme gerçekleştirmeyin ve koleksiyonu ABI sıklıkla geçirdiğinize göre — bu, başlangıçtan itibaren kullanımı `Platform::Collections::Map` daha pahalı olabilir ve bunu dönüştürme maliyetinden kaçınabilirsiniz. `std::map`. Herhangi bir durumda, bu üç türün en az performansı olduğundan `IMap` , arama ve ekleme işlemlerini bir daha kullanmaktan kaçının. Yalnızca kapsayıcıyı `IMap` ABI üzerinden geçirdiğiniz noktada öğesine dönüştürün.

## <a name="value-types-in-map"></a>Eşlemedeki değer türleri

[Platform:: Collections:: Map](../cppcx/platform-collections-map-class.md) içindeki öğeler sıralanmıştır. İçinde `Map` depolanacak her öğe, örtük olarak veya sağladığınız özel bir [STL:: less](../standard-library/less-struct.md) karşılaştırıcısı kullanarak, katı zayıf sıralamaya sahip daha az karşılaştırmayı desteklemelidir. Skaler türler karşılaştırmayı örtülü olarak destekler. Gibi skaler olmayan değer türleri `Windows::Foundation::DateTime`için veya özel karşılaştırmalar için — örneğin, `objA->UniqueID < objB->UniqueID`— özel bir karşılaştırıcı sağlamanız gerekir.

## <a name="collection-types"></a>Koleksiyon türleri

Koleksiyonlar dört kategoriye ayrılır: değiştirilebilir sürümler ve dizi koleksiyonlarının ve ilişkilendirilebilir koleksiyonların salt okunurdur. Ayrıca, C++/CX koleksiyonlara erişimi basitleştiren üç Yineleyici sınıfı sağlayarak koleksiyonları geliştirir.

Değiştirilebilir bir koleksiyonun öğeleri değiştirilebilir, ancak *Görünüm*olarak bilinen bir salt okuma koleksiyonunun öğeleri yalnızca okunabilir. Platform:: [Collections:: vector](../cppcx/platform-collections-vector-class.md) veya[Platform:: Collections:: vectorview](../cppcx/platform-collections-vectorview-class.md) koleksiyonunun öğelerine bir yineleyici veya koleksiyonun [vector:: GetAt](../cppcx/platform-collections-vector-class.md#getat) ve bir dizin kullanılarak erişilebilir. İlişkilendirilebilir bir koleksiyonun öğelerine, koleksiyonun [map:: Lookup](../cppcx/platform-collections-map-class.md#lookup) ve bir anahtar kullanılarak erişilebilir.

[Platform::Collections::Map Sınıfı](../cppcx/platform-collections-map-class.md)<br/>
Değiştirilebilir, ilişkilendirilebilir bir koleksiyon. Eşleme öğeleri anahtar-değer çiftleridir. İlişkili değerini almak için bir anahtar aranıyor ve tüm anahtar-değer çiftlerine yineleme, her ikisi de desteklenir.

`Map`ve `MapView` üzerinde`<K, V, C = std::less<K>>`şablonlanır; bu nedenle, karşılaştırıcısı özelleştirebilirsiniz.  Ayrıca, `Vector` ve `VectorView` `<T, E = std::equal_to<T>>` davranışını`IndexOf()`özelleştirebilmeniz için üzerinde şablon oluşturulur. Bu, çoğunlukla değer yapılarında `Vector` ve `VectorView` için önemlidir. Örneğin, bir vektör\<Windows:: Foundation::D atetime > oluşturmak için, DateTime = = işlecini aşırı yükmediği için özel bir karşılaştırıcı sağlamanız gerekir.

[Platform::Collections::MapView Sınıfı](../cppcx/platform-collections-mapview-class.md)<br/>
Bir `Map`öğesinin salt okunurdur sürümü.

[Platform::Collections::Vector Sınıfı](../cppcx/platform-collections-vector-class.md)<br/>
Değiştirilebilir sıralı bir koleksiyon. `Vector<T>`Sabit zamanlı rasgele erişimi ve itfası sabit zamanlı [ekleme](../cppcx/platform-collections-vector-class.md#append) işlemlerini destekler.

[Platform::Collections::VectorView Sınıfı](../cppcx/platform-collections-vectorview-class.md)<br/>
Bir `Vector`öğesinin salt okunurdur sürümü.

[Platform::Collections::InputIterator Sınıfı](../cppcx/platform-collections-inputiterator-class.md)<br/>
STL giriş yineleyicisinin gereksinimlerini karşılayan bir STL Yineleyici.

[Platform::Collections::VectorIterator Sınıfı](../cppcx/platform-collections-vectoriterator-class.md)<br/>
STL kesilebilir bir rastgele erişim Yineleyici gereksinimini karşılayan bir STL Yineleyici.

[Platform::Collections::VectorViewIterator Sınıfı](../cppcx/platform-collections-vectorviewiterator-class.md)<br/>
STL `const` rastgele erişim yineleyicisinin gereksinimlerini karşılayan bir STL Yineleyici.

### <a name="begin-and-end-functions"></a>Begin () ve End () işlevleri

`Vector` `VectorView` `Map` `Windows::Foundation::Collections` /CX, STL 'den işlem ,`MapView`,,, ve rastgele nesneler kullanımını basitleştirmek için [Begin işlevinin](../cppcx/begin-function.md) ve [son işlevin](../cppcx/end-function.md) üye olmayan aşırı yüklerini destekler C++ lerdir.

Aşağıdaki tabloda, kullanılabilir yineleyiciler ve işlevler listelenmektedir.

|Yineleyiciler|İşlevler|
|---------------|---------------|
|[Platform:: Collections:: vectorterator\<T >](../cppcx/platform-collections-vectoriterator-class.md)<br /><br /> [(Windows:: Foundation:: Collections:: IVector\<T >](/uwp/api/Windows.Foundation.Collections.IVector_T_) ve int.)|[başlangıç](../cppcx/begin-function.md)/ [](../cppcx/end-function.md)bitişi([Windows:: Foundation:: Collections:: IVector\<T >](/uwp/api/Windows.Foundation.Collections.IVector_T_))|
|[Platform:: Collections:: vectorviewiterator\<T >](../cppcx/platform-collections-vectorviewiterator-class.md)<br /><br /> ( [Ivectorview\<T >](/uwp/api/Windows.Foundation.Collections.IVectorView_T_)^ ve Int iç olarak depolanır.)|[](../cppcx/begin-function.md)Başlangıç/ [bitişi](../cppcx/end-function.md) ([ıvectorview\<T >](/uwp/api/Windows.Foundation.Collections.IVectorView_T_)^)|
|[Platform:: Collections:: InputIterator\<T >](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> ( [Iyineleyici\<t >](/uwp/api/Windows.Foundation.Collections.IIterator_T_)^ ve t olarak depolar.)|[](../cppcx/begin-function.md)Başlangıç/ [bitişi](../cppcx/end-function.md) ([ıiterable\<>](/uwp/api/Windows.Foundation.Collections.IIterable_T_))|
|[Platform:: Collections:: InputIterator < IKeyValuePair\<K, V > ^ >](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> ( [Iyineleyici\<t >](/uwp/api/Windows.Foundation.Collections.IIterator_T_)^ ve t olarak depolar.)|[](../cppcx/begin-function.md)Başlangıç/ [bitişi](../cppcx/end-function.md) ([IMAPK\<, V >](/uwp/api/Windows.Foundation.Collections.IMap_K_V_).|
|[Platform:: Collections:: InputIterator < IKeyValuePair\<K, V > ^ >](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> ( [Iyineleyici\<t >](/uwp/api/Windows.Foundation.Collections.IIterator_T_)^ ve t olarak depolar.)|[](../cppcx/begin-function.md)Başlangıç/ [bitişi](../cppcx/end-function.md) ([Windows:: Foundation:: Collections:: ımapview]/UWP/api/Windows.Foundation.Collections.IMapView_K_V_))|

### <a name="collection-change-events"></a>Koleksiyon değişiklik olayları

`Vector`ve `Map` bir koleksiyon nesnesi değiştirildiğinde veya sıfırlandığında ya da bir koleksiyonun herhangi bir öğesi eklendiğinde, kaldırıldığında veya değiştirildiğinde oluşan olayları uygulayarak xaml koleksiyonlarında veri bağlamayı destekler. Veri bağlamayı destekleyen kendi türlerinizi yazabilirsiniz, ancak `Map` ya `Vector` da bu türlerin mühürlenmesi gerekir.

[Windows:: Foundation:: Collections:: VectorChangedEventHandler](/uwp/api/windows.foundation.collections.vectorchangedeventhandler) ve [Windows:: Foundation:: Collections:: MapChangedEventHandler](/uwp/api/windows.foundation.collections.mapchangedeventhandler) Delegates, koleksiyon değişiklik olayları için olay işleyicilerine yönelik imzaları belirler. [Windows:: Foundation:: Collections:: collectionchange](/uwp/api/windows.foundation.collections.collectionchange) public enum class ve `Platform::Collection::Details::MapChangedEventArgs` ve `Platform::Collections::Details::VectorChangedEventArgs` ref sınıfları, olaya neyin neden olduğunu belirlemek için olay bağımsız değişkenlerini depolar. `Details` `Map` Ya `*EventArgs` dakullandığınızda,türleriaçıkçaoluşturmakveyakullanmakzorundaolmadığınızdantürleradalanındatanımlanır.`Vector`

## <a name="see-also"></a>Ayrıca bkz.

[Tür Sistemi](../cppcx/type-system-c-cx.md)<br/>
[C++/CX Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad Alanları Başvurusu](../cppcx/namespaces-reference-c-cx.md)
