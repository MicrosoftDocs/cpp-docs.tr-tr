---
title: Koleksiyonlar (C++/CX)
ms.date: 11/19/2018
ms.assetid: 914da30b-aac5-4cd7-9da3-a5ac08cdd72c
ms.openlocfilehash: 84c6ecad5ffb4920972faf5aa564103ec1f5b5df
ms.sourcegitcommit: 65fead53d56d531d71be42216056aca5f44def11
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2020
ms.locfileid: "88610952"
---
# <a name="collections-ccx"></a>Koleksiyonlar (C++/CX)

Bir C++/CX programında Standart Şablon kitaplığı (STL) kapsayıcılarından veya başka bir Kullanıcı tanımlı koleksiyon türünden ücretsiz olarak kullanım sağlayabilirsiniz. Ancak, koleksiyonları Windows Çalışma Zamanı uygulama ikili arabiriminde (ABı) (örneğin, bir XAML denetimine veya bir JavaScript istemcisine) geri ve ileri geçirdiğinizde, Windows Çalışma Zamanı koleksiyon türlerini kullanmanız gerekir.

Windows Çalışma Zamanı koleksiyonlar ve ilgili türlerin arabirimlerini tanımlar ve C++/CX, koleksiyon. h üstbilgi dosyasında somut C++ uygulamaları sağlar. Bu çizimde, koleksiyon türleri arasındaki ilişkiler gösterilmektedir:

![Koleksiyon türleri için C&#43;&#43;&#47;CX devralma ağacı](../cppcx/media/cppcxcollectionsinheritancetree.png "Koleksiyon türleri için C&#43;&#43;&#47;CX devralma ağacı")

- [Platform:: Collections:: Vector sınıfı](../cppcx/platform-collections-vector-class.md) [std:: vector sınıfına](../standard-library/vector-class.md)benzer.

- [Platform:: Collections:: Map sınıf](../cppcx/platform-collections-map-class.md) sınıfı, [std:: Map sınıfına](../standard-library/map-class.md)benzer.

- [Platform:: Collections:: VectorView sınıfı](../cppcx/platform-collections-vectorview-class.md) ve[Platform:: Collections:: MapView Sınıfı](../cppcx/platform-collections-mapview-class.md) , ve ' nin salt yazılır `Vector` sürümleridir `Map` .

- Yineleyiciler [Platform:: Collections ad alanında](../cppcx/platform-collections-namespace.md)tanımlanmıştır. Bu yineleyiciler STL yineleyiciler için gereksinimleri karşılar ve herhangi bir [Windows:: Foundation:: Collections](/uwp/api/windows.foundation.collections) arabirim türü veya [Platform:: Collections](../cppcx/platform-collections-namespace.md) somut türü üzerinde [std:: find](../standard-library/algorithm-functions.md#find), [std:: count_if](../standard-library/algorithm-functions.md#count_if)ve diğer stl algoritmalarının kullanılmasını sağlar. Örneğin, bu, C# dilinde oluşturulmuş bir Windows Çalışma Zamanı bileşeninde bir koleksiyonu yineleyebilir ve buna bir STL algoritması uygulayabilirsiniz.

   > [!IMPORTANT]
   > Proxy yineleyiciler `VectorIterator` ve `VectorViewIterator` IBU nesneleri KULLANıR ve `VectoryProxy<T>` `ArrowProxy<T>` STL kapsayıcılarıyla kullanımı etkinleştirir. Daha fazla bilgi için bu makalenin devamındaki "VectorProxy öğeleri" başlığına bakın.

- C++/CX koleksiyon türleri, STL kapsayıcılarının desteklediği iş parçacığı güvenliği garantisi sağlar.

- [Windows:: Foundation:: Collections:: IObservableVector](/uwp/api/windows.foundation.collections.iobservablevector-1) ve [Windows:: Foundation:: Collections:: ıobservablemap](/uwp/api/windows.foundation.collections.iobservablemap-2) , koleksiyon çeşitli şekillerde değiştiğinde harekete geçirilen olayları tanımlar. Bu arabirimleri uygulayarak  [Platform:: Collections:: Map](../cppcx/platform-collections-map-class.md) ve [Platform:: Collections:: vector](../cppcx/platform-collections-vector-class.md) ' ı xaml koleksiyonlarıyla veri bağlamayı destekler. Örneğin, bir öğesine `Vector` veri bağlamış bir öğesi varsa, bir koleksiyona bir `Grid` öğe eklediğinizde, değişiklik kılavuz Kullanıcı arabirimine yansıtılır.

## <a name="vector-usage"></a>Vektör kullanımı

Sınıfınızın bir dizi kapsayıcısını başka bir Windows Çalışma Zamanı bileşenine geçirmesi gerektiğinde, parametre veya dönüş türü olarak [Windows:: Foundation:: Collections:: IVector \<T> ](/uwp/api/windows.foundation.collections.ivector-1) ve somut uygulama olarak [Platform:: Collections:: vector \<T> ](../cppcx/platform-collections-vector-class.md) kullanın. `Vector`Ortak dönüş değeri veya parametresinde bir tür kullanmaya çalışırsanız, derleyici hatası C3986 tetiklenir. Öğesini olarak değiştirerek hatayı çözebilirsiniz `Vector` `IVector` .

> [!IMPORTANT]
> Kendi programınız dahilinde bir sıra geçirçalışıyorsanız, `Vector` veya ' `std::vector` den daha verimli olduklarından, ya da kullanın `IVector` . `IVector`Yalnızca KAPSAYıCıYı ABI arasında geçirdiğinizde kullanın.
>
> Windows Çalışma Zamanı tür sistemi, pürüzlü Diziler kavramını desteklemez ve bu nedenle bir `IVector<Platform::Array<T>>` dönüş değeri veya yöntem parametresi olarak geçirilemez. ABı arasında pürüzlü bir diziyi veya dizi dizilerini geçirmek için kullanın `IVector<IVector<T>^>` .

`Vector<T>` koleksiyondaki öğeleri eklemek, kaldırmak ve bunlara erişmek için gerekli olan ve örtülü olarak dönüştürülebilir olan yöntemleri sağlar `IVector<T>` . Ayrıca, örnekleri üzerinde STL algoritmaları da kullanabilirsiniz `Vector<T>` . Aşağıdaki örnekte, bazı temel kullanımlar gösterilmektedir. Burada [BEGIN Function](../cppcx/begin-function.md) ve [End işlevi](../cppcx/end-function.md) `Platform::Collections` ad alanından değil, ad alanı `std` .

[!code-cpp[cx_collections#01](../cppcx/codesnippet/CPP/collections/class1.cpp#01)]

`std::vector`' İ kullanan ve bir Windows çalışma zamanı bileşende yeniden kullanmak istediğiniz bir kodunuz varsa, `Vector` `std::vector` `Vector` koleksiyonu ABI arasında geçirdiğiniz noktada oluşturmak için bir veya çift yineleyiciler alan oluşturuculardan birini kullanmanız yeterlidir. Aşağıdaki örnek, ' `Vector` dan etkin başlatma için taşıma oluşturucusunun nasıl kullanılacağını gösterir `std::vector` . Taşıma işleminden sonra, özgün `vec` değişken artık geçerli değildir.

[!code-cpp[cx_collections#02](../cppcx/codesnippet/CPP/collections/class1.cpp#02)]

Daha sonraki bir noktada ABı üzerinde geçiş yapmanız gereken dizelerin vektörüne sahipseniz, dizeleri başlangıçta tür veya tür olarak oluşturmaya karar vermelisiniz `std::wstring` `Platform::String^` . Dizelerde çok sayıda işlem yapmanız gerekiyorsa kullanın `wstring` . Aksi takdirde, dizeleri türler olarak oluşturun `Platform::String^` ve daha sonra dönüştürme maliyetinden kaçının. Ayrıca, bu dizeleri bir `std:vector` veya dahili olarak mı yerleştireceğinize karar vermelisiniz `Platform::Collections::Vector` . Genel bir uygulama olarak, `std::vector` öğesini kullanın ve ardından `Platform::Vector` yalnızca kapsayıcıyı ABI arasında geçirdiğinizde bir oluşturun.

## <a name="value-types-in-vector"></a>Vektördeki değer türleri

[Platform:: Collections:: vector](../cppcx/platform-collections-vector-class.md) ' de depolanacak herhangi bir öğe, örtük olarak veya sağladığınız özel bir [std:: equal_to](../standard-library/equal-to-struct.md) karşılaştırıcı kullanarak eşitlik karşılaştırmayı desteklemelidir. Tüm başvuru türleri ve tüm skaler türler, eşitlik karşılaştırmaları örtülü olarak destekler. [Windows:: Foundation::D ateTime](/uwp/api/windows.foundation.datetime)gibi skalar olmayan değer türleri için veya özel karşılaştırmalar için — örneğin, `objA->UniqueID == objB->UniqueID` — özel bir işlev nesnesi sağlamanız gerekir.

## <a name="vectorproxy-elements"></a>VectorProxy öğeleri

[Platform:: Collections](../cppcx/platform-collections-vectoriterator-class.md) :: [Vectorterator ve platform:: Collections:: VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md) , `range for` bir [IVector \<T> ](/uwp/api/windows.foundation.collections.ivector-1) kapsayıcısı ile [std:: Sort](../standard-library/algorithm-functions.md#sort) gibi döngüler ve algoritmaların kullanımını etkinleştirir. Ancak, `IVector` C++ işaretçi başvurusu aracılığıyla öğelere erişilemez; yalnızca [GetAt](/uwp/api/windows.foundation.collections.ivector-1.getat) ve [SetAt](/uwp/api/windows.foundation.collections.ivector-1.setat) yöntemleri aracılığıyla erişilebilir. Bu nedenle, bu yineleyiciler ara sunucu sınıflarını kullanır `Platform::Details::VectorProxy<T>` ve `Platform::Details::ArrowProxy<T>` __\*__ __->__ Standart kitaplığın gerektirdiği şekilde,, ve __ \[ ]__ işleçleriyle tek tek öğelere erişim sağlar. ,,,, ' `IVector<Person^> vec` Nin türü olarak tamamen `*begin(vec)` konuşulur `VectorProxy<Person^>` . Ancak, proxy nesnesi neredeyse her zaman kodunuz için saydamdır. Bu proxy nesneleri yalnızca yineleyiciler tarafından iç kullanım için olduklarından belgelenmemiştir, ancak mekanizmanın nasıl çalıştığını öğrenmek faydalı olur.

`range for`Kapsayıcılar üzerinde bir döngü kullandığınızda `IVector` , `auto&&` Yineleyici değişkeninin öğelere doğru bir şekilde bağlanması için öğesini kullanın `VectorProxy` . **`auto`** Veya kullanıyorsanız `auto&` , derleyici uyarısı C4239 oluşturulur ve `VectoryProxy` Uyarı metninde bahsedilir.

Aşağıdaki çizimde bir döngüsü gösterilmektedir `range for` `IVector<Person^>` . Yürütmenin 64. satırdaki kesme noktasında durdurulduğuna dikkat edin. **QuickWatch** penceresi, yineleyici değişkeninin `p` aslında `VectorProxy<Person^>` `m_v` ve `m_i` üye değişkenleri olduğunu gösterir. Ancak, `GetType` Bu değişkeni çağırdığınızda, örneğe özdeş türü döndürür `Person` `p2` . Bu, `VectorProxy` `ArrowProxy` **hızlı**bir şekilde, hata ayıklayıcı bazı derleyici hatalarını veya başka yerlerde görünebilse de, genellikle açıkça kod yazmanız gerekmez.

![Döngüye göre&#45;Vektörtorproxy](../cppcx/media/vectorproxy-1.png "Döngüye göre&#45;Vektörtorproxy")

Proxy nesnesi etrafında kod yazmanız gereken bir senaryo **`dynamic_cast`** (örneğin, öğe koleksiyonundaki belirli bir TÜRÜN xaml nesnelerini ararken) öğeleri üzerinde gerçekleştirmeniz gerektiğinde `UIElement` . Bu durumda, önce öğeyi [Platform:: Object](../cppcx/platform-object-class.md)^ olarak atamalısınız ve sonra dinamik cast işlemini gerçekleştirmelisiniz:

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

Bu örnek, öğelerin nasıl ekleneceğini ve bir [Platform:: Collections:: Map](../cppcx/platform-collections-map-class.md)dosyasında nasıl görüneceğini gösterir ve ardından `Map` bir salt okunurdur [Windows:: Foundation:: Collections:: ımapview](/uwp/api/windows.foundation.collections.imapview-2) türü olarak döndürülür.

[!code-cpp[cx_collections#04](../cppcx/codesnippet/CPP/collections/class1.cpp#04)]

Genel olarak, iç eşleme işlevselliği için, `std::map` türü performans nedenleriyle tercih edin. Kapsayıcıyı ABı arasında geçirmeniz gerekiyorsa, [std:: map](../standard-library/map-class.md) ' ten bir [Platform:: Collections:: Map](../cppcx/platform-collections-map-class.md) oluşturun ve `Map` bir [Windows:: Foundation:: Collections::](/uwp/api/windows.foundation.collections.imap-2)Map olarak döndürün. `Map`Ortak dönüş değeri veya parametresinde bir tür kullanmaya çalışırsanız, derleyici hatası C3986 tetiklenir. Öğesini olarak değiştirerek hatayı çözebilirsiniz `Map` `IMap` . Bazı durumlarda — örneğin, çok sayıda arama veya ekleme gerçekleştirmeyin ve koleksiyonu ABı sıklıkla geçirdiğinize göre — bu, baştan itibaren kullanımı daha pahalı olabilir `Platform::Collections::Map` ve dönüştürme maliyetinden kaçınabilirsiniz `std::map` . Herhangi bir durumda, `IMap` Bu üç türün en az performansı olduğundan, arama ve ekleme işlemlerini bir daha kullanmaktan kaçının. `IMap`Yalnızca KAPSAYıCıYı ABI üzerinden geçirdiğiniz noktada öğesine dönüştürün.

## <a name="value-types-in-map"></a>Eşlemedeki değer türleri

[Platform:: Collections:: Map](../cppcx/platform-collections-map-class.md) içindeki öğeler sıralanmıştır. İçinde depolanacak her öğe `Map` , örtük olarak veya sağladığınız özel bir [STL:: less](../standard-library/less-struct.md) karşılaştırıcısı kullanarak, katı zayıf sıralamaya sahip daha az karşılaştırmayı desteklemelidir. Skaler türler karşılaştırmayı örtülü olarak destekler. Gibi skaler olmayan değer türleri için `Windows::Foundation::DateTime` veya özel karşılaştırmalar için — örneğin, `objA->UniqueID < objB->UniqueID` — özel bir karşılaştırıcı sağlamanız gerekir.

## <a name="collection-types"></a>Koleksiyon türleri

Koleksiyonlar dört kategoriye ayrılır: değiştirilebilir sürümler ve dizi koleksiyonlarının ve ilişkilendirilebilir koleksiyonların salt okunurdur. Ayrıca, C++/CX, koleksiyonlara erişimi basitleştiren üç Yineleyici sınıfı sağlayarak koleksiyonları geliştirir.

Değiştirilebilir bir koleksiyonun öğeleri değiştirilebilir, ancak *Görünüm*olarak bilinen bir salt okuma koleksiyonunun öğeleri yalnızca okunabilir. Platform:: [Collections:: vector](../cppcx/platform-collections-vector-class.md) veya[Platform:: Collections:: vectorview](../cppcx/platform-collections-vectorview-class.md) koleksiyonunun öğelerine bir yineleyici veya koleksiyonun [vector:: GetAt](../cppcx/platform-collections-vector-class.md#getat) ve bir dizin kullanılarak erişilebilir. İlişkilendirilebilir bir koleksiyonun öğelerine, koleksiyonun [map:: Lookup](../cppcx/platform-collections-map-class.md#lookup) ve bir anahtar kullanılarak erişilebilir.

[Platform:: Collections:: Map sınıfı](../cppcx/platform-collections-map-class.md)<br/>
Değiştirilebilir, ilişkilendirilebilir bir koleksiyon. Eşleme öğeleri anahtar-değer çiftleridir. İlişkili değerini almak için bir anahtar aranıyor ve tüm anahtar-değer çiftlerine yineleme, her ikisi de desteklenir.

`Map` ve `MapView` üzerinde şablonlanır `<K, V, C = std::less<K>>` ; Bu nedenle, karşılaştırıcısı özelleştirebilirsiniz.  Ayrıca, `Vector` ve `VectorView` davranışını özelleştirebilmeniz için üzerinde şablon oluşturulur `<T, E = std::equal_to<T>>` `IndexOf()` . Bu, çoğunlukla `Vector` değer yapılarında ve için önemlidir `VectorView` . Örneğin, bir vektör oluşturmak için \<Windows::Foundation::DateTime> , DateTime = = işlecini aşırı yükmediği için özel bir karşılaştırıcı sağlamanız gerekir.

[Platform:: Collections:: MapView Sınıfı](../cppcx/platform-collections-mapview-class.md)<br/>
Bir öğesinin salt okunurdur sürümü `Map` .

[Platform:: Collections:: vector Sınıfı](../cppcx/platform-collections-vector-class.md)<br/>
Değiştirilebilir sıralı bir koleksiyon. `Vector<T>` Sabit zamanlı rasgele erişimi ve itfası sabit zamanlı [ekleme](../cppcx/platform-collections-vector-class.md#append) işlemlerini destekler.

[Platform:: Collections:: VectorView sınıfı](../cppcx/platform-collections-vectorview-class.md)<br/>
Bir öğesinin salt okunurdur sürümü `Vector` .

[Platform:: Collections:: InputIterator sınıfı](../cppcx/platform-collections-inputiterator-class.md)<br/>
STL giriş yineleyicisinin gereksinimlerini karşılayan bir STL Yineleyici.

[Platform:: Collections:: Vectorterator sınıfı](../cppcx/platform-collections-vectoriterator-class.md)<br/>
STL kesilebilir bir rastgele erişim Yineleyici gereksinimini karşılayan bir STL Yineleyici.

[Platform:: Collections:: Vectorviewwiterator sınıfı](../cppcx/platform-collections-vectorviewiterator-class.md)<br/>
STL rastgele erişim yineleyicisinin gereksinimlerini karşılayan bir STL Yineleyici  **`const`** .

### <a name="begin-and-end-functions"></a>Begin () ve End () işlevleri

C++/CX, STL 'nin işlem,,, `Vector` `VectorView` `Map` ve rastgele nesnelerin kullanımını basitleştirmek amacıyla `MapView` `Windows::Foundation::Collections` [BEGIN Function](../cppcx/begin-function.md) ve [End Function](../cppcx/end-function.md) üye olmayan işlevlerin aşırı yüklerini destekler.

Aşağıdaki tabloda, kullanılabilir yineleyiciler ve işlevler listelenmektedir.

|Yineleyiciler|İşlevler|
|---------------|---------------|
|[Platform:: Collections:: Vectorterator\<T>](../cppcx/platform-collections-vectoriterator-class.md)<br /><br /> ( [Windows:: Foundation:: Collections:: IVector \<T> ](/uwp/api/windows.foundation.collections.ivector-1) ve Int ile dahili olarak depolanır.)|[Başlangıç](../cppcx/begin-function.md) /  [End](../cppcx/end-function.md)([Windows:: Foundation:: Collections:: IVector \<T> ](/uwp/api/windows.foundation.collections.ivector-1))|
|[Platform:: Collections:: Vectorviewwiterator\<T>](../cppcx/platform-collections-vectorviewiterator-class.md)<br /><br /> ( [Ivectorview \<T> ](/uwp/api/windows.foundation.collections.ivectorview-1)^ ve int 'i dahili olarak depolar.)|[Başlangıç](../cppcx/begin-function.md) /  [End](../cppcx/end-function.md) ([ıvectorview \<T> ](/uwp/api/windows.foundation.collections.ivectorview-1)^)|
|[Platform:: Collections:: InputIterator\<T>](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> ( [Iyineleyici \<T> ](/uwp/api/windows.foundation.collections.iiterator-1)^ ve T 'yi dahili olarak depolar.)|[Başlangıç](../cppcx/begin-function.md) /  [son](../cppcx/end-function.md) ([ıiterable \<T> ](/uwp/api/windows.foundation.collections.iiterable-1))|
|[Platform:: Collections:: InputIterator<IKeyValuePair\<K, V>^>](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> ( [Iyineleyici \<T> ](/uwp/api/windows.foundation.collections.iiterator-1)^ ve T 'yi dahili olarak depolar.)|[Başlangıç](../cppcx/begin-function.md) /  [End](../cppcx/end-function.md) ([IMAP \<K,V> ](/uwp/api/windows.foundation.collections.imap-2).|
|[Platform:: Collections:: InputIterator<IKeyValuePair\<K, V>^>](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> ( [Iyineleyici \<T> ](/uwp/api/windows.foundation.collections.iiterator-1)^ ve T 'yi dahili olarak depolar.)|[Başlangıç](../cppcx/begin-function.md) /  [End](../cppcx/end-function.md) ([Windows:: Foundation:: Collections:: ımapview](/uwp/api/windows.foundation.collections.imapview-2))|

### <a name="collection-change-events"></a>Koleksiyon değişiklik olayları

`Vector` ve `Map` bir koleksiyon nesnesi değiştirildiğinde veya sıfırlandığında ya da bir koleksiyonun herhangi bir öğesi eklendiğinde, kaldırıldığında veya değiştirildiğinde oluşan olayları uygulayarak xaml koleksiyonlarında veri bağlamayı destekler. Veri bağlamayı destekleyen kendi türlerinizi yazabilirsiniz, ancak `Map` ya da `Vector` Bu türlerin mühürlenmesi gerekir.

[Windows:: Foundation:: Collections:: VectorChangedEventHandler](/uwp/api/windows.foundation.collections.vectorchangedeventhandler-1) ve [Windows:: Foundation:: Collections:: MapChangedEventHandler](/uwp/api/windows.foundation.collections.mapchangedeventhandler-2) Delegates, koleksiyon değişiklik olayları için olay işleyicilerine yönelik imzaları belirler. [Windows:: Foundation:: Collections:: CollectionChange](/uwp/api/windows.foundation.collections.collectionchange) public enum class ve `Platform::Collection::Details::MapChangedEventArgs` ve `Platform::Collections::Details::VectorChangedEventArgs` ref sınıfları, olaya neyin neden olduğunu belirlemek için olay bağımsız değişkenlerini depolar. `*EventArgs`Ya da kullandığınızda, türleri `Details` açıkça oluşturmak veya kullanmak zorunda olmadığınızdan türler ad alanında tanımlanır `Map` `Vector` .

## <a name="see-also"></a>Ayrıca bkz.

[Tür sistemi](../cppcx/type-system-c-cx.md)<br/>
[C++/CX dil başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad alanı başvurusu](../cppcx/namespaces-reference-c-cx.md)
