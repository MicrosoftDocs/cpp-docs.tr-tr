---
title: hash_map (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_map
dev_langs:
- C++
helpviewer_keywords:
- <cliext/hash_map> header [STL/CLR]
- <hash_map> header [STL/CLR]
- hash_map class [STL/CLR]
ms.assetid: c3cfc69b-04c6-42ae-a30e-0eda953fe883
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ad09cf718e2e76cbed99c5628a3eafc5104ad03f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="hashmap-stlclr"></a>hash_map (STL/CLR)
Şablon sınıfı çift yönlü erişimi olan öğeleri değişen uzunluk dizisi denetleyen bir nesne tanımlar. Kapsayıcı kullandığınız `hash_map` bir çift yönlü depolama her tablo girişi öğeleri dizisi bir karma tablosu olarak yönetmek için düğümleri ve tek bir öğede depolama her düğüm listesi bağlı. Bir öğenin dizisi ve için kılma gider eşlenen bir değer sıralama için bir anahtar oluşur.  
  
 Aşağıda, açıklamada `GValue` aynıdır:  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 burada:  
  
 `GKey` aynı `Key` ikinci ref türü olmadıkça olmasından; bu durumda `Key^`  
  
 `GMapped` aynı `Mapped` ikinci ref türü olmadıkça olmasından; bu durumda `Mapped^`  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Key,  
    typename Mapped>  
    ref class hash_map  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        System::Collections::Generic::IDictionary<Gkey, GMapped>,  
        Microsoft::VisualC::StlClr::IHash<Gkey, GValue>  
    { ..... };  
```  
  
#### <a name="parameters"></a>Parametreler  
 Anahtar  
 Anahtar bileşeni denetlenen sıradaki öğenin türü.  
  
 eşlenen  
 Ek bileşen denetlenen sıradaki öğenin türü.  
  
## <a name="members"></a>Üyeler  
  
|Tür Tanımlaması|Açıklama|  
|---------------------|-----------------|  
|[hash_map::const_iterator (STL/CLR)](../dotnet/hash-map-const-iterator-stl-clr.md)|Denetlenen dizi için bir sabit yineleyici türü.|  
|[hash_map::const_reference (STL/CLR)](../dotnet/hash-map-const-reference-stl-clr.md)|Bir öğe için sabit bir başvuru türü.|  
|[hash_map::const_reverse_iterator (STL/CLR)](../dotnet/hash-map-const-reverse-iterator-stl-clr.md)|Denetimli sırası için sabit bir ters yineleyici türü.|  
|[hash_map::difference_type (STL/CLR)](../dotnet/hash-map-difference-type-stl-clr.md)|İki öğeler arasında (büyük olasılıkla imzalanmış) bir uzaklık türü.|  
|[hash_map::generic_container (STL/CLR)](../dotnet/hash-map-generic-container-stl-clr.md)|Genel arabirim kapsayıcının türü.|  
|[hash_map::generic_iterator (STL/CLR)](../dotnet/hash-map-generic-iterator-stl-clr.md)|Yineleyici kapsayıcısı için genel arabirimi türü.|  
|[hash_map::generic_reverse_iterator (STL/CLR)](../dotnet/hash-map-generic-reverse-iterator-stl-clr.md)|Kapsayıcı için genel arabirimini ters yineleyici türü.|  
|[hash_map::generic_value (STL/CLR)](../dotnet/hash-map-generic-value-stl-clr.md)|Kapsayıcı için genel arabirimini öğenin türü.|  
|[hash_map::hasher (STL/CLR)](../dotnet/hash-map-hasher-stl-clr.md)|Bir anahtar için karma temsilcisi.|  
|[hash_map::iterator (STL/CLR)](../dotnet/hash-map-iterator-stl-clr.md)|Denetlenen dizi için bir yineleyici türü.|  
|[hash_map::key_compare (STL/CLR)](../dotnet/hash-map-key-compare-stl-clr.md)|İki anahtar sıralama temsilcisi.|  
|[hash_map::key_type (STL/CLR)](../dotnet/hash-map-key-type-stl-clr.md)|Bir sıralama anahtarının türü.|  
|[hash_map::mapped_type (STL/CLR)](../dotnet/hash-map-mapped-type-stl-clr.md)|Her anahtar ile ilişkili eşlenen değer türü.|  
|[hash_map::reference (STL/CLR)](../dotnet/hash-map-reference-stl-clr.md)|Bir öğe için bir başvuru türü.|  
|[hash_map::reverse_iterator (STL/CLR)](../dotnet/hash-map-reverse-iterator-stl-clr.md)|Denetimli sırası için ters yineleyici türü.|  
|[hash_map::size_type (STL/CLR)](../dotnet/hash-map-size-type-stl-clr.md)|İki öğe arasındaki (negatif olmayan) uzaklığı türü.|  
|[hash_map::value_compare (STL/CLR)](../dotnet/hash-map-value-compare-stl-clr.md)|İki öğenin değerleri için sıralama temsilcisi.|  
|[hash_map::value_type (STL/CLR)](../dotnet/hash-map-value-type-stl-clr.md)|Öğenin türü.|  
  
|Üye İşlevi|Açıklama|  
|---------------------|-----------------|  
|[hash_map::begin (STL/CLR)](../dotnet/hash-map-begin-stl-clr.md)|Denetlenen dizinin başlangıcını belirtir.|  
|[hash_map::bucket_count (STL/CLR)](../dotnet/hash-map-bucket-count-stl-clr.md)|Demet sayar.|  
|[hash_map::clear (STL/CLR)](../dotnet/hash-map-clear-stl-clr.md)|Tüm öğeleri kaldırır.|  
|[hash_map::count (STL/CLR)](../dotnet/hash-map-count-stl-clr.md)|Belirtilen anahtar eşleşen öğeleri sayar.|  
|[hash_map::empty (STL/CLR)](../dotnet/hash-map-empty-stl-clr.md)|Bir öğe olup olmadığını sınar.|  
|[hash_map::end (STL/CLR)](../dotnet/hash-map-end-stl-clr.md)|Denetlenen dizinin bitişini belirtir.|  
|[hash_map::equal_range (STL/CLR)](../dotnet/hash-map-equal-range-stl-clr.md)|Belirtilen bir anahtarla eşleşen aralığı bulur.|  
|[hash_map::erase (STL/CLR)](../dotnet/hash-map-erase-stl-clr.md)|Belirtilen konumlardaki öğeleri kaldırır.|  
|[hash_map::find (STL/CLR)](../dotnet/hash-map-find-stl-clr.md)|Belirtilen bir anahtarla eşleşen bir öğeyi bulur.|  
|[hash_map::hash_delegate (STL/CLR)](../dotnet/hash-map-hash-delegate-stl-clr.md)|Bir anahtar için karma temsilci kopyalar.|  
|[hash_map::hash_map (STL/CLR)](../dotnet/hash-map-hash-map-stl-clr.md)|Bir kapsayıcı nesnesi oluşturur.|  
|[hash_map::insert (STL/CLR)](../dotnet/hash-map-insert-stl-clr.md)|Öğeleri ekler.|  
|[hash_map::key_comp (STL/CLR)](../dotnet/hash-map-key-comp-stl-clr.md)|İki anahtar sıralama temsilcisi kopyalar.|  
|[hash_map::load_factor (STL/CLR)](../dotnet/hash-map-load-factor-stl-clr.md)|Demet başına ortalama öğeyi sayar.|  
|[hash_map::lower_bound (STL/CLR)](../dotnet/hash-map-lower-bound-stl-clr.md)|Belirtilen anahtarla eşleşen aralığının başlangıcını bulur.|  
|[hash_map::make_value (STL/CLR)](../dotnet/hash-map-make-value-stl-clr.md)|Bir değer nesnesi oluşturur.|  
|[hash_map::max_load_factor (STL/CLR)](../dotnet/hash-map-max-load-factor-stl-clr.md)|Demet başına en yüksek öğe sayısını alır veya ayarlar.|  
|[hash_map::rbegin (STL/CLR)](../dotnet/hash-map-rbegin-stl-clr.md)|Ters denetimli dizisi başlangıcını belirtir.|  
|[hash_map::rehash (STL/CLR)](../dotnet/hash-map-rehash-stl-clr.md)|Karma tabloyu yeniden oluşturur.|  
|[hash_map::rend (STL/CLR)](../dotnet/hash-map-rend-stl-clr.md)|Ters denetimli dizinin sonuna belirler.|  
|[hash_map::size (STL/CLR)](../dotnet/hash-map-size-stl-clr.md)|Öğe sayısını sayar.|  
|[hash_map::swap (STL/CLR)](../dotnet/hash-map-swap-stl-clr.md)|İki kapsayıcının içeriğinin yerini değiştirir.|  
|[hash_map::to_array (STL/CLR)](../dotnet/hash-map-to-array-stl-clr.md)|Denetimli sırası yeni bir diziye kopyalar.|  
|[hash_map::upper_bound (STL/CLR)](../dotnet/hash-map-upper-bound-stl-clr.md)|Belirtilen anahtarla eşleşen aralığın sonuna bulur.|  
|[hash_map::value_comp (STL/CLR)](../dotnet/hash-map-value-comp-stl-clr.md)|İki öğenin değerleri için sıralama temsilci kopyalar.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[hash_map::operator= (STL/CLR)](../dotnet/hash-map-operator-assign-stl-clr.md)|Denetimli dizisi yerini alır.|  
|[hash_map::operator(STL/CLR)](../dotnet/hash-map-operator-stl-clr.md)|Bir anahtar ilişkili eşlenen değerine eşler.|  
  
## <a name="interfaces"></a>Arabirimler  
  
|Arabirim|Açıklama|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Yinelenen bir nesne.|  
|<xref:System.Collections.IEnumerable>|Öğeleri dizisi.|  
|<xref:System.Collections.ICollection>|Öğeleri grubunu koruyun.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Yazılan öğeleri dizisi.|  
|<xref:System.Collections.Generic.ICollection%601>|Yazılı öğeleri grubunu koruyun.|  
|<xref:System.Collections.Generic.IDictionary%602>|{Anahtar, değer} grubunun korumak çiftleri.|  
|IHash < anahtar, değer >|Genel kapsayıcı korur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Nesne ayırır ve bağlı bir çift yönlü listedeki tek düğümler olarak denetlediği dizisi için depolama boşaltır. Erişimi hızlandırmak için nesne da verimli tüm liste alt listelerin, bir dizi yönetme bir değişen uzunluk dizisi işaretçileri (karma tablosu), listeye tutar veya aralıkları. Hiçbir zaman kopyalayarak bir düğümün içeriğini başka düğümler arasındaki bağlantılar değiştirilerek sıralı tutan kova öğeleri ekler. INSERT ve rahatsız edici kalan öğeleri olmadan serbestçe öğeleri Kaldır anlamına gelir.  
  
 Nesne tarafından denetlenen bir saklı temsilci nesne türü çağırarak her demet siparişleri [hash_set::key_compare (STL/CLR)](../dotnet/hash-set-key-compare-stl-clr.md). Hash_set yapısı oluştururken saklı temsilci nesnesini belirtebilirsiniz; hiçbir temsilci nesnesi belirtirseniz, karşılaştırma varsayılandır `operator<=(key_type, key_type)`.  
  
 Üye işlevini çağırarak saklı temsilci nesneye erişim [hash_set::key_comp (STL/CLR)](../dotnet/hash-set-key-comp-stl-clr.md)`()`. Böyle bir temsilci nesne eşdeğer sıralama anahtarları türü arasında tanımlamalısınız [hash_set::key_type (STL/CLR)](../dotnet/hash-set-key-type-stl-clr.md). Yani, herhangi iki tuşları `X` ve `Y`:  
  
 `key_comp()(X, Y)` Her çağrıda aynı Boolean sonucu döndürür.  
  
 Varsa `key_comp()(X, Y) && key_comp()(Y, X)` true ise `X` ve `Y` eşdeğer sıralama sahip söylenir.  
  
 Gibi davranır herhangi bir sıralama kural `operator<=(key_type, key_type)`, `operator>=(key_type, key_type)` veya `operator==(key_type, key_type)` eqivalent sıralama tanımlar.  
  
 Kapsayıcı yalnızca öğeleri eşdeğer sıralama, anahtarlara sahip (ve hangi karma aynı tamsayı değerine) içinde bir demet bitişik olduğunu güvence altına alır. Şablon sınıfı aksine [hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md), şablon sınıfın bir nesnesi `hash_map` anahtarları tüm öğelerin benzersiz olmasını sağlar. (Eşdeğer sıralama hiçbir iki anahtarı vardır.)  
  
 Nesne türünde bir saklı temsilci nesne çağırarak belirli bir sıralama anahtarı hangi demet içermesi gereken belirler [hash_set::hasher (STL/CLR)](../dotnet/hash-set-hasher-stl-clr.md). Üye işlevini çağırarak saklı bu nesneye erişim [hash_set::hash_delegate (STL/CLR)](../dotnet/hash-set-hash-delegate-stl-clr.md) `()` anahtar değerine bağlı bir tamsayı değeri elde edilir. Hash_set yapısı oluştururken saklı temsilci nesnesini belirtebilirsiniz; hiçbir temsilci nesnesi belirtirseniz, varsayılan işlevdir `System::Object::hash_value(key_type)`. Yani, herhangi bir anahtarı `X` ve `Y`:  
  
 `hash_delegate()(X)` Her çağrıda aynı tamsayı sonuç döndürür.  
  
 Varsa `X` ve `Y` eşdeğer, sonra sıralama sahip `hash_delegate()(X)` aynı tamsayı sonuç döndürmelidir `hash_delegate()(Y)`.  
  
 Her öğe ayrı bir anahtar ve eşlenen bir değer içeriyor. Sıra, arama, ekleme ve kaldırma en az örneklerinin en iyi (sabit süresi)--dizisindeki öğelerin sayısı bağımsızdır işlemlerinin sayısı ile rastgele bir öğenin izin veren şekilde gösterilir. Ayrıca, bir öğe eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; bir öğenin kaldırılması yalnızca bu kaldırılan öğeyi gösteren yineleyicileri geçersiz kılar.  
  
 Karma değerler aynı şekilde dağıtılmaz, ancak bir karma tablosu bozuk. Her zaman aynı değer--döndüren bir karma işlev için extreme--arama, ekleme ve kaldırma (doğrusal saati) dizisindeki öğelerin sayısıyla orantılı arasındadır. Makul karma işlevi, ortalama kova boyutu seçmek kapsayıcı endeavors ve karma tablo boyutu (demet toplam sayısı), ancak bu seçenek bir bölümünü veya tamamını kılabilirsiniz. Örneğin, fonksiyonları görmek [hash_set::max_load_factor (STL/CLR)](../dotnet/hash-set-max-load-factor-stl-clr.md) ve [hash_set::rehash (STL/CLR)](../dotnet/hash-set-rehash-stl-clr.md).  
  
 Bir hash_map çift yönlü yineleyiciler denetlenen sıradaki öğenin atayan bir yineleyici verilen bitişik öğelerine adım anlamı destekler. Özel bir baş düğüm tarafından döndürülen yineleyici karşılık gelen [hash_map::end (STL/CLR)](../dotnet/hash-map-end-stl-clr.md)`()`. Denetlenen sıradaki son öğe ulaşmak için bu yineleyici varsa azaltma. Baş düğüm ulaşması hash_map yineleyici artırabilirsiniz ve bu ardından eşit karşılaştırır `end()`. Ancak tarafından döndürülen yineleyici başvuramaz `end()`.  
  
 Rasgele erişim yineleyici gerektiren sayısal konumunu--doğrudan verilen hash_map öğeye başvuramaz unutmayın.  
  
 Hash_map yineleyici sırayla ilişkilendirilmiş kapsayıcısı için bir tanıtıcı depolar onun ilişkili hash_map düğümü için bir tanıtıcı depolar. Yalnızca ilişkili kapsayıcı nesneleri ile yineleyiciler kullanabilirsiniz. İlişkili hash_map düğümü bazı hash_map ile ilişkili olduğu sürece hash_map yineleyici geçerli kalır. Ayrıca, geçerli bir yineleyici dereferencable--erişmek veya eşit değil sürece bunu atayan--öğe değeri değiştirmek için kullanmak `end()`.  
  
 Silme veya bir öğe kaldırıldığında yıkıcı depolanan değeri için çağırır. Kapsayıcı yok etme tüm öğeleri siler. Bu nedenle, hiçbir öğe kapsayıcı outlive ref sınıfı öğe türü olan bir kapsayıcı sağlar. Ancak, bir kapsayıcı, tanıtıcısı algılamadığı unutmayın `not` öğeleri yok.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [hash_map](../dotnet/hash-map-stl-clr.md)   
 [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [eşleme (STL/CLR)](../dotnet/map-stl-clr.md)   
 [multimap (STL/CLR)](../dotnet/multimap-stl-clr.md)   
 [multiset (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [set (STL/CLR)](../dotnet/set-stl-clr.md)   
 [STL/CLR Kitaplık Başvurusu](../dotnet/stl-clr-library-reference.md)