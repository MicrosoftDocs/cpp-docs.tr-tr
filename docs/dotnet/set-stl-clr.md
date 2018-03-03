---
title: (STL/CLR) ayarlama | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::set
dev_langs:
- C++
helpviewer_keywords:
- <cliext/set> header [STL/CLR]
- <set> header [STL/CLR]
- set class [STL/CLR]
ms.assetid: 27d3628c-741a-43a7-bef1-5085536f679e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9624f08c54629657e7f52c2c688d2083aa557a56
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="set-stlclr"></a>set (STL/CLR)
Şablon sınıfı çift yönlü erişimi olan öğeleri değişen uzunluk dizisi denetleyen bir nesne tanımlar. Kapsayıcı kullandığınız `set` öğeleri dizisi (neredeyse) dengeli sıralı ağacı düğümleri olarak her bir öğe depolamak yönetmek için.  
  
 Aşağıda, açıklamada `GValue` aynı `GKey`, sırayla olduğu aynı `Key` ikinci ref türü olmadıkça olmasından; bu durumda `Key^`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Key>  
    ref class set  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::ITree<Gkey, GValue>  
    { ..... };  
```  
  
#### <a name="parameters"></a>Parametreler  
 Anahtar  
 Anahtar bileşeni denetlenen sıradaki öğenin türü.  
  
## <a name="members"></a>Üyeler  
  
|Tür Tanımlaması|Açıklama|  
|---------------------|-----------------|  
|[set::const_iterator (STL/CLR)](../dotnet/set-const-iterator-stl-clr.md)|Denetlenen dizi için bir sabit yineleyici türü.|  
|[set::const_reference (STL/CLR)](../dotnet/set-const-reference-stl-clr.md)|Bir öğe için sabit bir başvuru türü.|  
|[set::const_reverse_iterator (STL/CLR)](../dotnet/set-const-reverse-iterator-stl-clr.md)|Denetimli sırası için sabit bir ters yineleyici türü.|  
|[set::difference_type (STL/CLR)](../dotnet/set-difference-type-stl-clr.md)|İki öğeler arasında (büyük olasılıkla imzalanmış) bir uzaklık türü.|  
|[set::generic_container (STL/CLR)](../dotnet/set-generic-container-stl-clr.md)|Genel arabirim kapsayıcının türü.|  
|[set::generic_iterator (STL/CLR)](../dotnet/set-generic-iterator-stl-clr.md)|Yineleyici kapsayıcısı için genel arabirimi türü.|  
|[set::generic_reverse_iterator (STL/CLR)](../dotnet/set-generic-reverse-iterator-stl-clr.md)|Kapsayıcı için genel arabirimini ters yineleyici türü.|  
|[set::generic_value (STL/CLR)](../dotnet/set-generic-value-stl-clr.md)|Kapsayıcı için genel arabirimini öğenin türü.|  
|[set::iterator (STL/CLR)](../dotnet/set-iterator-stl-clr.md)|Denetlenen dizi için bir yineleyici türü.|  
|[set::key_compare (STL/CLR)](../dotnet/set-key-compare-stl-clr.md)|İki anahtar sıralama temsilcisi.|  
|[set::key_type (STL/CLR)](../dotnet/set-key-type-stl-clr.md)|Bir sıralama anahtarının türü.|  
|[set::reference (STL/CLR)](../dotnet/set-reference-stl-clr.md)|Bir öğe için bir başvuru türü.|  
|[set::reverse_iterator (STL/CLR)](../dotnet/set-reverse-iterator-stl-clr.md)|Denetimli sırası için ters yineleyici türü.|  
|[set::size_type (STL/CLR)](../dotnet/set-size-type-stl-clr.md)|İki öğe arasındaki (negatif olmayan) uzaklığı türü.|  
|[set::value_compare (STL/CLR)](../dotnet/set-value-compare-stl-clr.md)|İki öğenin değerleri için sıralama temsilcisi.|  
|[set::value_type (STL/CLR)](../dotnet/set-value-type-stl-clr.md)|Öğenin türü.|  
  
|Üye İşlevi|Açıklama|  
|---------------------|-----------------|  
|[set::begin (STL/CLR)](../dotnet/set-begin-stl-clr.md)|Denetlenen dizinin başlangıcını belirtir.|  
|[set::clear (STL/CLR)](../dotnet/set-clear-stl-clr.md)|Tüm öğeleri kaldırır.|  
|[set::count (STL/CLR)](../dotnet/set-count-stl-clr.md)|Belirtilen anahtar eşleşen öğeleri sayar.|  
|[set::empty (STL/CLR)](../dotnet/set-empty-stl-clr.md)|Bir öğe olup olmadığını sınar.|  
|[set::end (STL/CLR)](../dotnet/set-end-stl-clr.md)|Denetlenen dizinin bitişini belirtir.|  
|[set::equal_range (STL/CLR)](../dotnet/set-equal-range-stl-clr.md)|Belirtilen bir anahtarla eşleşen aralığı bulur.|  
|[set::erase (STL/CLR)](../dotnet/set-erase-stl-clr.md)|Belirtilen konumlardaki öğeleri kaldırır.|  
|[set::find (STL/CLR)](../dotnet/set-find-stl-clr.md)|Belirtilen bir anahtarla eşleşen bir öğeyi bulur.|  
|[set::insert (STL/CLR)](../dotnet/set-insert-stl-clr.md)|Öğeleri ekler.|  
|[set::key_comp (STL/CLR)](../dotnet/set-key-comp-stl-clr.md)|İki anahtar sıralama temsilcisi kopyalar.|  
|[set::lower_bound (STL/CLR)](../dotnet/set-lower-bound-stl-clr.md)|Belirtilen anahtarla eşleşen aralığının başlangıcını bulur.|  
|[set::make_value (STL/CLR)](../dotnet/set-make-value-stl-clr.md)|Bir değer nesnesi oluşturur.|  
|[set::rbegin (STL/CLR)](../dotnet/set-rbegin-stl-clr.md)|Ters denetimli dizisi başlangıcını belirtir.|  
|[set::rend (STL/CLR)](../dotnet/set-rend-stl-clr.md)|Ters denetimli dizinin sonuna belirler.|  
|[set::set (STL/CLR)](../dotnet/set-set-stl-clr.md)|Bir kapsayıcı nesnesi oluşturur.|  
|[set::size (STL/CLR)](../dotnet/set-size-stl-clr.md)|Öğe sayısını sayar.|  
|[set::swap (STL/CLR)](../dotnet/set-swap-stl-clr.md)|İki kapsayıcının içeriğinin yerini değiştirir.|  
|[set::to_array (STL/CLR)](../dotnet/set-to-array-stl-clr.md)|Denetimli sırası yeni bir diziye kopyalar.|  
|[set::upper_bound (STL/CLR)](../dotnet/set-upper-bound-stl-clr.md)|Belirtilen anahtarla eşleşen aralığın sonuna bulur.|  
|[set::value_comp (STL/CLR)](../dotnet/set-value-comp-stl-clr.md)|İki öğenin değerleri için sıralama temsilci kopyalar.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[set::operator= (STL/CLR)](../dotnet/set-operator-assign-stl-clr.md)|Denetimli dizisi yerini alır.|  
|[operator!= (set) (STL/CLR)](../dotnet/operator-inequality-set-stl-clr.md)|Belirler bir `set` nesne diğerine eşit değil `set` nesnesi.|  
|[operator< (set) (STL/CLR)](../dotnet/operator-less-than-set-stl-clr.md)|Belirler bir `set` nesnesi, başka değerinden `set` nesnesi.|  
|[operator<= (set) (STL/CLR)](../dotnet/operator-less-or-equal-set-stl-clr.md)|Belirler bir `set` nesnesidir değerinden küçük veya eşit başka `set` nesnesi.|  
|[operator== (set) (STL/CLR)](../dotnet/operator-equality-set-stl-clr.md)|Belirler bir `set` nesnesidir diğerine eşit `set` nesnesi.|  
|[operator> (set) (STL/CLR)](../dotnet/operator-greater-than-set-stl-clr.md)|Belirler bir `set` nesnesidir diğerinden daha büyük `set` nesnesi.|  
|[operator>= (set) (STL/CLR)](../dotnet/operator-greater-or-equal-set-stl-clr.md)|Belirler bir `set` nesnesidir büyük veya ona eşit diğerine `set` nesnesi.|  
  
## <a name="interfaces"></a>Arabirimler  
  
|Arabirim|Açıklama|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Yinelenen bir nesne.|  
|<xref:System.Collections.IEnumerable>|Öğeleri dizisi.|  
|<xref:System.Collections.ICollection>|Öğeleri grubunu koruyun.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Yazılan öğeleri dizisi.|  
|<xref:System.Collections.Generic.ICollection%601>|Yazılı öğeleri grubunu koruyun.|  
|ITree\<anahtar, değer >|Genel kapsayıcı korur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Nesne ayırır ve bireysel düğümleri olarak denetimleri dizisi için depolama boşaltır. Hiçbir zaman kopyalayarak bir düğümün içeriğini başka düğümler arasındaki bağlantılar değiştirilerek sıralı tutar (neredeyse) dengeli bir ağaç öğeleri ekler. INSERT ve rahatsız edici kalan öğeleri olmadan serbestçe öğeleri Kaldır anlamına gelir.  
  
 Nesne denetleyen bir saklı temsilci nesne türü çağırarak dizisi siparişleri [set::key_compare (STL/CLR)](../dotnet/set-key-compare-stl-clr.md). Küme oluşturmak zaman saklı temsilci nesnesini belirtebilirsiniz; hiçbir temsilci nesnesi belirtirseniz, karşılaştırma varsayılandır `operator<(key_type, key_type)`. Üye işlevini çağırarak saklı bu nesneye erişim [set::key_comp (STL/CLR)](../dotnet/set-key-comp-stl-clr.md)`()`.  
  
 Böyle bir temsilci nesnenin katı bir zayıf türü anahtarları sıralama zorunlu tuttukları gerekir [set::key_type (STL/CLR)](../dotnet/set-key-type-stl-clr.md). Yani, herhangi iki tuşları `X` ve `Y`:  
  
 `key_comp()(X, Y)`Her çağrıda aynı Boolean sonucu döndürür.  
  
 Varsa `key_comp()(X, Y)` true ise `key_comp()(Y, X)` false olmalıdır.  
  
 Varsa `key_comp()(X, Y)` true ise `X` önce sıralanmalıdır söylenir `Y`.  
  
 Varsa `!key_comp()(X, Y) && !key_comp()(Y, X)` true ise `X` ve `Y` eşdeğer sıralama sahip söylenir.  
  
 Herhangi bir öğe için `X` , önündeki `Y` denetlenen sıradaki `key_comp()(Y, X)` false olur. (Varsayılan temsilci nesnesi için anahtarları hiçbir zaman değerini azaltın.) Şablon sınıfı aksine [ayarlamak](../dotnet/set-stl-clr.md), şablon sınıfın bir nesnesi `set` anahtarları tüm öğelerin benzersiz olmasını gerektirmez. (İki veya daha fazla anahtarı eşdeğer sıralama olabilir.)  
  
 Her öğe bir tuş hem de bir değer olarak görev yapar. Sıra, arama, ekleme ve kaldırma işlemlerini öğe sayısını logaritmasını orantılı çeşitli rasgele bir öğenin dizisi (Logaritmik saati) izin veren şekilde gösterilir. Ayrıca, bir öğe eklenmesi hiçbir yineleyiciyi geçersiz kılmaz; bir öğenin kaldırılması yalnızca bu kaldırılan öğeyi gösteren yineleyicileri geçersiz kılar.  
  
 Denetlenen sıradaki öğenin atayan bir yineleyici verilen bitişik öğelerine adım anlamına gelir kümesi, çift yönlü yineleyiciler destekler. Özel bir baş düğüm tarafından döndürülen yineleyici karşılık gelen [set::end (STL/CLR)](../dotnet/set-end-stl-clr.md)`()`. Denetlenen sıradaki son öğe ulaşmak için bu yineleyici varsa azaltma. Baş düğüm ulaşmak için bir set yineleyici artırabilirsiniz ve bu ardından eşit karşılaştırır `end()`. Ancak tarafından döndürülen yineleyici başvuramaz `end()`.  
  
 Doğrudan bir erişim rastgele yineleyici gerektiren sayısal konumunu--verilen kümesi öğeye başvuramaz unutmayın.  
  
 Sırayla ilişkilendirilmiş kapsayıcısı için bir tanıtıcı depolar onun ilişkili küme düğümü için bir tanıtıcı kümesi yineleyici depolar. Yalnızca ilişkili kapsayıcı nesneleri ile yineleyiciler kullanabilirsiniz. İlişkili küme düğümü bazı kümesiyle ilişkili olduğu sürece kümesi yineleyici geçerli kalır. Ayrıca, geçerli bir yineleyici dereferencable--erişmek veya eşit değil sürece bunu atayan--öğe değeri değiştirmek için kullanmak `end()`.  
  
 Silme veya bir öğe kaldırıldığında yıkıcı depolanan değeri için çağırır. Kapsayıcı yok etme tüm öğeleri siler. Bu nedenle, hiçbir öğe kapsayıcı outlive ref sınıfı öğe türü olan bir kapsayıcı sağlar. Ancak, bir kapsayıcı, tanıtıcısı algılamadığı unutmayın `not` öğeleri yok.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/kümesi >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [eşleme (STL/CLR)](../dotnet/map-stl-clr.md)   
 [ayarlama](../dotnet/set-stl-clr.md)   
 [ayarlama](../dotnet/set-stl-clr.md)   
 [STL/CLR Kitaplık Başvurusu](../dotnet/stl-clr-library-reference.md)