---
title: "eşleme (STL/CLR) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::map
dev_langs: C++
helpviewer_keywords:
- <map> header [STL/CLR]
- map class [STL/CLR]
- <cliext/map> header [STL/CLR]
ms.assetid: 8b0a7764-b5e4-4175-a802-82b72eb8662a
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6b6e535dac08e473e281f45e45a084d856c931b7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="map-stlclr"></a>eşle (STL/CLR)
Şablon sınıfı çift yönlü erişimi olan öğeleri değişen uzunluk dizisi denetleyen bir nesne tanımlar. Kapsayıcı kullandığınız `map` öğeleri dizisi (neredeyse) dengeli sıralı ağacı düğümleri olarak her bir öğe depolamak yönetmek için. Bir öğenin dizisi ve için kılma gider eşlenen bir değer sıralama için bir anahtar oluşur.  
  
 Aşağıda, açıklamada `GValue` aynıdır:  
  
 `Microsoft::VisualC::StlClr::GenericPair<GKey, GMapped>`  
  
 burada:  
  
 `GKey`aynı `Key` ikinci ref türü olmadıkça olmasından; bu durumda`Key^`  
  
 `GMapped`aynı `Mapped` ikinci ref türü olmadıkça olmasından; bu durumda`Mapped^`  
  
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
|[Map::const_iterator (STL/CLR)](../dotnet/map-const-iterator-stl-clr.md)|Denetlenen dizi için bir sabit yineleyici türü.|  
|[Map::const_reference (STL/CLR)](../dotnet/map-const-reference-stl-clr.md)|Bir öğe için sabit bir başvuru türü.|  
|[Map::const_reverse_iterator (STL/CLR)](../dotnet/map-const-reverse-iterator-stl-clr.md)|Denetimli sırası için sabit bir ters yineleyici türü.|  
|[Map::difference_type (STL/CLR)](../dotnet/map-difference-type-stl-clr.md)|İki öğeler arasında (büyük olasılıkla imzalanmış) bir uzaklık türü.|  
|[Map::generic_container (STL/CLR)](../dotnet/map-generic-container-stl-clr.md)|Genel arabirim kapsayıcının türü.|  
|[Map::generic_iterator (STL/CLR)](../dotnet/map-generic-iterator-stl-clr.md)|Yineleyici kapsayıcısı için genel arabirimi türü.|  
|[Map::generic_reverse_iterator (STL/CLR)](../dotnet/map-generic-reverse-iterator-stl-clr.md)|Kapsayıcı için genel arabirimini ters yineleyici türü.|  
|[Map::generic_value (STL/CLR)](../dotnet/map-generic-value-stl-clr.md)|Kapsayıcı için genel arabirimini öğenin türü.|  
|[Map::iterator (STL/CLR)](../dotnet/map-iterator-stl-clr.md)|Denetlenen dizi için bir yineleyici türü.|  
|[Map::key_compare (STL/CLR)](../dotnet/map-key-compare-stl-clr.md)|İki anahtar sıralama temsilcisi.|  
|[Map::key_type (STL/CLR)](../dotnet/map-key-type-stl-clr.md)|Bir sıralama anahtarının türü.|  
|[Map::mapped_type (STL/CLR)](../dotnet/map-mapped-type-stl-clr.md)|Her anahtar ile ilişkili eşlenen değer türü.|  
|[Map::Reference (STL/CLR)](../dotnet/map-reference-stl-clr.md)|Bir öğe için bir başvuru türü.|  
|[Map::reverse_iterator (STL/CLR)](../dotnet/map-reverse-iterator-stl-clr.md)|Denetimli sırası için ters yineleyici türü.|  
|[Map::size_type (STL/CLR)](../dotnet/map-size-type-stl-clr.md)|İki öğe arasındaki (negatif olmayan) uzaklığı türü.|  
|[Map::value_compare (STL/CLR)](../dotnet/map-value-compare-stl-clr.md)|İki öğenin değerleri için sıralama temsilcisi.|  
|[Map::value_type (STL/CLR)](../dotnet/map-value-type-stl-clr.md)|Öğenin türü.|  
  
|Üye İşlevi|Açıklama|  
|---------------------|-----------------|  
|[Map::Begin (STL/CLR)](../dotnet/map-begin-stl-clr.md)|Denetlenen dizinin başlangıcını belirtir.|  
|[Map::Clear (STL/CLR)](../dotnet/map-clear-stl-clr.md)|Tüm öğeleri kaldırır.|  
|[Map::Count (STL/CLR)](../dotnet/map-count-stl-clr.md)|Belirtilen anahtar eşleşen öğeleri sayar.|  
|[Map::Empty (STL/CLR)](../dotnet/map-empty-stl-clr.md)|Bir öğe olup olmadığını sınar.|  
|[Map::End (STL/CLR)](../dotnet/map-end-stl-clr.md)|Denetlenen dizinin bitişini belirtir.|  
|[Map::equal_range (STL/CLR)](../dotnet/map-equal-range-stl-clr.md)|Belirtilen bir anahtarla eşleşen aralığı bulur.|  
|[Map::ERASE (STL/CLR)](../dotnet/map-erase-stl-clr.md)|Belirtilen konumlardaki öğeleri kaldırır.|  
|[Map::Find (STL/CLR)](../dotnet/map-find-stl-clr.md)|Belirtilen bir anahtarla eşleşen bir öğeyi bulur.|  
|[Map::insert (STL/CLR)](../dotnet/map-insert-stl-clr.md)|Öğeleri ekler.|  
|[Map::key_comp (STL/CLR)](../dotnet/map-key-comp-stl-clr.md)|İki anahtar sıralama temsilcisi kopyalar.|  
|[Map::lower_bound (STL/CLR)](../dotnet/map-lower-bound-stl-clr.md)|Belirtilen anahtarla eşleşen aralığının başlangıcını bulur.|  
|[Map::make_value (STL/CLR)](../dotnet/map-make-value-stl-clr.md)|Bir değer nesnesi oluşturur.|  
|[Map::Map (STL/CLR)](../dotnet/map-map-stl-clr.md)|Bir kapsayıcı nesnesi oluşturur.|  
|[Map::rbegin (STL/CLR)](../dotnet/map-rbegin-stl-clr.md)|Ters denetimli dizisi başlangıcını belirtir.|  
|[Map::rend (STL/CLR)](../dotnet/map-rend-stl-clr.md)|Ters denetimli dizinin sonuna belirler.|  
|[Map::size (STL/CLR)](../dotnet/map-size-stl-clr.md)|Öğe sayısını sayar.|  
|[Map::Swap (STL/CLR)](../dotnet/map-swap-stl-clr.md)|İki kapsayıcının içeriğinin yerini değiştirir.|  
|[Map::to_array (STL/CLR)](../dotnet/map-to-array-stl-clr.md)|Denetimli sırası yeni bir diziye kopyalar.|  
|[Map::upper_bound (STL/CLR)](../dotnet/map-upper-bound-stl-clr.md)|Belirtilen anahtarla eşleşen aralığın sonuna bulur.|  
|[Map::value_comp (STL/CLR)](../dotnet/map-value-comp-stl-clr.md)|İki öğenin değerleri için sıralama temsilci kopyalar.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[Map::operator (STL/CLR) =](../dotnet/map-operator-assign-stl-clr.md)|Denetimli dizisi yerini alır.|  
|[Map::operator(stl/CLR)](../dotnet/map-operator-stl-clr.md)|Bir anahtar ilişkili eşlenen değerine eşler.|  
|[operator! = (map) (STL/CLR)](../dotnet/operator-inequality-map-stl-clr.md)|Belirler bir `map` nesne diğerine eşit değil `map` nesnesi.|  
|[operator < (map) (STL/CLR)](../dotnet/operator-less-than-map-stl-clr.md)|Belirler bir `map` nesnesi, başka değerinden `map` nesnesi.|  
|[operator < = (map) (STL/CLR)](../dotnet/operator-less-or-equal-map-stl-clr.md)|Belirler bir `map` nesnesidir değerinden küçük veya eşit başka `map` nesnesi.|  
|[operator == (map) (STL/CLR)](../dotnet/operator-equality-map-stl-clr.md)|Belirler bir `map` nesnesidir diğerine eşit `map` nesnesi.|  
|[operator > (map) (STL/CLR)](../dotnet/operator-greater-than-map-stl-clr.md)|Belirler bir `map` nesnesidir diğerinden daha büyük `map` nesnesi.|  
|[operator > = (map) (STL/CLR)](../dotnet/operator-greater-or-equal-map-stl-clr.md)|Belirler bir `map` nesnesidir büyük veya ona eşit diğerine `map` nesnesi.|  
  
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
  
 `key_comp()(X, Y)`Her çağrıda aynı Boolean sonucu döndürür.  
  
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