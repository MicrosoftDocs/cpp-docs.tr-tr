---
title: hash_multiset (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_multiset
dev_langs: C++
helpviewer_keywords:
- <cliext/hash_set> header [STL/CLR]
- hash_multiset class [STL/CLR]
- <hash_set> header [STL/CLR]
ms.assetid: 8462bd21-6829-4dd3-ac81-c42d6fdf92f0
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8b98e8d858c154e344320c759ac4a38c1cf78cbf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="hashmultiset-stlclr"></a>hash_multiset (STL/CLR)
Şablon sınıfı çift yönlü erişimi olan öğeleri değişen uzunluk dizisi denetleyen bir nesne tanımlar. Kapsayıcı kullandığınız `hash_multiset` bir çift yönlü depolama her tablo girişi öğeleri dizisi bir karma tablosu olarak yönetmek için düğümleri ve tek bir öğede depolama her düğüm listesi bağlı. Her öğenin değerini dizisi sıralama için bir anahtar olarak kullanılır.  
  
 Aşağıda, açıklamada `GValue` aynı `GKey`, sırayla olduğu aynı `Key` ikinci ref türü olmadıkça olmasından; bu durumda `Key^`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Key>  
    ref class hash_multiset  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IHash<Gkey, GValue>  
    { ..... };  
```  
  
#### <a name="parameters"></a>Parametreler  
 Anahtar  
 Anahtar bileşeni denetlenen sıradaki öğenin türü.  
  
## <a name="members"></a>Üyeler  
  
|Tür Tanımlaması|Açıklama|  
|---------------------|-----------------|  
|[hash_multiset::const_iterator (STL/CLR)](../dotnet/hash-multiset-const-iterator-stl-clr.md)|Denetlenen dizi için bir sabit yineleyici türü.|  
|[hash_multiset::const_reference (STL/CLR)](../dotnet/hash-multiset-const-reference-stl-clr.md)|Bir öğe için sabit bir başvuru türü.|  
|[hash_multiset::const_reverse_iterator (STL/CLR)](../dotnet/hash-multiset-const-reverse-iterator-stl-clr.md)|Denetimli sırası için sabit bir ters yineleyici türü.|  
|[hash_multiset::difference_type (STL/CLR)](../dotnet/hash-multiset-difference-type-stl-clr.md)|İki öğeler arasında (büyük olasılıkla imzalanmış) bir uzaklık türü.|  
|[hash_multiset::generic_container (STL/CLR)](../dotnet/hash-multiset-generic-container-stl-clr.md)|Genel arabirim kapsayıcının türü.|  
|[hash_multiset::generic_iterator (STL/CLR)](../dotnet/hash-multiset-generic-iterator-stl-clr.md)|Yineleyici kapsayıcısı için genel arabirimi türü.|  
|[hash_multiset::generic_reverse_iterator (STL/CLR)](../dotnet/hash-multiset-generic-reverse-iterator-stl-clr.md)|Kapsayıcı için genel arabirimini ters yineleyici türü.|  
|[hash_multiset::generic_value (STL/CLR)](../dotnet/hash-multiset-generic-value-stl-clr.md)|Kapsayıcı için genel arabirimini öğenin türü.|  
|[hash_multiset::hasher (STL/CLR)](../dotnet/hash-multiset-hasher-stl-clr.md)|Bir anahtar için karma temsilcisi.|  
|[hash_multiset::iterator (STL/CLR)](../dotnet/hash-multiset-iterator-stl-clr.md)|Denetlenen dizi için bir yineleyici türü.|  
|[hash_multiset::key_compare (STL/CLR)](../dotnet/hash-multiset-key-compare-stl-clr.md)|İki anahtar sıralama temsilcisi.|  
|[hash_multiset::key_type (STL/CLR)](../dotnet/hash-multiset-key-type-stl-clr.md)|Bir sıralama anahtarının türü.|  
|[hash_multiset::Reference (STL/CLR)](../dotnet/hash-multiset-reference-stl-clr.md)|Bir öğe için bir başvuru türü.|  
|[hash_multiset::reverse_iterator (STL/CLR)](../dotnet/hash-multiset-reverse-iterator-stl-clr.md)|Denetimli sırası için ters yineleyici türü.|  
|[hash_multiset::size_type (STL/CLR)](../dotnet/hash-multiset-size-type-stl-clr.md)|İki öğe arasındaki (negatif olmayan) uzaklığı türü.|  
|[hash_multiset::value_compare (STL/CLR)](../dotnet/hash-multiset-value-compare-stl-clr.md)|İki öğenin değerleri için sıralama temsilcisi.|  
|[hash_multiset::value_type (STL/CLR)](../dotnet/hash-multiset-value-type-stl-clr.md)|Öğenin türü.|  
  
|Üye İşlevi|Açıklama|  
|---------------------|-----------------|  
|[hash_multiset::Begin (STL/CLR)](../dotnet/hash-multiset-begin-stl-clr.md)|Denetlenen dizinin başlangıcını belirtir.|  
|[hash_multiset::bucket_count (STL/CLR)](../dotnet/hash-multiset-bucket-count-stl-clr.md)|Demet sayar.|  
|[hash_multiset::Clear (STL/CLR)](../dotnet/hash-multiset-clear-stl-clr.md)|Tüm öğeleri kaldırır.|  
|[hash_multiset::Count (STL/CLR)](../dotnet/hash-multiset-count-stl-clr.md)|Belirtilen anahtar eşleşen öğeleri sayar.|  
|[hash_multiset::Empty (STL/CLR)](../dotnet/hash-multiset-empty-stl-clr.md)|Bir öğe olup olmadığını sınar.|  
|[hash_multiset::End (STL/CLR)](../dotnet/hash-multiset-end-stl-clr.md)|Denetlenen dizinin bitişini belirtir.|  
|[hash_multiset::equal_range (STL/CLR)](../dotnet/hash-multiset-equal-range-stl-clr.md)|Belirtilen bir anahtarla eşleşen aralığı bulur.|  
|[hash_multiset::ERASE (STL/CLR)](../dotnet/hash-multiset-erase-stl-clr.md)|Belirtilen konumlardaki öğeleri kaldırır.|  
|[hash_multiset::Find (STL/CLR)](../dotnet/hash-multiset-find-stl-clr.md)|Belirtilen bir anahtarla eşleşen bir öğeyi bulur.|  
|[hash_multiset::hash_delegate (STL/CLR)](../dotnet/hash-multiset-hash-delegate-stl-clr.md)|Bir anahtar için karma temsilci kopyalar.|  
|[hash_multiset::hash_multiset (STL/CLR)](../dotnet/hash-multiset-hash-multiset-stl-clr.md)|Bir kapsayıcı nesnesi oluşturur.|  
|[hash_multiset::insert (STL/CLR)](../dotnet/hash-multiset-insert-stl-clr.md)|Öğeleri ekler.|  
|[hash_multiset::key_comp (STL/CLR)](../dotnet/hash-multiset-key-comp-stl-clr.md)|İki anahtar sıralama temsilcisi kopyalar.|  
|[hash_multiset::load_factor (STL/CLR)](../dotnet/hash-multiset-load-factor-stl-clr.md)|Demet başına ortalama öğeyi sayar.|  
|[hash_multiset::lower_bound (STL/CLR)](../dotnet/hash-multiset-lower-bound-stl-clr.md)|Belirtilen anahtarla eşleşen aralığının başlangıcını bulur.|  
|[hash_multiset::make_value (STL/CLR)](../dotnet/hash-multiset-make-value-stl-clr.md)|Bir değer nesnesi oluşturur.|  
|[hash_multiset::max_load_factor (STL/CLR)](../dotnet/hash-multiset-max-load-factor-stl-clr.md)|Demet başına en yüksek öğe sayısını alır veya ayarlar.|  
|[hash_multiset::rbegin (STL/CLR)](../dotnet/hash-multiset-rbegin-stl-clr.md)|Ters denetimli dizisi başlangıcını belirtir.|  
|[hash_multiset::rehash (STL/CLR)](../dotnet/hash-multiset-rehash-stl-clr.md)|Karma tabloyu yeniden oluşturur.|  
|[hash_multiset::rend (STL/CLR)](../dotnet/hash-multiset-rend-stl-clr.md)|Ters denetimli dizinin sonuna belirler.|  
|[hash_multiset::size (STL/CLR)](../dotnet/hash-multiset-size-stl-clr.md)|Öğe sayısını sayar.|  
|[hash_multiset::Swap (STL/CLR)](../dotnet/hash-multiset-swap-stl-clr.md)|İki kapsayıcının içeriğinin yerini değiştirir.|  
|[hash_multiset::to_array (STL/CLR)](../dotnet/hash-multiset-to-array-stl-clr.md)|Denetimli sırası yeni bir diziye kopyalar.|  
|[hash_multiset::upper_bound (STL/CLR)](../dotnet/hash-multiset-upper-bound-stl-clr.md)|Belirtilen anahtarla eşleşen aralığın sonuna bulur.|  
|[hash_multiset::value_comp (STL/CLR)](../dotnet/hash-multiset-value-comp-stl-clr.md)|İki öğenin değerleri için sıralama temsilci kopyalar.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[hash_multiset::operator (STL/CLR) =](../dotnet/hash-multiset-operator-assign-stl-clr.md)|Denetimli dizisi yerini alır.|  
  
## <a name="interfaces"></a>Arabirimler  
  
|Arabirim|Açıklama|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Yinelenen bir nesne.|  
|<xref:System.Collections.IEnumerable>|Öğeleri dizisi.|  
|<xref:System.Collections.ICollection>|Öğeleri grubunu koruyun.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Yazılan öğeleri dizisi.|  
|<xref:System.Collections.Generic.ICollection%601>|Yazılı öğeleri grubunu koruyun.|  
|IHash\<anahtar, değer >|Genel kapsayıcı korur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Nesne ayırır ve bağlı bir çift yönlü listedeki tek düğümler olarak denetlediği dizisi için depolama boşaltır. Erişimi hızlandırmak için nesne da verimli tüm liste alt listelerin, bir dizi yönetme bir değişen uzunluk dizisi işaretçileri (karma tablosu), listeye tutar veya aralıkları. Hiçbir zaman kopyalayarak bir düğümün içeriğini başka düğümler arasındaki bağlantılar değiştirilerek sıralı tutan kova öğeleri ekler. INSERT ve rahatsız edici kalan öğeleri olmadan serbestçe öğeleri Kaldır anlamına gelir.  
  
 Nesne tarafından denetlenen bir saklı temsilci nesne türü çağırarak her demet siparişleri [hash_set::key_compare (STL/CLR)](../dotnet/hash-set-key-compare-stl-clr.md). Hash_set yapısı oluştururken saklı temsilci nesnesini belirtebilirsiniz; hiçbir temsilci nesnesi belirtirseniz, karşılaştırma varsayılandır `operator<=(key_type, key_type)`.  
  
 Üye işlevini çağırarak saklı temsilci nesneye erişim [hash_set::key_comp (STL/CLR)](../dotnet/hash-set-key-comp-stl-clr.md)`()`. Böyle bir temsilci nesne eşdeğer sıralama anahtarları türü arasında tanımlamalısınız [hash_set::key_type (STL/CLR)](../dotnet/hash-set-key-type-stl-clr.md). Yani, herhangi iki tuşları `X` ve `Y`:  
  
 `key_comp()(X, Y)`Her çağrıda aynı Boolean sonucu döndürür.  
  
 Varsa `key_comp()(X, Y) && key_comp()(Y, X)` true ise `X` ve `Y` eşdeğer sıralama sahip söylenir.  
  
 Gibi davranır herhangi bir sıralama kural `operator<=(key_type, key_type)`, `operator>=(key_type, key_type)` veya `operator==(key_type, key_type)` eqivalent sıralama tanımlar.  
  
 Kapsayıcı yalnızca öğeleri eşdeğer sıralama, anahtarlara sahip (ve hangi karma aynı tamsayı değerine) içinde bir demet bitişik olduğunu güvence altına alır. Şablon sınıfı aksine [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md), şablon sınıfın bir nesnesi `hash_multiset` anahtarları tüm öğelerin benzersiz olmasını gerektirmez. (İki veya daha fazla anahtarı eşdeğer sıralama olabilir.)  
  
 Nesne türünde bir saklı temsilci nesne çağırarak belirli bir sıralama anahtarı hangi demet içermesi gereken belirler [hash_set::hasher (STL/CLR)](../dotnet/hash-set-hasher-stl-clr.md). Üye işlevini çağırarak saklı bu nesneye erişim [hash_set::hash_delegate (STL/CLR)](../dotnet/hash-set-hash-delegate-stl-clr.md) `()` anahtar değerine bağlı bir tamsayı değeri elde edilir. Hash_set yapısı oluştururken saklı temsilci nesnesini belirtebilirsiniz; hiçbir temsilci nesnesi belirtirseniz, varsayılan işlevdir `System::Object::hash_value(key_type)`. Yani, herhangi bir anahtarı `X` ve `Y`:  
  
 `hash_delegate()(X)`Her çağrıda aynı tamsayı sonuç döndürür.  
  
 Varsa `X` ve `Y` eşdeğer, sonra sıralama sahip `hash_delegate()(X)` aynı tamsayı sonuç döndürmelidir `hash_delegate()(Y)`.  
  
 Her öğe bir anahtar ve değer görev yapar. Sıra, arama, ekleme ve kaldırma en az örneklerinin en iyi (sabit süresi)--dizisindeki öğelerin sayısı bağımsızdır işlemlerinin sayısı ile rastgele bir öğenin izin veren şekilde gösterilir. Ayrıca, bir öğe eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; bir öğenin kaldırılması yalnızca bu kaldırılan öğeyi gösteren yineleyicileri geçersiz kılar.  
  
 Karma değerler aynı şekilde dağıtılmaz, ancak bir karma tablosu bozuk. Her zaman aynı değer--döndüren bir karma işlev için extreme--arama, ekleme ve kaldırma (doğrusal saati) dizisindeki öğelerin sayısıyla orantılı arasındadır. Makul karma işlevi, ortalama kova boyutu seçmek kapsayıcı endeavors ve karma tablo boyutu (demet toplam sayısı), ancak bu seçenek bir bölümünü veya tamamını kılabilirsiniz. Örneğin, fonksiyonları görmek [hash_set::max_load_factor (STL/CLR)](../dotnet/hash-set-max-load-factor-stl-clr.md) ve [hash_set::rehash (STL/CLR)](../dotnet/hash-set-rehash-stl-clr.md).  
  
 Bir hash_multiset çift yönlü yineleyiciler denetlenen sıradaki öğenin atayan bir yineleyici verilen bitişik öğelerine adım anlamı destekler. Özel bir baş düğüm tarafından döndürülen yineleyici karşılık gelen [hash_multiset::end (STL/CLR)](../dotnet/hash-multiset-end-stl-clr.md)`()`. Denetlenen sıradaki son öğe ulaşmak için bu yineleyici varsa azaltma. Baş düğüm ulaşması hash_multiset yineleyici artırabilirsiniz ve bu ardından eşit karşılaştırır `end()`. Ancak tarafından döndürülen yineleyici başvuramaz `end()`.  
  
 Rasgele erişim yineleyici gerektiren sayısal konumunu--doğrudan verilen hash_multiset öğeye başvuramaz unutmayın.  
  
 Hash_multiset yineleyici sırayla ilişkilendirilmiş kapsayıcısı için bir tanıtıcı depolar onun ilişkili hash_multiset düğümü için bir tanıtıcı depolar. Yalnızca ilişkili kapsayıcı nesneleri ile yineleyiciler kullanabilirsiniz. İlişkili hash_multiset düğümü bazı hash_multiset ile ilişkili olduğu sürece hash_multiset yineleyici geçerli kalır. Ayrıca, geçerli bir yineleyici dereferencable--erişmek veya eşit değil sürece bunu atayan--öğe değeri değiştirmek için kullanmak `end()`.  
  
 Silme veya bir öğe kaldırıldığında yıkıcı depolanan değeri için çağırır. Kapsayıcı yok etme tüm öğeleri siler. Bu nedenle, hiçbir öğe kapsayıcı outlive ref sınıfı öğe türü olan bir kapsayıcı sağlar. Ancak, bir kapsayıcı, tanıtıcısı algılamadığı unutmayın `not` öğeleri yok.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [eşleme (STL/CLR)](../dotnet/map-stl-clr.md)   
 [multiset (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [multiset (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [set (STL/CLR)](../dotnet/set-stl-clr.md)   
 [STL/CLR Kitaplık Başvurusu](../dotnet/stl-clr-library-reference.md)