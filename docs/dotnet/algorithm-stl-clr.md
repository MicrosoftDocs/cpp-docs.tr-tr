---
title: algoritma (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- <cliext/algorithm>
dev_langs:
- C++
helpviewer_keywords:
- algorithm functions [STL/CLR]
- <algorithm> header [STL/CLR]
- <cliext/algorithm> header [STL/CLR]
ms.assetid: ee2718dc-a98d-40b8-8341-593fe7d2ac15
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7dac0e574122342c96b28a2f5ccbeb1ea5088ae9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="algorithm-stlclr"></a>algoritma (STL/CLR)
Algoritmalar gerçekleştirmek STL/CLR kapsayıcı şablon işlevleri tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#include <cliext/algorithm>  
```  
  
## <a name="functions"></a>İşlevler  
  
|İşlev|Açıklama|  
|--------------|-----------------|  
|[adjacent_find (STL/CLR)](../dotnet/adjacent-find-stl-clr.md)|Eşit iki bitişik öğeleri arar.|  
|[binary_search (STL/CLR)](../dotnet/binary-search-stl-clr.md)|Bir sıralanmış sırası belirli bir değeri içerip içermediğini sınar.|  
|[copy (STL/CLR)](../dotnet/copy-stl-clr.md)|İleri yönde yineleme bir hedef aralığı için bir kaynak aralığı değerleri kopyalar.|  
|[copy_backward (STL/CLR)](../dotnet/copy-backward-stl-clr.md)|Geriye dönük yönde yineleme bir hedef aralığı için kaynak aralık değerleri kopyalar.|  
|[count (STL/CLR)](../dotnet/count-stl-clr.md)|Değerleri belirtilen bir değerle eşleşen bir aralıktaki öğelerin sayısını döndürür.|  
|[count_if (STL/CLR)](../dotnet/count-if-stl-clr.md)|Değerleri belirtilen bir koşulla eşleşen bir aralıktaki öğelerin sayısını döndürür.|  
|[equal (STL/CLR)](../dotnet/equal-stl-clr.md)|İki aralıkları, öğe karşılaştırır.|  
|[equal_range (STL/CLR)](../dotnet/equal-range-stl-clr.md)|Sıralı değerler arar ve belirli bir öğenin tüm eşit değerlerin bir değişkene sınırlandırmak iki konumlarını döndürür.|  
|[fill (STL/CLR)](../dotnet/fill-stl-clr.md)|Aynı yeni değeri belirtilen bir aralıktaki her öğeye atar.|  
|[fill_n (STL/CLR)](../dotnet/fill-n-stl-clr.md)|Yeni bir değer bir aralık başına öğeleri belirli bir öğesiyle belirtilen sayıda atar.|  
|[find (STL/CLR)](../dotnet/find-stl-clr.md)|Belirtilen bir değerin ilk oluşum konumunu döndürür.|  
|[find_end (STL/CLR)](../dotnet/find-end-stl-clr.md)|Belirtilen sıra için aynı olan bir aralıkta son değişkene döndürür.|  
|[find_first_of (STL/CLR)](../dotnet/find-first-of-stl-clr.md)|Öğe verilen aralığını herhangi birinin ilk a geçişi için bir aralığı arar.|  
|[find_if (STL/CLR)](../dotnet/find-if-stl-clr.md)|İlk öğenin konumunu burada öğesi belirtilen bir koşula uygun değerleri bir dizi döndürür.|  
|[for_each (STL/CLR)](../dotnet/for-each-stl-clr.md)|Belirtilen işlev nesnesi değerleri dizisindeki her öğesine uygular ve işlev nesnesi döndürür.|  
|[generate (STL/CLR)](../dotnet/generate-stl-clr.md)|Değerleri dizisindeki her öğe için bir işlev nesnesi tarafından üretilen değerler atar.|  
|[generate_n (STL/CLR)](../dotnet/generate-n-stl-clr.md)|Belirtilen sayıda öğeyi işlevi nesnesine tarafından üretilen değerler atar.|  
|[includes (STL/CLR)](../dotnet/includes-stl-clr.md)|Bir sıralanmış aralık ikinci bir sıralanmış aralıktaki tüm öğeleri içeren olup olmadığını sınar.|  
|[inplace_merge (STL/CLR)](../dotnet/inplace-merge-stl-clr.md)|İki ardışık sıralanmış aralıkları öğeleri tek bir sıralanmış aralığına birleştirir.|  
|[iter_swap (STL/CLR)](../dotnet/iter-swap-stl-clr.md)|Belirtilen yineleyicilerin bir çifti tarafından başvurulan iki değeri birbiriyle değiştirir.|  
|[lexicographical_compare (STL/CLR)](../dotnet/lexicographical-compare-stl-clr.md)|İki dizileri, hangi iki daha düşük bir dizidir tanımlayan öğe, karşılaştırır.|  
|[lower_bound (STL/CLR)](../dotnet/lower-bound-stl-clr.md)|Belirtilen değere eşit veya daha büyük bir değere sahip sıralı değerlerin ilk öğenin konumunu bulur.|  
|[make_heap (STL/CLR)](../dotnet/make-heap-stl-clr.md)|Öğeleri belirtilen bir aralıktan ilk öğe öbek üzerinde en büyük olduğu yığına dönüştürür.|  
|[max (STL/CLR)](../dotnet/max-stl-clr.md)|İki nesneyi karşılaştırır ve büyük iki döndürür.|  
|[max_element (STL/CLR)](../dotnet/max-element-stl-clr.md)|En büyük öğeyi değerlerin belirtilen sırayla bulur.|  
|[merge (STL/CLR)](../dotnet/merge-stl-clr.md)|İki sıralanmış kaynak aralığı tüm öğeleri bir tek, sıralanmış hedef aralığına birleştirir.|  
|[min (STL/CLR)](../dotnet/min-stl-clr.md)|İki nesneyi karşılaştırır ve küçük iki döndürür.|  
|[min_element (STL/CLR)](../dotnet/min-element-stl-clr.md)|En küçük öğeyi değerlerin belirtilen sırayla bulur.|  
|[mismatch (STL/CLR)](../dotnet/mismatch-stl-clr.md)|İki aralıkları öğe karşılaştırır ve bir fark oluştuğu ilk konumunu döndürür.|  
|[next_permutation (STL/CLR)](../dotnet/next-permutation-stl-clr.md)|Böylece özgün sıralama varsa lexicographically sonraki büyük nesne tarafından değiştirilir bir aralıkta öğeleri yeniden sıralar.|  
|[nth_element (STL/CLR)](../dotnet/nth-element-stl-clr.md)|Öğeleri doğru bulma, bir dizi bölümler `n`th öğesi dizisi böylece, önünde tüm öğeleri değerden küçük veya bu değere eşit olan ve onu izleyen tüm öğeleri değerinden büyük veya ona eşit.|  
|[partial_sort (STL/CLR)](../dotnet/partial-sort-stl-clr.md)|Belirtilen sayıda küçük öğeyi bir aralıkta nondescending düzeni içinde düzenler.|  
|[partial_sort_copy (STL/CLR)](../dotnet/partial-sort-copy-stl-clr.md)|Kaynak aralığı öğeleri sıralı şekilde öğelerini bir kaynak aralığından bir hedef aralığına kopyalar.|  
|[partition (STL/CLR)](../dotnet/partition-stl-clr.md)|Birli koşul karşılamak bu öğeleri karşılamayı başarısız olmuş öncesinde, bir aralıktaki öğeleri düzenler.|  
|[pop_heap (STL/CLR)](../dotnet/pop-heap-stl-clr.md)|En büyük öğeyi yığın Önden sonuna taşır ve yeni bir öbek kalan öğelerden oluşturur.|  
|[prev_permutation (STL/CLR)](../dotnet/prev-permutation-stl-clr.md)|Böylece özgün sıralama varsa lexicographically önceki büyük nesne tarafından değiştirilir öğelerinin bir dizisini yeniden sıralar.|  
|[push_heap (STL/CLR)](../dotnet/push-heap-stl-clr.md)|Aralığın sonundaki bir öğeyi aralıktaki önceki öğeleri içeren mevcut yığına ekler.|  
|[random_shuffle (STL/CLR)](../dotnet/random-shuffle-stl-clr.md)|Bir dizi yeniden düzenler `N` birini aralığına öğelerinde `N`! olası düzenlemeleri rastgele seçilmiş.|  
|[remove (STL/CLR)](../dotnet/remove-stl-clr.md)|Kalan öğelerin sırasını etkilemeden arasında belirli bir aralık belirtilen bir değeri siler ve yeni bir aralık belirtilen değerinin boş sonunu döndürür.|  
|[remove_copy (STL/CLR)](../dotnet/remove-copy-stl-clr.md)|Belirtilen bir değeri öğeleri, kalan öğelerin sırasını etkilemeden kopyalanmaz dışında öğelerini hedef aralığı için bir kaynak aralığından kopyalar.|  
|[remove_copy_if (STL/CLR)](../dotnet/remove-copy-if-stl-clr.md)|Kalan öğelerin sırasını etkilemeden bir koşulu karşılayan olanlar dışında bir hedef aralığı kaynak aralığından öğelerine kopyalar.|  
|[remove_if (STL/CLR)](../dotnet/remove-if-stl-clr.md)|Kalan öğelerin sırasını etkilemeden bir koşul belirli bir aralıktan karşılamak öğeleri siler. biçimindeki telefon numarasıdır.|  
|[replace (STL/CLR)](../dotnet/replace-stl-clr.md)|Yeni bir değer belirli bir değerle eşleşen öğeleri bir aralıkta yerini alır.|  
|[replace_copy (STL/CLR)](../dotnet/replace-copy-stl-clr.md)|Yeni bir değer belirli bir değerle eşleşen öğeleri değiştirme hedef aralığı, bir kaynak aralıktan öğelerine kopyalar.|  
|[replace_copy_if (STL/CLR)](../dotnet/replace-copy-if-stl-clr.md)|Bir kaynak aralığındaki her öğeyi inceler ve sonuç yeni bir hedef aralığına kopyalanırken öğe belirtilen bir koşulu karşılıyorsa, onu değiştirir.|  
|[replace_if (STL/CLR)](../dotnet/replace-if-stl-clr.md)|Bir aralıktaki tüm öğeleri inceler ve belirtilen bir koşulu karşılıyorsa değiştirir.|  
|[reverse (STL/CLR)](../dotnet/reverse-stl-clr.md)|Bir aralık içindeki öğelerin sırasını tersine çevirir.|  
|[reverse_copy (STL/CLR)](../dotnet/reverse-copy-stl-clr.md)|Bir hedef aralığına kopyalarken bir kaynak aralıkta öğelerin sırasını tersine çevirir.|  
|[rotate (STL/CLR)](../dotnet/rotate-stl-clr.md)|İki bitişik aralık içindeki öğeleri birbiriyle değiştirir.|  
|[rotate_copy (STL/CLR)](../dotnet/rotate-copy-stl-clr.md)|Bir kaynak aralık içindeki iki bitişik aralıktaki öğeleri birbiriyle değiştirir ve sonucu bir hedef aralığına kopyalar.|  
|[search (STL/CLR)](../dotnet/search-stl-clr.md)|Öğeleri verili bir öğe dizisi içindekilerle eşit olan veya öğeleri verili bir dizi öğe için ikili bir koşula göre belirtildiği şekilde denk olan bir hedef aralığındaki dizinin ilk geçtiği yeri arar.|  
|[search_n (STL/CLR)](../dotnet/search-n-stl-clr.md)|Belirli bir değere veya ikili bir koşula göre belirtilen değerle bir ilişkiye sahip olan öğelerin belirli bir sayısının aralığındaki ilk diziyi arar.|  
|[set_difference (STL/CLR)](../dotnet/set-difference-stl-clr.md)|Sıralanmış ikinci bir kaynak aralığına sahip olanları değil, sıralanmış bir kaynak aralığına sahip öğelerin tümünü tek, sıralanmış bir hedef aralığı içinde birleştirir, burada sıralama ölçütü ikili bir koşula göre belirtilebilir.|  
|[set_intersection (STL/CLR)](../dotnet/set-intersection-stl-clr.md)|Her iki sıralanmış kaynak aralığa sahip öğelerin tümünü tek, sıralanmış bir aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.|  
|[set_symmetric_difference (STL/CLR)](../dotnet/set-symmetric-difference-stl-clr.md)|İki değil, tek bir sıralanmış kaynak aralığa sahip öğelerin tümünü tek, sıralanmış bir aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.|  
|[set_union (STL/CLR)](../dotnet/set-union-stl-clr.md)|İki sıralanmış kaynak aralığından en az birine sahip öğelerin tümünü tek, sıralanmış bir aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.|  
|[sort (STL/CLR)](../dotnet/sort-stl-clr.md)|Belirtilen bir aralıktaki öğeleri azalmayan şekilde veya bir ikili koşul tarafından belirtilen bir sıralama ölçütüne göre düzenler.|  
|[sort_heap (STL/CLR)](../dotnet/sort-heap-stl-clr.md)|Bir yığını sıralanmış bir aralığa dönüştürür.|  
|[stable_partition (STL/CLR)](../dotnet/stable-partition-stl-clr.md)|Bir aralıktaki öğeleri, eşdeğer öğelerin göreli sırasını koruyaraktan, onları karşılamada yetersiz koşulu önceleyen birli koşulu sağlayan öğelerle iki ayrık kümede sınıflandırır.|  
|[stable_sort (STL/CLR)](../dotnet/stable-sort-stl-clr.md)|Belirtilen bir aralıktaki öğeleri, eşdeğer öğelerin göreli sıralamasını koruyaraktan, azalmayan şekilde veya bir ikili koşul tarafından belirtilen bir sıralama ölçütüne göre düzenler.|  
|[swap (STL/CLR)](../dotnet/swap-stl-clr.md)|İlk nesnenin içeriğini ikinci nesneye ve ikinci nesneni içeriğini birinciye atayarak, nesnelerin iki türü arasındaki öğelerin değerlerini birbiriyle değiştirir.|  
|[swap_ranges (STL/CLR)](../dotnet/swap-ranges-stl-clr.md)|Bir aralığın öğelerini eşit büyüklükteki bir diğerinin öğeleriyle değiştirir.|  
|[transform (STL/CLR)](../dotnet/transform-stl-clr.md)|Belirtilen işlev nesnesini bir kaynak aralıktaki her bir öğeye veya iki kaynak aralıktaki bir öğe çiftine uygular ve işlev nesnenin dönüş değerlerini bir hedef aralığa kopyalar.|  
|[unique (STL/CLR)](../dotnet/unique-stl-clr.md)|Belirli bir aralıktaki birbirine bitişik yinelenen öğeleri kaldırır.|  
|[unique_copy (STL/CLR)](../dotnet/unique-copy-stl-clr.md)|Birbirine bitişik yinelenen öğeler hariç bir kaynak aralıktaki öğeleri hedef aralığa kopyalar.|  
|[upper_bound (STL/CLR)](../dotnet/upper-bound-stl-clr.md)|Belirtilenden daha büyük bir değere sahip sıralı bir aralıktaki ilk öğenin konumunu bulur, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/algoritması >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [STL/CLR Kitaplık Başvurusu](../dotnet/stl-clr-library-reference.md)