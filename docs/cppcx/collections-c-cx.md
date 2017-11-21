---
title: Koleksiyonlar (C + +/ CX) | Microsoft Docs
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 914da30b-aac5-4cd7-9da3-a5ac08cdd72c
caps.latest.revision: "35"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: c8496e0128d3ebd88c5a3a2fafad593c135f6fbf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="collections-ccx"></a>Koleksiyonlar (C + +/ CX)
C + +/ CX programı standart Şablon kitaplığı (STL) kapsayıcıları veya herhangi bir kullanıcı tanımlı koleksiyon türü boş kullanımını yapabilir. Ancak, geçirdiğiniz zaman koleksiyonları ve geriye Windows çalışma zamanı uygulama ikili arabirimi (ABI) — Örneğin, bir XAML denetimi veya bir JavaScript istemci — Windows çalışma zamanı koleksiyon türleri kullanmanız gerekir.  
  
 Windows Çalışma Zamanı Modülü arabirimler koleksiyonları ve ilgili türleri ve C + için tanımlar +/ CX collection.h üstbilgi dosyası somut C++ uygulamalarında sağlar. Bu çizim koleksiyon türleri arasındaki ilişkileri göstermektedir:  
  
 ![C &#43; &#43; &#47; Koleksiyon türleri için CX devralma ağacı](../cppcx/media/cppcxcollectionsinheritancetree.png "CPPCXCollectionsInheritanceTree")  
  
-   [Platform::Collections:: Vector sınıfı](../cppcx/platform-collections-vector-class.md) benzer [std::vector sınıfı](../standard-library/vector-class.md).  
  
-   [Platform::Collections sınıfı](../cppcx/platform-collections-map-class.md) sınıfı benzer [std::map sınıfı](../standard-library/map-class.md).  
  
-   [Platform::Collections::VectorView sınıfı](../cppcx/platform-collections-vectorview-class.md) ve[Platform::Collections::MapView sınıfı](../cppcx/platform-collections-mapview-class.md) salt okunur sürümleri `Vector` ve `Map`.  
  
-   Yineleyiciler tanımlanmış [Platform::Collections Namespace](../cppcx/platform-collections-namespace.md). Bu yineleyiciler STL yineleyiciler gereksinimlerini karşılamak ve kullanımını etkinleştirmek [std::find](../standard-library/algorithm-functions.md#find), [std::count_if](../standard-library/algorithm-functions.md#count_if)ve herhangi diğer STL algoritmaları [Windows::Foundation::Collections](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.aspx) arabirim türü veya [Platform::Collections](../cppcx/platform-collections-namespace.md) somut türü. Örneğin, bu, C# içinde oluşturulur ve bir STL algoritma uygulayan bir Windows çalışma zamanı bileşeni koleksiyonunda yineleyebilirsiniz anlamına gelir.  
  
    > [!IMPORTANT]
    >  Proxy yineleyiciler `VectorIterator` ve `VectorViewIterator` proxy nesnelerini kullanan `VectoryProxy<T>` ve `ArrowProxy<T>` STL kapsayıcıları ile kullanımını etkinleştirmek için. Daha fazla bilgi için bu makalenin sonraki bölümlerinde "VectorProxy öğeler" bölümüne bakın.  
  
-   C + +/ CX koleksiyon türleri desteği aynı iş parçacığı güvenliği garanti STL kapsayıcıları destekler.  
  
-   [Windows::Foundation::Collections::IObservableVector](http://msdn.microsoft.com/library/windows/apps/br226052.aspx) ve [Windows::Foundation::Collections::IObservableMap](http://msdn.microsoft.com/library/windows/apps/br226050.aspx) koleksiyonu çeşitli şekillerde değiştirdiğinde tetiklenen olayları tanımlayın. Bu arabirimleri uygulayarak [Platform::Collections](../cppcx/platform-collections-map-class.md) ve [Platform::Collections:: Vector](../cppcx/platform-collections-vector-class.md) XAML koleksiyonları ile veri bağlamayı destekler. Örneğin, bir `Vector` , veri bağlama için bir `Grid`, ne zaman, bir koleksiyon için bir öğe ekleme, değiştirme kılavuz Arabiriminde yansıtılır.  
  
## <a name="vector-usage"></a>Vektör kullanımı  
 Sınıfınıza dizisi kapsayıcı başka bir Windows çalışma zamanı bileşenine geçmek olduğunda, kullanın [Windows::Foundation::Collections:: IVector\<T >](http://msdn.microsoft.com/library/windows/apps/br206631.aspx) parametresi veya dönüş türü olarak ve [Platform:: Collections::Vector\<T >](../cppcx/platform-collections-vector-class.md) somut uygulaması olarak. Kullanmayı denerseniz, bir `Vector` türü ortak dönüş değeri veya parametre, derleyici hatası C3986 harekete geçirilen. Değiştirerek hatayı düzeltmek `Vector` için bir `IVector`.  
  
> [!IMPORTANT]
>  Bir dizi kendi programında geçirilirse, ardından kullanın ya da `Vector` veya `std::vector` daha verimlidir olduklarından `IVector`. Kullanım `IVector` yalnızca kapsayıcı arasında ABI geçirdiğiniz zaman.  
>   
>  Windows çalışma zamanı tür sistemi basit diziler kavramını desteklemez ve bu nedenle bir IVector geçiremezsiniz < Platform::Array\<T >> bir dönüş değeri veya yöntem parametresi olarak. Basit bir dizi veya bir dizi sıraları ABI arasında geçirmek için kullanmak `IVector<IVector<T>^>`.  
  
 `Vector<T>`ekleme, kaldırma ve erişme öğelerini koleksiyonda ve örtük olarak dönüştürülebilir için gerekli olan yöntemleri sağlayan `IVector<T>`. STL algoritmaları örneklerinde kullanabilirsiniz `Vector<T>`. Aşağıdaki örnek, bazı temel kullanım gösterir. [İşlevi başlamak](../cppcx/begin-function.md) ve [bitiş işlevi](../cppcx/end-function.md) aşağıda verilmiştir `Platform::Collections` ad alanı, değil `std` ad alanı.  
  
 [!code-cpp[cx_collections#01](../cppcx/codesnippet/CPP/collections/class1.cpp#01)]  
  
 Kullanan var olan kodu varsa `std::vector` ve bir Windows çalışma zamanı bileşenini yeniden, yalnızca birini kullanmak istediğiniz `Vector` alır oluşturucular bir `std::vector` veya oluşturmak için yineleyiciler çiftinin bir `Vector` burada geçirdiğiniz noktada ABI koleksiyonunda. Aşağıdaki örnekte nasıl kullanılacağını gösterir `Vector` taşıma Oluşturucusu verimli başlatma işlemi için bir `std::vector`. Özgün taşıma işleminden sonra `vec` değişkeni artık geçerli değil.  
  
 [!code-cpp[cx_collections#02](../cppcx/codesnippet/CPP/collections/class1.cpp#02)]  
  
 Gelecekteki bir noktada ABI arasında geçmesi gereken dizeleri vektörü varsa dizesi oluşturmak karar vermeniz gerekir başlangıçta olarak `std::wstring` türleri veya as `Platform::String^` türleri. Dizelerde işleme çok yapmanız gereken, ardından kullanın `wstring`. Aksi takdirde, dize olarak oluşturun `Platform::String^` türleri ve daha sonra dönüştürme maliyetini kaçının. Ayrıca bu dizeleri almaya karar vermeniz gerekir bir `std:vector` veya `Platform::Collections::Vector` dahili olarak. Genel bir uygulama olarak kullanmak `std::vector` ve ardından oluşturun bir `Platform::Vector` arasında ABI kapsayıcı geçirdiğinizde almaktır.  
  
## <a name="value-types-in-vector"></a>Vektör değer türleri  
 Depolanması için herhangi bir öğe bir [Platform::Collections:: Vector](../cppcx/platform-collections-vector-class.md) eşitlik karşılaştırması örtük veya özel bir kullanarak desteklemelidir [std::equal_to](../standard-library/equal-to-struct.md) sağladığınız karşılaştırıcı. Tüm başvuru türleri ve örtük olarak eşitlik karşılaştırmaları destekleyen tüm skaler türler. Skaler olmayan için değer türleri gibi [Windows::Foundation::DateTime](http://msdn.microsoft.com/library/windows/apps/windows.foundation.datetime.aspx), veya özel karşılaştırmaları — Örneğin, `objA->UniqueID == objB->UniqueID`— özel işlev nesnesi sağlamanız gerekir.  
   
  
## <a name="vectorproxy-elements"></a>VectorProxy öğeleri  
 [Platform::Collections::VectorIterator](../cppcx/platform-collections-vectoriterator-class.md) ve [Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md) kullanımını etkinleştirmek `range for` döngüler ve algoritmalar gibi [std::sort](../standard-library/algorithm-functions.md#sort) ile bir [IVector\<T >](http://msdn.microsoft.com/en-us/library/windows/apps/br206631.aspx) kapsayıcı. Ancak `IVector` öğeleri C++ erişilemiyor işaretçiye; yalnızca aracılığıyla erişilebilen [GetAt](http://msdn.microsoft.com/library/windows/apps/br206634.aspx) ve [SetAt](http://msdn.microsoft.com/library/windows/apps/br206642.aspx) yöntemleri. Bu nedenle, bu yineleyiciler proxy sınıfları kullanan `Platform::Details::VectorProxy<T>` ve `Platform::Details::ArrowProxy<T>` ayrı ayrı öğeler erişim sağlamak için `*`, `->`, ve `[]` STL gerektirdiği işleçler. NET olarak söylemek verilen bir `IVector<Person^> vec`, türü `*begin(vec)` olan `VectorProxy<Person^>`. Ancak, proxy neredeyse her zaman kodunuzu saydam nesnesidir. Bu proxy nesneleri, çünkü bunlar yalnızca yineleyiciler tarafından dahili kullanım içindir, ancak mekanizması nasıl çalıştığını anlamak kullanışlıdır açıklanmamıştır.  
  
 Kullandığınızda, bir `range for` üzerinden döngü `IVector` kapsayıcılar, kullanma `auto&&` doğru olarak bağlamak için yineleyici değişken etkinleştirmek için `VectorProxy` öğeleri. Kullanırsanız `auto` veya `auto&`, derleyici uyarısı C4239 oluşturulur ve `VectoryProxy` uyarı metni belirtiliyor.  
  
 Aşağıdaki çizimde gösterildiği bir `range for` üzerinden döngü bir `IVector<Person^>`. Yürütme satırında 64 kesme durdurulur dikkat edin. **QuickWatch** penceresi gösterir, yineleyici değişken `p` aslında bir `VectorProxy<Person^>` olan `m_v` ve `m_i` üye değişkenleri. Çağırdığınızda ancak `GetType` isteğe bağlı olarak bu değişken üzerinde aynı türde döndürür `Person` örneği `p2`. Takeaway rağmen olan `VectorProxy` ve `ArrowProxy` görünebilir **QuickWatch**, hata ayıklayıcı belirli derleyici hataları veya başka bir yerde, genellikle açıkça kendileri için kod gerekmez.  
  
 ![Aralık &#45; VectorProxy döngü için temel](../cppcx/media/vectorproxy-1.png "VectorProxy_1")  
  
 Sahip olduğunuz koduna proxy nesnesi geçici bir senaryo gerçekleştirmek sahip olduğunda bir `dynamic_cast` öğelerde — Örneğin, ne zaman aradığınız XAML nesneleri belirli bir türdeki bir `UIElement` öğe koleksiyonu. Bu durumda, ilk öğeye atamalısınız [Platform::Object](../cppcx/platform-object-class.md)^ ve dinamik atama gerçekleştirin:  
  
```  
  
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
 Bu örnek öğeleri eklemek ve de aramak gösterilmektedir bir [Platform::Collections](../cppcx/platform-collections-map-class.md)ve sonra geri dönüp `Map` salt okunur olarak [Windows::Foundation::Collections::IMapView](http://msdn.microsoft.com/library/windows/apps/br226037.aspx) türü.  
  
 [!code-cpp[cx_collections#04](../cppcx/codesnippet/CPP/collections/class1.cpp#04)]  
  
 Genel olarak, iç harita işlevselliği için tercih ettiğiniz `std::map` performans nedenleriyle türü. Kapsayıcı ABI arasında geçirmek varsa oluşturmak bir [Platform::Collections](../cppcx/platform-collections-map-class.md) gelen [std::map](../standard-library/map-class.md) ve geri dönüp `Map` olarak bir [Windows::Foundation:: Collections::IMap](http://msdn.microsoft.com/library/windows/apps/br226042.aspx). Kullanmayı denerseniz, bir `Map` türü ortak dönüş değeri veya parametre, derleyici hatası C3986 harekete geçirilen. Değiştirerek hatayı düzeltmek `Map` için bir `IMap`. Bazı durumlarda — Örneğin, çok sayıda aramaları veya eklemeleri yetişememe ve koleksiyon sık arasında ABI geçtiğiniz — kullanmak daha ucuz olabilir `Platform::Collections::Map` başlangıçtan itibaren ve dönüştürmemaliyetinikaçının`std::map`. Herhangi bir durumda, arama önlemek ve işlemleri eklemek bir `IMap` bu üç tür en az kullanıcı olduğundan. Dönüştür `IMap` yalnızca kapsayıcı ABI arasında geçirmek noktada.  
  
## <a name="value-types-in-map"></a>Haritadaki değer türleri  
 Öğeleri bir [Platform::Collections](../cppcx/platform-collections-map-class.md) sıralanır. Depolanması için herhangi bir öğe bir `Map` daha az desteklemelidir-sıralama, dolaylı ya da özel bir kullanarak strict zayıf ile karşılaştırma daha [stl::less](../standard-library/less-struct.md) sağladığınız karşılaştırıcı. Skaler türler karşılaştırma örtük olarak destekler. Skaler olmayan için değer türleri gibi `Windows::Foundation::DateTime`, veya özel karşılaştırmaları — Örneğin, `objA->UniqueID < objB->UniqueID`— özel bir karşılaştırıcı sağlamanız gerekir.  
  
## <a name="collection-types"></a>Koleksiyon türleri  
 Koleksiyonları dört kategoriye ayrılır: salt okunur sürümleri dizisi koleksiyonları ve ilişkilendirilebilir koleksiyonları ve değiştirilebilir. Ayrıca, C + +/ CX koleksiyonları erişmeyi kolaylaştırmak üç yineleyici sınıfları sağlayarak koleksiyonları geliştirir. 
  
 Değiştirilebilir bir koleksiyonun öğelerini değiştirilebilir, ancak olarak bilinen bir salt okunur koleksiyonun öğelerini bir *Görünüm*, salt okunur. Öğeleri bir [Platform::Collections:: Vector](../cppcx/platform-collections-vector-class.md) veya[Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md) koleksiyonu erişilebilir yineleyici veya koleksiyonun kullanarak [Vector::GetAt](../cppcx/platform-collections-vector-class.md#getat) ve bir dizin. İlişkilendirilebilir bir koleksiyonun öğelerini erişilebilir koleksiyonunun kullanarak [Map::Lookup](../cppcx/platform-collections-map-class.md#lookup) ve bir anahtar.  
  
 [Platform::Collections sınıfı](../cppcx/platform-collections-map-class.md)  
 Değiştirilebilir, ilişkilendirilebilir koleksiyonu. Harita, anahtar-değer çiftleri öğelerdir. İlişkili değerini ve tüm anahtar-değer çiftleri yineleme almak için bir anahtar bakarak, her ikisi de desteklenir.  
  
 `Map`ve `MapView` üzerinde şablonlu olan `<K, V, C = std::less<K>>`; bu nedenle, karşılaştırıcı özelleştirebilirsiniz.  Ayrıca, `Vector` ve `VectorView` üzerinde şablonlu olan `<T, E = std::equal_to<T>>` davranışını özelleştirebilirsiniz böylece `IndexOf()`. Bu çoğunlukla önemlidir `Vector` ve `VectorView` değeri yapılar. Örneğin, bir vektör oluşturmak için\<Windows::Foundation::DateTime >, DateTime aşırı değil çünkü özel bir karşılaştırıcı sağlamalısınız == işleci.  
  
 [Platform::Collections::MapView sınıfı](../cppcx/platform-collections-mapview-class.md)  
 Bir salt okunur sürümünü bir `Map`.  
  
 [Platform::Collections:: Vector sınıfı](../cppcx/platform-collections-vector-class.md)  
 Değiştirilebilir dizisi koleksiyonu. `Vector<T>`sabiti zamanı rasgele erişim ve amortized-sabiti-time destekler [Append](../cppcx/platform-collections-vector-class.md#append) işlemleri...  
  
 [Platform::Collections::VectorView sınıfı](../cppcx/platform-collections-vectorview-class.md)  
 Bir salt okunur sürümünü bir `Vector`.  
  
 [Platform::Collections::InputIterator sınıfı](../cppcx/platform-collections-inputiterator-class.md)  
 STL giriş yineleyici gereksinimlerini karşılayan bir STL yineleyici.  
  
 [Platform::Collections::VectorIterator sınıfı](../cppcx/platform-collections-vectoriterator-class.md)  
 STL değişebilir rasgele erişim yineleyici gereksinimlerini karşılayan bir STL yineleyici.  
  
 [Platform::Collections::VectorViewIterator sınıfı](../cppcx/platform-collections-vectorviewiterator-class.md)  
 Bir STL gereksinimlerini karşılayan bir STL yineleyici `const` rasgele erişim yineleyici.  
  
### <a name="begin-and-end-functions"></a>Begin() ve end() işlevleri  
 İşlenecek STL kullanımını kolaylaştırmak için `Vector`, `VectorView`, `Map`, `MapView`ve rasgele `Windows::Foundation::Collections` nesneleri, C + +/ CX destekleyen aşırı [işlevi başlamak](../cppcx/begin-function.md) ve [bitiş İşlev](../cppcx/end-function.md) olmayan üye işlevleri.  
  
 Aşağıdaki tabloda kullanılabilir yineleyiciler ve işlevleri listeler.  
  
|Yineleyiciler|İşlevler|  
|---------------|---------------|  
|[Platform::Collections::VectorIterator\<T >](../cppcx/platform-collections-vectoriterator-class.md)<br /><br /> (Dahili olarak depolar [Windows::Foundation::Collections:: IVector\<T >](http://msdn.microsoft.com/library/windows/apps/br206631.aspx) ve tamsayı)|[Begin](../cppcx/begin-function.md)/ [son](../cppcx/end-function.md)([Windows::Foundation::Collections:: IVector\<T >](http://msdn.microsoft.com/library/windows/apps/br206631.aspx))|  
|[Platform::Collections::VectorViewIterator\<T >](../cppcx/platform-collections-vectorviewiterator-class.md)<br /><br /> (Dahili olarak depolar [IVectorView\<T >](http://msdn.microsoft.com/library/windows/apps/br226058.aspx)^ ve tamsayı)|[Begin](../cppcx/begin-function.md)/ [son](../cppcx/end-function.md) ([IVectorView\<T >](http://msdn.microsoft.com/library/windows/apps/br226058.aspx)^)|  
|[Platform::Collections::InputIterator\<T >](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> (Dahili olarak depolar [IIterator\<T >](http://msdn.microsoft.com/library/windows/apps/br226026.aspx)^ ve t)|[Begin](../cppcx/begin-function.md)/ [son](../cppcx/end-function.md) ([IIterable\<T >](http://msdn.microsoft.com/library/windows/apps/br226024.aspx))|  
|[Platform::Collections::InputIterator < IKeyValuePair\<K, V > ^ >](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> (Dahili olarak depolar [IIterator\<T >](http://msdn.microsoft.com/library/windows/apps/br226026.aspx)^ ve t)|[Begin](../cppcx/begin-function.md)/ [son](../cppcx/end-function.md) ([IMAP\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226042.aspx).|  
|[Platform::Collections::InputIterator < IKeyValuePair\<K, V > ^ >](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> (Dahili olarak depolar [IIterator\<T >](http://msdn.microsoft.com/library/windows/apps/br226026.aspx)^ ve t)|[Begin](../cppcx/begin-function.md)/ [son](../cppcx/end-function.md) ([Windows::Foundation::Collections::IMapView](http://msdn.microsoft.com/library/windows/apps/br226037.aspx))|  
  
### <a name="collection-change-events"></a>Koleksiyon değişikliği olayları  
 `Vector`ve `Map` bir koleksiyon nesnesi değiştirildiğinde meydana gelen olayları veya sıfırlama uygulayarak XAML koleksiyonları veri bağlamasını destekleyen veya bir koleksiyonun herhangi bir öğe eklendiğinde, kaldırıldı veya değiştirildi. Devralınan olamaz rağmen bu destek databinding kendi türlerine yazabilirsiniz `Map` veya `Vector` bu türlerde korumalı için.  
  
 [Windows::Foundation::Collections::VectorChangedEventHandler](http://msdn.microsoft.com/library/windows/apps/br206656.aspx) ve [Windows::Foundation::Collections::MapChangedEventHandler](http://msdn.microsoft.com/library/windows/apps/br206644.aspx) temsilcileri belirtmek için olay işleyicileri imzaları Koleksiyon olayları değiştirin. [Windows::Foundation::Collections::CollectionChange](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.collectionchange.aspx) ortak enum sınıfı ve `Platform::Collection::Details::MapChangedEventArgs` ve `Platform::Collections::Details::VectorChangedEventArgs` ref sınıfları depolamak olay neyin neden olduğunu belirlemek için olay bağımsız değişkenler. *`EventArgs` Türleri tanımlanmış `Details` ad alanı oluşturmak veya bunları açıkça kullandığınızda tüketen gerekmez çünkü `Map` veya `Vector`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tür sistemi](../cppcx/type-system-c-cx.md)   
 [Yerleşik türler](http://msdn.microsoft.com/en-us/acc196fd-09da-4882-b554-6c94685ec75f)   
 [Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)   
 [Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)