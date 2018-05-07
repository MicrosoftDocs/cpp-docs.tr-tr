---
title: eşleme (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::map
dev_langs:
- C++
helpviewer_keywords:
- <map> header [STL/CLR]
- map class [STL/CLR]
- <cliext/map> header [STL/CLR]
ms.assetid: 8b0a7764-b5e4-4175-a802-82b72eb8662a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cda679ed01e5266f0605639df45940d8f17e506d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="map-stlclr"></a>eşle (STL/CLR)
Şablon sınıfı çift yönlü erişimi olan öğeleri değişen uzunluk dizisi denetleyen bir nesne tanımlar. Kapsayıcı kullandığınız `map` öğeleri dizisi (neredeyse) dengeli sıralı ağacı düğümleri olarak her bir öğe depolamak yönetmek için. Bir öğenin dizisi ve için kılma gider eşlenen bir değer sıralama için bir anahtar oluşur.  
  
 Aşağıda, açıklamada `GValue` aynıdır:  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 burada:  
  
 `GKey` aynı `Key` ikinci ref türü olmadıkça olmasından; bu durumda `Key^`  
  
 `GMapped` aynı `Mapped` ikinci ref türü olmadıkça olmasından; bu durumda `Mapped^`  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Key,  
    typename Mapped>  
    ref class map  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        System::Collections::Generic::IDictionary<Gkey, GMapped>,  
        Microsoft::VisualC::StlClr::ITree<Gkey, GValue>  
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
|[map::const_iterator (STL/CLR)](../dotnet/map-const-iterator-stl-clr.md)|Denetlenen dizi için bir sabit yineleyici türü.|  
|[map::const_reference (STL/CLR)](../dotnet/map-const-reference-stl-clr.md)|Bir öğe için sabit bir başvuru türü.|  
|[map::const_reverse_iterator (STL/CLR)](../dotnet/map-const-reverse-iterator-stl-clr.md)|Denetimli sırası için sabit bir ters yineleyici türü.|  
|[map::difference_type (STL/CLR)](../dotnet/map-difference-type-stl-clr.md)|İki öğeler arasında (büyük olasılıkla imzalanmış) bir uzaklık türü.|  
|[map::generic_container (STL/CLR)](../dotnet/map-generic-container-stl-clr.md)|Genel arabirim kapsayıcının türü.|  
|[map::generic_iterator (STL/CLR)](../dotnet/map-generic-iterator-stl-clr.md)|Yineleyici kapsayıcısı için genel arabirimi türü.|  
|[map::generic_reverse_iterator (STL/CLR)](../dotnet/map-generic-reverse-iterator-stl-clr.md)|Kapsayıcı için genel arabirimini ters yineleyici türü.|  
|[map::generic_value (STL/CLR)](../dotnet/map-generic-value-stl-clr.md)|Kapsayıcı için genel arabirimini öğenin türü.|  
|[map::iterator (STL/CLR)](../dotnet/map-iterator-stl-clr.md)|Denetlenen dizi için bir yineleyici türü.|  
|[map::key_compare (STL/CLR)](../dotnet/map-key-compare-stl-clr.md)|İki anahtar sıralama temsilcisi.|  
|[map::key_type (STL/CLR)](../dotnet/map-key-type-stl-clr.md)|Bir sıralama anahtarının türü.|  
|[map::mapped_type (STL/CLR)](../dotnet/map-mapped-type-stl-clr.md)|Her anahtar ile ilişkili eşlenen değer türü.|  
|[map::reference (STL/CLR)](../dotnet/map-reference-stl-clr.md)|Bir öğe için bir başvuru türü.|  
|[map::reverse_iterator (STL/CLR)](../dotnet/map-reverse-iterator-stl-clr.md)|Denetimli sırası için ters yineleyici türü.|  
|[map::size_type (STL/CLR)](../dotnet/map-size-type-stl-clr.md)|İki öğe arasındaki (negatif olmayan) uzaklığı türü.|  
|[map::value_compare (STL/CLR)](../dotnet/map-value-compare-stl-clr.md)|İki öğenin değerleri için sıralama temsilcisi.|  
|[map::value_type (STL/CLR)](../dotnet/map-value-type-stl-clr.md)|Öğenin türü.|  
  
|Üye İşlevi|Açıklama|  
|---------------------|-----------------|  
|[map::begin (STL/CLR)](../dotnet/map-begin-stl-clr.md)|Denetlenen dizinin başlangıcını belirtir.|  
|[map::clear (STL/CLR)](../dotnet/map-clear-stl-clr.md)|Tüm öğeleri kaldırır.|  
|[map::count (STL/CLR)](../dotnet/map-count-stl-clr.md)|Belirtilen anahtar eşleşen öğeleri sayar.|  
|[map::empty (STL/CLR)](../dotnet/map-empty-stl-clr.md)|Bir öğe olup olmadığını sınar.|  
|[map::end (STL/CLR)](../dotnet/map-end-stl-clr.md)|Denetlenen dizinin bitişini belirtir.|  
|[map::equal_range (STL/CLR)](../dotnet/map-equal-range-stl-clr.md)|Belirtilen bir anahtarla eşleşen aralığı bulur.|  
|[map::erase (STL/CLR)](../dotnet/map-erase-stl-clr.md)|Belirtilen konumlardaki öğeleri kaldırır.|  
|[map::find (STL/CLR)](../dotnet/map-find-stl-clr.md)|Belirtilen bir anahtarla eşleşen bir öğeyi bulur.|  
|[map::insert (STL/CLR)](../dotnet/map-insert-stl-clr.md)|Öğeleri ekler.|  
|[map::key_comp (STL/CLR)](../dotnet/map-key-comp-stl-clr.md)|İki anahtar sıralama temsilcisi kopyalar.|  
|[map::lower_bound (STL/CLR)](../dotnet/map-lower-bound-stl-clr.md)|Belirtilen anahtarla eşleşen aralığının başlangıcını bulur.|  
|[map::make_value (STL/CLR)](../dotnet/map-make-value-stl-clr.md)|Bir değer nesnesi oluşturur.|  
|[map::map (STL/CLR)](../dotnet/map-map-stl-clr.md)|Bir kapsayıcı nesnesi oluşturur.|  
|[map::rbegin (STL/CLR)](../dotnet/map-rbegin-stl-clr.md)|Ters denetimli dizisi başlangıcını belirtir.|  
|[map::rend (STL/CLR)](../dotnet/map-rend-stl-clr.md)|Ters denetimli dizinin sonuna belirler.|  
|[map::size (STL/CLR)](../dotnet/map-size-stl-clr.md)|Öğe sayısını sayar.|  
|[map::swap (STL/CLR)](../dotnet/map-swap-stl-clr.md)|İki kapsayıcının içeriğinin yerini değiştirir.|  
|[map::to_array (STL/CLR)](../dotnet/map-to-array-stl-clr.md)|Denetimli sırası yeni bir diziye kopyalar.|  
|[map::upper_bound (STL/CLR)](../dotnet/map-upper-bound-stl-clr.md)|Belirtilen anahtarla eşleşen aralığın sonuna bulur.|  
|[map::value_comp (STL/CLR)](../dotnet/map-value-comp-stl-clr.md)|İki öğenin değerleri için sıralama temsilci kopyalar.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[map::operator= (STL/CLR)](../dotnet/map-operator-assign-stl-clr.md)|Denetimli dizisi yerini alır.|  
|[map::operator(STL/CLR)](../dotnet/map-operator-stl-clr.md)|Bir anahtar ilişkili eşlenen değerine eşler.|  
|[operator!= (map) (STL/CLR)](../dotnet/operator-inequality-map-stl-clr.md)|Belirler bir `map` nesne diğerine eşit değil `map` nesnesi.|  
|[operator< (map) (STL/CLR)](../dotnet/operator-less-than-map-stl-clr.md)|Belirler bir `map` nesnesi, başka değerinden `map` nesnesi.|  
|[operator<= (map) (STL/CLR)](../dotnet/operator-less-or-equal-map-stl-clr.md)|Belirler bir `map` nesnesidir değerinden küçük veya eşit başka `map` nesnesi.|  
|[operator== (map) (STL/CLR)](../dotnet/operator-equality-map-stl-clr.md)|Belirler bir `map` nesnesidir diğerine eşit `map` nesnesi.|  
|[operator> (map) (STL/CLR)](../dotnet/operator-greater-than-map-stl-clr.md)|Belirler bir `map` nesnesidir diğerinden daha büyük `map` nesnesi.|  
|[operator>= (map) (STL/CLR)](../dotnet/operator-greater-or-equal-map-stl-clr.md)|Belirler bir `map` nesnesidir büyük veya ona eşit diğerine `map` nesnesi.|  
  
## <a name="interfaces"></a>Arabirimler  
  
|Arabirim|Açıklama|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Yinelenen bir nesne.|  
|<xref:System.Collections.IEnumerable>|Öğeleri dizisi.|  
|<xref:System.Collections.ICollection>|Öğeleri grubunu koruyun.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Yazılan öğeleri dizisi.|  
|<xref:System.Collections.Generic.ICollection%601>|Yazılı öğeleri grubunu koruyun.|  
|<xref:System.Collections.Generic.IDictionary%602>|{Anahtar, değer} grubunun korumak çiftleri.|  
|ITree < anahtar, değer >|Genel kapsayıcı korur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Nesne ayırır ve bireysel düğümleri olarak denetimleri dizisi için depolama boşaltır. Hiçbir zaman kopyalayarak bir düğümün içeriğini başka düğümler arasındaki bağlantılar değiştirilerek sıralı tutar (neredeyse) dengeli bir ağaç öğeleri ekler. INSERT ve rahatsız edici kalan öğeleri olmadan serbestçe öğeleri Kaldır anlamına gelir.  
  
 Nesne denetleyen bir saklı temsilci nesne türü çağırarak dizisi siparişleri [map::key_compare (STL/CLR)](../dotnet/map-key-compare-stl-clr.md). Harita oluşturmak zaman saklı temsilci nesnesini belirtebilirsiniz; hiçbir temsilci nesnesi belirtirseniz, karşılaştırma varsayılandır `operator<(key_type, key_type)`. Üye işlevini çağırarak saklı bu nesneye erişim [map::key_comp (STL/CLR)](../dotnet/map-key-comp-stl-clr.md)`()`.  
  
 Böyle bir temsilci nesnenin katı bir zayıf türü anahtarları sıralama zorunlu tuttukları gerekir [map::key_type (STL/CLR)](../dotnet/map-key-type-stl-clr.md). Yani, herhangi iki tuşları `X` ve `Y`:  
  
 `key_comp()(X, Y)` Her çağrıda aynı Boolean sonucu döndürür.  
  
 Varsa `key_comp()(X, Y)` true ise `key_comp()(Y, X)` false olmalıdır.  
  
 Varsa `key_comp()(X, Y)` true ise `X` önce sıralanmalıdır söylenir `Y`.  
  
 Varsa `!key_comp()(X, Y) && !key_comp()(Y, X)` true ise `X` ve `Y` eşdeğer sıralama sahip söylenir.  
  
 Herhangi bir öğe için `X` , önündeki `Y` denetlenen sıradaki `key_comp()(Y, X)` false olur. (Varsayılan temsilci nesnesi için anahtarları hiçbir zaman değerini azaltın.) Şablon sınıfı aksine [harita](../dotnet/map-stl-clr.md), şablon sınıfın bir nesnesi `map` anahtarları tüm öğelerin benzersiz olmasını gerektirmez. (İki veya daha fazla anahtarı eşdeğer sıralama olabilir.)  
  
 Her öğe ayrı bir anahtar ve eşlenen bir değer içeriyor. Sıra, arama, ekleme ve kaldırma işlemlerini öğe sayısını logaritmasını orantılı çeşitli rasgele bir öğenin dizisi (Logaritmik saati) izin veren şekilde gösterilir. Ayrıca, bir öğe eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; bir öğenin kaldırılması yalnızca bu kaldırılan öğeyi gösteren yineleyicileri geçersiz kılar.  
  
 Bir harita çift yönlü yineleyiciler denetlenen sıradaki öğenin atayan bir yineleyici verilen bitişik öğelerine adım anlamı destekler. Özel bir baş düğüm tarafından döndürülen yineleyici karşılık gelen [map::end (STL/CLR)](../dotnet/map-end-stl-clr.md)`()`. Denetlenen sıradaki son öğe ulaşmak için bu yineleyici varsa azaltma. Baş düğüm ulaşmak için bir harita yineleyici artırabilirsiniz ve bu ardından eşit karşılaştırır `end()`. Ancak tarafından döndürülen yineleyici başvuramaz `end()`.  
  
 Rasgele erişim yineleyici gerektiren sayısal konumunu--doğrudan verilen bir harita öğesi başvuramaz unutmayın.  
  
 Bir harita yineleyici sırayla ilişkilendirilmiş kapsayıcısı için bir tanıtıcı depolar, ilişkili eşleme düğümü için bir tanıtıcı depolar. Yalnızca ilişkili kapsayıcı nesneleri ile yineleyiciler kullanabilirsiniz. İlişkili harita düğümü bazı Haritası ilişkili olduğu sürece bir harita yineleyici geçerli kalır. Ayrıca, geçerli bir yineleyici dereferencable--erişmek veya eşit değil sürece bunu atayan--öğe değeri değiştirmek için kullanmak `end()`.  
  
 Silme veya bir öğe kaldırıldığında yıkıcı depolanan değeri için çağırır. Kapsayıcı yok etme tüm öğeleri siler. Bu nedenle, hiçbir öğe kapsayıcı outlive ref sınıfı öğe türü olan bir kapsayıcı sağlar. Ancak, bir kapsayıcı, tanıtıcısı algılamadığı unutmayın `not` öğeleri yok.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [eşleme](../dotnet/map-stl-clr.md)   
 [multiset (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [set (STL/CLR)](../dotnet/set-stl-clr.md)   
 [STL/CLR Kitaplık Başvurusu](../dotnet/stl-clr-library-reference.md)