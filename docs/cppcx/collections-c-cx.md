---
title: Koleksiyonlar (C++/CX)
ms.date: 11/19/2018
ms.assetid: 914da30b-aac5-4cd7-9da3-a5ac08cdd72c
ms.openlocfilehash: 59e73b803a0878e88361c7fe75cff556b8eeedcd
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032323"
---
# <a name="collections-ccx"></a>Koleksiyonlar (C++/CX)

Bir C++/CX programında, Standart Şablon Kitaplığı (STL) kapsayıcılarından veya kullanıcı tarafından tanımlanan diğer koleksiyon türlerinden ücretsiz olarak yararlanabilirsiniz. Ancak, koleksiyonları Windows Runtime uygulama ikili arabirimi (ABI)-örneğin, bir XAML denetimine veya bir JavaScript istemcisine aktardığınızda-Windows Runtime toplama türlerini kullanmanız gerekir.

Windows Runtime koleksiyonları ve ilgili türleri için arabirimleri tanımlar ve C++/CX collection.h üstbilgi dosyasında somut C++ uygulamalarını sağlar. Bu resimde koleksiyon türleri arasındaki ilişkileri gösterir:

![Toplama türleri için C&#43;&#43;&#47;CX devralma ağacı](../cppcx/media/cppcxcollectionsinheritancetree.png "Toplama türleri için C&#43;&#43;&#47;CX devralma ağacı")

- [Platform::Koleksiyonlar::Vektör sınıfı](../cppcx/platform-collections-vector-class.md) [std benzer::vektör sınıfı](../standard-library/vector-class.md).

- [Platform::Koleksiyonlar::Harita Sınıfı](../cppcx/platform-collections-map-class.md) [std benzer::harita sınıfı](../standard-library/map-class.md).

- [Platform::Koleksiyonlar::VectorView Sınıfı](../cppcx/platform-collections-vectorview-class.md) ve[Platformu::Koleksiyonlar::MapView Sınıfı](../cppcx/platform-collections-mapview-class.md) yalnızca `Vector` `Map`okunan sürümlerdir ve .

- Yineleyiciler [Platform'da tanımlanır::Koleksiyonlar Ad Alanı.](../cppcx/platform-collections-namespace.md) Bu yineleyiciler STL yineleyiciler için gereksinimleri karşılamak ve std kullanımını [etkinleştirmek::bul,](../standard-library/algorithm-functions.md#find) [std::count_if](../standard-library/algorithm-functions.md#count_if), ve diğer STL algoritmaları herhangi bir [Windows::Foundation::Collections](/uwp/api/windows.foundation.collections) arayüz türü veya [Platform::Koleksiyonlar](../cppcx/platform-collections-namespace.md) beton türü. Örneğin, bu, C# 'da oluşturulan bir Windows Runtime bileşeninde bir koleksiyonu yineleyebilir ve ona bir STL algoritması uygulayabilirsiniz anlamına gelir.

   > [!IMPORTANT]
   > Proxy `VectorIterator` yineleyiciler `VectorViewIterator` ve proxy `VectoryProxy<T>` nesneleri `ArrowProxy<T>` kullanmak ve STL kapsayıcıları ile kullanımını etkinleştirmek için. Daha fazla bilgi için bu makalenin ilerleyen saatlerinde "VectorProxy öğeleri"ne bakın.

- C++/CX toplama türleri, STL kapsayıcılarının desteklediği aynı iş parçacığı güvenliğini destekler.

- [Windows::Foundation::Collections::IObservableVector](/uwp/api/windows.foundation.collections.iobservablevector-1) ve [Windows::Foundation::Collections::IObservableMap,](/uwp/api/windows.foundation.collections.iobservablemap-2) koleksiyon çeşitli şekillerde değiştiğinde açılan olayları tanımlar. Bu arabirimleri uygulayarak, [Platform::Koleksiyonlar::Harita](../cppcx/platform-collections-map-class.md) ve [Platform::Koleksiyonlar::Vektör](../cppcx/platform-collections-vector-class.md) desteği XAML koleksiyonları ile veri bağlama. Örneğin, bir koleksiyona `Vector` bir öğe eklediğinizde `Grid`bir veriye bağlı bir veriniz varsa, değişiklik Grid UI'ye yansıtılır.

## <a name="vector-usage"></a>Vektör kullanımı

Sınıfınızın bir sıra kapsayıcısını başka bir Windows Runtime bileşenine geçirmesi gerektiğinde, [Windows:Foundation::Collections:: IVector\<T](/uwp/api/windows.foundation.collections.ivector-1) parametre veya dönüş türü olarak>ve [Platform::Koleksiyonlar::Vektör\<T>](../cppcx/platform-collections-vector-class.md) somut uygulama olarak kullanın. Ortak iade değeri `Vector` veya parametrebir tür kullanmaya çalışırsanız, derleyici hatası C3986 yükseltilir. Bir `IVector`' ye değiştirerek `Vector` hatayı düzeltebilirsiniz.

> [!IMPORTANT]
> Kendi programınızda bir sıra geçiyorsanız, o `Vector` `std::vector` zaman ya da `IVector`daha verimli oldukları için kullanın. Yalnızca `IVector` konteynırı ABI'nin diğer tarafına geçirirken kullanın.
>
> Windows Runtime türü sistemi pürüzlü diziler kavramını desteklemez ve bu nedenle bir\<IVector<Platformu geçemez::Array T>> bir dönüş değeri veya yöntem parametresi olarak. Pürüzlü bir dizi veya ABI genelinde diziler `IVector<IVector<T>^>`dizisi geçmek için.

`Vector<T>`koleksiyondaki öğeleri eklemek, kaldırmak ve bunlara erişmek için gerekli olan yöntemleri sağlar ve `IVector<T>`dolaylı olarak .'e dönüştürülebilir. STL algoritmalarını `Vector<T>`da . Aşağıdaki örnek, bazı temel kullanımı göstermektedir. Buradaki [başlangıç işlevi](../cppcx/begin-function.md) ve bitiş `Platform::Collections` `std` [işlevi](../cppcx/end-function.md) ad alanından değil, ad alanından dır.

[!code-cpp[cx_collections#01](../cppcx/codesnippet/CPP/collections/class1.cpp#01)]

Windows Runtime bileşeninde `std::vector` kullanan varolan kodunuz varsa ve bunu yeniden kullanmak `Vector` istiyorsanız, koleksiyonu ABI'den geçtiğiniz noktada bir `std::vector` `Vector` kod oluşturmak için bir veya bir çift yineleyici alan oluşturuculardan birini kullanmanız gerekir. Aşağıdaki örnekte, `Vector` bir `std::vector`'den verimli bir şekilde başlatma için hareket oluşturucusu nasıl kullanılacağı gösterilmektedir. Taşıma işleminden sonra, `vec` özgün değişken artık geçerli değildir.

[!code-cpp[cx_collections#02](../cppcx/codesnippet/CPP/collections/class1.cpp#02)]

İleride ABI üzerinden geçmeniz gereken bir dize vektörünvarsa, dizeleri başlangıçta tür olarak `std::wstring` mı yoksa `Platform::String^` tür olarak mı oluşturacağına karar vermelisiniz. Dizeleri üzerinde işleme bir sürü yapmak zorunda, `wstring`o zaman kullanın. Aksi takdirde, dizeleri `Platform::String^` türleri olarak oluşturun ve daha sonra dönüştürme maliyetini önlemek. Ayrıca, bu dizeleri bir `std:vector` veya `Platform::Collections::Vector` dahili içine koymak için karar vermelidir. Genel bir uygulama `std::vector` olarak, kullanın `Platform::Vector` ve sonra sadece ABI üzerinden konteyner geçtiğınızda ondan bir oluşturun.

## <a name="value-types-in-vector"></a>Vektör'deki değer türleri

Platformda depolanacak herhangi bir [öğe::Koleksiyonlar::Vektör,](../cppcx/platform-collections-vector-class.md) dolaylı olarak veya sağladığınız özel bir std kullanarak eşitlik karşılaştırmasını [desteklemelidir::equal_to](../standard-library/equal-to-struct.md) karşılaştırıcı. Tüm başvuru türleri ve tüm skaler türleri dolaylı olarak eşitlik karşılaştırmalarını destekler. [Windows:Foundation::DateTime](/uwp/api/windows.foundation.datetime)gibi skaler olmayan değer türleri için veya özel karşılaştırmalar `objA->UniqueID == objB->UniqueID`için -örneğin- özel bir işlev nesnesi sağlamanız gerekir.

## <a name="vectorproxy-elements"></a>VectorProxy elemanları

[Platform::Koleksiyonlar::VectorIterator](../cppcx/platform-collections-vectoriterator-class.md) ve [Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md) std gibi `range for` döngülerin ve algoritmaların kullanımını etkinleştirin::iVector [\<T>](/uwp/api/windows.foundation.collections.ivector-1) kapsayıcıile [sıralayın.](../standard-library/algorithm-functions.md#sort) Ancak `IVector` c++ işaretçisi dereference ile öğelere erişilemez; yalnızca [GetAt](/uwp/api/windows.foundation.collections.ivector-1.getat) ve [SetAt](/uwp/api/windows.foundation.collections.ivector-1.setat) yöntemleri ile erişilebilirler. Bu nedenle, bu yineleyiciler `Platform::Details::VectorProxy<T>` `Platform::Details::ArrowProxy<T>` proxy sınıflarını kullanır ve __\*__ __->__ Standart Kitaplık tarafından gerekli olduğu gibi , , ve __ \[]__ işleçleri aracılığıyla tek tek öğelere erişim sağlamak için. Açıkçası, verilen `IVector<Person^> vec`bir , `*begin(vec)` `VectorProxy<Person^>`türüdür . Ancak, proxy nesnesi hemen hemen her zaman kodunuzda saydamdır. Bu proxy nesneleri yalnızca yineleyiciler tarafından iç kullanım için olduğundan belgelenmez, ancak mekanizmanın nasıl çalıştığını bilmek yararlıdır.

Kapsayıcılar üzerinde `range for` `IVector` bir döngü `auto&&` kullandığınızda, yineleyici değişkeninin `VectorProxy` öğelere doğru şekilde bağlanmasını sağlamak için kullanın. Eğer `auto` kullanıyorsanız `auto&`veya, derleyici uyarı C4239 yükseltilir ve `VectoryProxy` uyarı metninde belirtilir.

Aşağıdaki resimde bir `range for` `IVector<Person^>`. Yürütmenin 64. **QuickWatch** penceresi, yineleyici değişkeninin `p` aslında `VectorProxy<Person^>` `m_v` `m_i` üye değişkenlere sahip ve sahip olan bir değişken olduğunu gösterir. Ancak, bu `GetType` değişkeni çağırdığınızda, aynı türü `Person` `p2`örneğin karşısına döndürür. Paket, **QuickWatch'ta**görünse de, `VectorProxy` `ArrowProxy` hata ayıklayıcının belirli derleyici hatalarını veya diğer yerlerde görünmesine rağmen, genellikle bunlar için açıkça kodlamanız gerekmese de.

![VectorProxy aralığında&#45;döngü için dayalı](../cppcx/media/vectorproxy-1.png "VectorProxy aralığında&#45;döngü için dayalı")

Proxy nesnesinin etrafında kodlamanız gereken senaryolardan biri, öğeler `dynamic_cast` üzerinde bir şey gerçekleştirmeniz gerektiğinde (örneğin, bir `UIElement` öğe koleksiyonunda belirli bir türdeki XAML nesnelerini aradığınızda) olur. Bu durumda, önce [öğeyi Platform::Object](../cppcx/platform-object-class.md)^'a atmalı ve ardından dinamik dökümü gerçekleştirmelisiniz:

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

## <a name="map-usage"></a>Harita kullanımı

Bu örnek, öğeleri nasıl ekleyip bir Platformda nasıl arayacağını [gösterir::Koleksiyonlar::Harita](../cppcx/platform-collections-map-class.md), ve sonra salt okunur Windows olarak `Map` döndürün::Hazırlık::Koleksiyonlar::IMapView türü. [Windows::Foundation::Collections::IMapView](/uwp/api/windows.foundation.collections.imapview-2)

[!code-cpp[cx_collections#04](../cppcx/codesnippet/CPP/collections/class1.cpp#04)]

Genel olarak, iç harita işlevselliği için, performans nedenleriyle türü tercih edin. `std::map` Eğer ABI üzerinden konteyner geçmek zorunda, bir [Platform oluşturmak::Koleksiyonlar::Std](../cppcx/platform-collections-map-class.md) gelen [harita::harita](../standard-library/map-class.md) ve bir Windows `Map` olarak döndürün::Temel::Koleksiyonlar::IMap . [Windows::Foundation::Collections::IMap](/uwp/api/windows.foundation.collections.imap-2) Ortak iade değeri `Map` veya parametrebir tür kullanmaya çalışırsanız, derleyici hatası C3986 yükseltilir. Bir `IMap`' ye değiştirerek `Map` hatayı düzeltebilirsiniz. Bazı durumlarda-örneğin, çok sayıda arama veya ekleme yapmıyorsanız ve koleksiyonu sık sık ABI üzerinden geçiriyorsanız-en başından itibaren kullanmak `Platform::Collections::Map` ve `std::map`. Her durumda, bu üç tür en `IMap` az performans gösterir, çünkü bir arama ve ekleme işlemleri kaçının. `IMap` Yalnızca kabı ABI'den geçtiğiniz noktada dönüştürün.

## <a name="value-types-in-map"></a>Haritadaki değer türleri

[Platformdaki öğeler::Koleksiyonlar::Harita](../cppcx/platform-collections-map-class.md) sıralanır. Bir'de depolanacak herhangi `Map` bir öğe, örtülü olarak veya sağladığınız özel bir [stl::daha az](../standard-library/less-struct.md) karşılaştırıcı kullanarak, katı zayıf sıralama ile karşılaştırıldığında daha az destek gerekir. Skaler türleri örtülü karşılaştırmayı destekler. Gibi `Windows::Foundation::DateTime`skaler olmayan değer türleri için veya özel karşılaştırmalar `objA->UniqueID < objB->UniqueID`için (örneğin), özel bir karşılaştırıcı sağlamanız gerekir.

## <a name="collection-types"></a>Koleksiyon türleri

Koleksiyonlar dört kategoriye ayrılır: değiştirilebilir sürümler ve sıra koleksiyonlarının salt okunur sürümleri ve birleştirici koleksiyonlar. Buna ek olarak, C++/CX koleksiyonların erişimini kolaylaştıran üç yineleyici sınıfı sağlayarak koleksiyonları geliştirir.

Değiştirilebilir bir koleksiyonun öğeleri değiştirilebilir, ancak *görünüm*olarak bilinen salt okunur koleksiyonun öğeleri yalnızca okunabilir. [Bir Platformun Öğeleri::Koleksiyonlar::Vektör](../cppcx/platform-collections-vector-class.md) veya[Platform::Koleksiyonlar::VectorView](../cppcx/platform-collections-vectorview-class.md) koleksiyonuna bir yineleyici veya koleksiyonun [Vektörü::GetAt](../cppcx/platform-collections-vector-class.md#getat) ve dizin kullanılarak erişilebilir. Bir bağdaştırıcı koleksiyonun öğelerine, koleksiyonun [Haritası::Arama](../cppcx/platform-collections-map-class.md#lookup) ve bir anahtar kullanılarak erişilebilir.

[Platform::Collections::Map Sınıfı](../cppcx/platform-collections-map-class.md)<br/>
Değiştirilebilir, işşifif bir koleksiyon. Eşöğe öğeleri anahtar değeri çiftleridir. İlişkili değerini almak için bir anahtar aranıyor ve tüm anahtar değeri çiftleri arasında yinelenme, her ikisi de desteklenir.

`Map`ve `MapView` şablonlar; `<K, V, C = std::less<K>>` bu nedenle, karşılaştırıcıözelleştirebilirsiniz.  Ayrıca, `Vector` ve `VectorView` böylece davranışını `<T, E = std::equal_to<T>>` `IndexOf()`özelleştirebilirsiniz şablona. Bu çoğunlukla ve `Vector` `VectorView` değer structs için önemlidir. Örneğin, Bir Vector\<Windows oluşturmak için::Foundation::DateTime>, DateTime == işleci aşırı yüklemez çünkü özel bir karşılaştırıcı sağlamanız gerekir.

[Platform::Koleksiyonlar::MapView Sınıfı](../cppcx/platform-collections-mapview-class.md)<br/>
Bir `Map`.

[Platform::Collections::Vector Sınıfı](../cppcx/platform-collections-vector-class.md)<br/>
Değiştirilebilir sıra koleksiyonu. `Vector<T>`sabit zamanlı rasgele erişimi ve amortismana tabi-sabit zamanlı [Append](../cppcx/platform-collections-vector-class.md#append) işlemlerini destekler...

[Platform::Collections::VectorView Sınıfı](../cppcx/platform-collections-vectorview-class.md)<br/>
Bir `Vector`.

[Platform::Collections::InputIterator Sınıfı](../cppcx/platform-collections-inputiterator-class.md)<br/>
Bir STL giriş yinelemesinin gereksinimlerini karşılayan bir STL yineleyici.

[Platform::Collections::VectorIterator Sınıfı](../cppcx/platform-collections-vectoriterator-class.md)<br/>
STL mutasyona uğrayabilir rasgele erişim yineleyicisinin gereksinimlerini karşılayan bir STL yineleyici.

[Platform::Koleksiyonlar::VectorViewIterator Sınıfı](../cppcx/platform-collections-vectorviewiterator-class.md)<br/>
Bir STL `const` rasgele erişim yineleme gereksinimlerini karşılayan bir STL yineleyici.

### <a name="begin-and-end-functions"></a>begin() ve end() fonksiyonları

C++/CX, STL'nin `VectorView` `Map`,, ve `MapView` `Windows::Foundation::Collections` rasgele nesneleri işlemek `Vector`için kullanımını basitleştirmek [için, begin İşlev](../cppcx/begin-function.md) ve [bitiş Işlevi](../cppcx/end-function.md) üye olmayan işlevlerin aşırı yüklenmelerini destekler.

Aşağıdaki tabloda kullanılabilir yineleyiciler ve işlevler listelenmektedir.

|Yineleyiciler|İşlevler|
|---------------|---------------|
|[Platform::Koleksiyonlar::VectorIterator\<T>](../cppcx/platform-collections-vectoriterator-class.md)<br /><br /> (Dahili depolar [Windows::Foundation::Koleksiyonlar:: IVector\<T>](/uwp/api/windows.foundation.collections.ivector-1) ve int.)|[begin](../cppcx/begin-function.md)/ [end](../cppcx/end-function.md)([Windows:Foundation::Koleksiyonlar::\<IVector T>](/uwp/api/windows.foundation.collections.ivector-1))|
|[Platform::Koleksiyonlar::VectorViewIterator\<T>](../cppcx/platform-collections-vectorviewiterator-class.md)<br /><br /> (Dahili mağazalar [IVectorView\<T>](/uwp/api/windows.foundation.collections.ivectorview-1)^ ve int.)|[başlangıç](../cppcx/begin-function.md)/ [sonu](../cppcx/end-function.md) ([\<IVectorView T>](/uwp/api/windows.foundation.collections.ivectorview-1)^)|
|[Platform::Koleksiyonlar::Giriş T\<>](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> (Dahili mağazalar [\<IIterator T>](/uwp/api/windows.foundation.collections.iiterator-1)^ ve T.)|[bitiş başlar](../cppcx/begin-function.md)/ [end](../cppcx/end-function.md) ([\<Iterable T>](/uwp/api/windows.foundation.collections.iiterable-1))|
|[Platform::Koleksiyonlar::InputIterator<IKeyValuePair\<K, V>^>](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> (Dahili mağazalar [\<IIterator T>](/uwp/api/windows.foundation.collections.iiterator-1)^ ve T.)|[bitiş başlar](../cppcx/begin-function.md)/ [end](../cppcx/end-function.md) ([IMap\<K,V>](/uwp/api/windows.foundation.collections.imap-2).|
|[Platform::Koleksiyonlar::InputIterator<IKeyValuePair\<K, V>^>](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> (Dahili mağazalar [\<IIterator T>](/uwp/api/windows.foundation.collections.iiterator-1)^ ve T.)|[begin](../cppcx/begin-function.md)/ [end](../cppcx/end-function.md) ([Windows::Foundation::Koleksiyonlar::IMapView](/uwp/api/windows.foundation.collections.imapview-2))|

### <a name="collection-change-events"></a>Koleksiyon değişikliği olayları

`Vector`ve `Map` bir koleksiyon nesnesi değiştirildiğinde veya sıfırlandığında veya koleksiyonun herhangi bir öğesi eklendiğinde, kaldırıldığında veya değiştirildiğinde meydana gelen olayları uygulayarak XAML koleksiyonlarında veri bağlamayı destekleyin. Devralamazsınız `Map` veya `Vector` bu türler mühürlü olduğundan, veri bağlamayı destekleyen kendi türlerinizi yazabilirsiniz.

[Windows::Foundation::Collections::VectorChangedEventHandler](/uwp/api/windows.foundation.collections.vectorchangedeventhandler-1) ve [Windows::Foundation::Collections::MapChangedEventHandler](/uwp/api/windows.foundation.collections.mapchangedeventhandler-2) temsilcileri, koleksiyon değişikliği olayları için olay işleyicileri için imzaları belirtir. [Windows:Foundation::Collections::CollectionChange](/uwp/api/windows.foundation.collections.collectionchange) public enum class `Platform::Collection::Details::MapChangedEventArgs` ve `Platform::Collections::Details::VectorChangedEventArgs` ref sınıfları, olaya neyin neden olduğunu belirlemek için olay bağımsız değişkenlerini depolayın. Türler `*EventArgs` `Details` ad alanında tanımlanır, çünkü bunları kullanırken `Map` veya . `Vector`

## <a name="see-also"></a>Ayrıca bkz.

[Tür Sistemi](../cppcx/type-system-c-cx.md)<br/>
[C++/CX Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad Alanları Başvurusu](../cppcx/namespaces-reference-c-cx.md)
