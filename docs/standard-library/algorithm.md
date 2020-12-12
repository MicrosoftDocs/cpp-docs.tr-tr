---
description: 'Daha fazla bilgi edinin: &lt; algoritması&gt;'
title: '&lt;algoritmalar&gt;'
ms.date: 11/04/2016
f1_keywords:
- <algorithm>
helpviewer_keywords:
- algorithm header [C++]
- C++ Standard Library, algorithms
- <algorithm> header
ms.assetid: 19f97711-7a67-4a65-8fd1-9a2bd3ca327d
ms.openlocfilehash: 42f03372d01ac2d3218ce5844b86e92526055bbf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163775"
---
# <a name="ltalgorithmgt"></a>&lt;algoritmalar&gt;

Algoritmalar gerçekleştiren C++ standart kitaplık kapsayıcı şablonu işlevlerini tanımlar.

## <a name="syntax"></a>Syntax

```cpp
(see relevant links below for specific algorithm syntax)
```

> [!NOTE]
> \<algorithm>Kitaplık, ifadesini de kullanır `#include <initializer_list>` .

## <a name="remarks"></a>Açıklamalar

C++ Standart Kitaplığı algoritmaları, çeşitli veri yapıları üzerinde çalışabildiklerinden geneldir. Üzerinde çalışabildikleri veri yapıları yalnızca ve gibi C++ standart kitaplık kapsayıcı sınıflarını değil `vector` `list` , ayrıca program tanımlı veri yapılarını ve belirli bir algoritmanın gereksinimlerini karşılayan öğe dizilerini içerir. C++ standart kitaplık algoritmaları, yineleyiciler aracılığıyla dolaylı olarak bir kapsayıcının öğelerine erişerek ve geçiş yaparak bu düzeyde bir elde elde elde edin.

C++ Standart Kitaplığı algoritmaları, genellikle başlangıç veya bitiş konumlarına göre belirtilen Yineleyici aralıklarını işler. Aralıklardaki tüm işaretçilerin tekrar başvurulabilir olması ve her aralığın dizisinde olması gerekliliği bakımından, başvurulan aralıkların geçerli olması gerekir; son konum da artış yoluyla birinciden erişilebilir olmalıdır.

C++ Standart Kitaplığı algoritmaları, her C++ standart kitaplığı kapsayıcısının işlemler ve üye işlevleri tarafından desteklenen eylemleri genişletir ve örneğin aynı anda farklı kapsayıcı nesne türleriyle çalışmaya izin verir. İki sonek, algoritmaların amacı hakkında bilgi iletmek için kullanılmıştır.

- `_if`Sonek, algoritmanın öğelerin kendileri yerine öğelerin değerleri üzerinde çalışan işlev nesneleriyle kullanıldığını gösterir. `find_if`Algoritması, değerleri bir işlev nesnesi tarafından belirtilen ölçütü karşılayan öğeleri arar ve `find` algoritma belirli bir değeri arar.

- _Copy soneki algoritmanın yalnızca öğelerinin değerlerini yönetmeyeceğini, aynı zamanda değiştirilen değerlerin bir hedef aralığına da kopyalayacağını belirtir. `reverse`Algoritma, öğelerin sırasını bir Aralık içinde tersine çevirir ve `reverse_copy` algoritma Ayrıca sonucu bir hedef aralığa kopyalar.

C++ Standart Kitaplığı algoritmaları, genellikle amaçları veya gereksinimleriyle ilgili bir şeyi gösteren gruplar halinde sınıflandırılır. Bunlar, öğelerin değerlerini değiştiren algoritmaların değişmeyen algoritmalarla karşılaştırıldığında değiştirilmesini içerir. Algoritmaların değiştirilmesi öğelerin sırasını değiştirir, ancak kendi öğelerinin değerlerini değiştirmez. Algoritmaların kaldırılması bir aralıktaki ya da aralıktaki bir kopyadaki öğeleri yok sayabilir. Sıralama algoritmaları, bir aralıktaki öğeleri çeşitli yollarla yeniden sıralar ve sıralanmış Aralık algoritmaları yalnızca öğeleri belirli bir şekilde sıralanan aralıklar üzerinde işlem görür.

Sayısal işleme için belirtilen C++ standart kitaplığı sayısal algoritmalarının kendi başlık dosyaları vardır [\<numeric>](numeric.md) ve işlev nesneleri ve bağdaştırıcılar, [\<functional>](functional.md) Boole değerleri döndüren üst bilgi işlev nesnelerinde tanımlanmıştır. Varsayılan ikili koşul karşılaştırma ' dır `operator<` . Genelde, sıralanan öğelerin küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu eşdeğer olmayan öğeler arasında bir sıralamaya neden olur.

### <a name="function-templates"></a>İşlev şablonları

|Ad|Açıklama|
|-|-|
|[adjacent_find](algorithm-functions.md#adjacent_find)|Eşit ya da belirli bir koşulu karşılayan iki bitişik öğeyi arar.|
|[all_of](algorithm-functions.md#all_of)|**`true`** Verilen aralıktaki her bir öğede bir koşul varsa döndürür.|
|[any_of](algorithm-functions.md#any_of)|**`true`** Belirtilen öğe aralığında bir koşul en az bir kez olduğunda döndürür.|
|[binary_search](algorithm-functions.md#binary_search)|Belirtilen değere eşit sıralanmış bir aralıkta bir öğe olup olmadığını ya da bir ikili koşula göre belirtilen anlamda ona eşdeğer bir öğe olup olmadığını sınar.|
|[Clamp](algorithm-functions.md#clamp)||
|[kopya](algorithm-functions.md#copy)|Bir kaynak aralığındaki öğe değerlerini bir hedef aralığına atayarak, öğelerin kaynak sırası boyunca yineler ve bunları yeni konumlarına ileri yönde atar.|
|[copy_backward](algorithm-functions.md#copy_backward)|Bir kaynak aralığındaki öğe değerlerini bir hedef aralığına atayarak, öğelerin kaynak sırası boyunca yineler ve bunları yeni konumlarına geri yönde atar.|
|[copy_if](algorithm-functions.md#copy_if)|Belirtilen bir koşul için test edilen belirli bir aralıktaki tüm öğeleri Kopyala **`true`**|
|[copy_n](algorithm-functions.md#copy_n)|Belirtilen sayıda öğeyi kopyalar.|
|[biriktirme](algorithm-functions.md#count)|Değerleri belirtilen bir değerle eşleşen bir aralıktaki öğelerin sayısını döndürür.|
|[count_if](algorithm-functions.md#count_if)|Değerleri belirtilen bir koşulla eşleşen bir aralıktaki öğelerin sayısını döndürür.|
|[sıfıra](algorithm-functions.md#equal)|Bir ikili koşula göre belirtilen anlamda eşitlik ya da denklik için iki aralık öğesini öğeye göre karşılaştırır.|
|[equal_range](algorithm-functions.md#equal_range)|Sıralanmış aralıktaki konumların çiftini bulur, birinci belirtilen bir öğenin konumundan küçük veya ona eşittir ve ikinci öğenin konumundan büyüktür, burada dizideki konumlar oluşturmak için kullanılan denkliğin veya sıralamanın anlamı bir ikili koşula göre belirtilebilir.|
|[doldurması](algorithm-functions.md#fill)|Aynı yeni değeri belirtilen bir aralıktaki her öğeye atar.|
|[fill_n](algorithm-functions.md#fill_n)|Belirli bir öğeyle başlayan bir aralıktaki belirli öğe sayısına yeni bir değer atar.|
|[bilgi](algorithm-functions.md#find)|Bir öğenin belirli bir değere sahip olan aralıktaki ilk geçtiği konumu bulur.|
|[find_end](algorithm-functions.md#find_end)|Belirli bir diziye özdeş veya bir ikili koşula göre belirtildiği şekilde denk olan son dizi için bir aralık arar.|
|[find_first_of](algorithm-functions.md#find_first_of)|Bir hedef aralığındaki çeşitli değerlerden herhangi birinin ilk geçtiği yeri veya bir ikili koşula göre belirtilen bir öğeler kümesine belirtildiği şekilde denk olan çeşitli öğelerin geçtiği ilk yeri arar.|
|[find_if](algorithm-functions.md#find_if)|Bir öğenin belirli bir koşulu karşıladığı aralıktaki ilk geçtiği konumu bulur.|
|[find_if_not](algorithm-functions.md#find_if_not)|Bir koşulu karşılamayan belirtilen aralıktaki ilk öğeyi döndürür.|
|[for_each](algorithm-functions.md#for_each)|Bir aralıktaki ileriye doğru sıradaki her öğeye belirli bir işlev uygular ve işlev nesnesini döndürür.|
|[for_each_n](algorithm-functions.md#for_each_n)||
|[üretecek](algorithm-functions.md#generate)|Bir işlev nesnesi tarafından oluşturulan değerleri bir aralıktaki her öğeye atar.|
|[generate_n](algorithm-functions.md#generate_n)|Bir işlev nesnesi tarafından oluşturulan değerleri bir aralıktaki belirtilen öğe sayısına atar ve birinin son atanan değere geçirdiği konuma döner.|
|[içermektedir](algorithm-functions.md#includes)|Sıralanmış bir aralığın ikinci bir sıralanmış aralıkta kapsanan tüm öğeleri içerip içermediğini sınar, burada öğeler arasındaki sıralama veya denklik ölçütü bir ikili koşula göre belirlenebilir.|
|[inplace_merge](algorithm-functions.md#inplace_merge)|Ardışık iki sıralanmış aralıktaki öğeleri tek bir sıralanmış aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.|
|[is_heap](algorithm-functions.md#is_heap)|**`true`** Belirtilen aralıktaki öğelerin bir yığın oluştur, döndürür.|
|[is_heap_until](algorithm-functions.md#is_heap_until)|**`true`** Belirtilen aralığın son öğe kadar bir yığın olarak form halinde olup olmadığını döndürür.|
|[is_partitioned](algorithm-functions.md#is_partitioned)|**`true`** Bir koşulu test eden belirtilen aralıktaki tüm öğelerin **`true`** test eden herhangi bir öğeden önce gelip gelmediğini döndürür **`false`** .|
|[is_permutation](algorithm-functions.md#is_permutation)|Belirli bir aralıktaki öğelerin geçerli bir permütasyon yapıp olmadığını belirler.|
|[is_sorted](algorithm-functions.md#is_sorted)|**`true`** Belirtilen aralıktaki öğelerin sıralı sırada olup olmadığını döndürür.|
|[is_sorted_until](algorithm-functions.md#is_sorted_until)|**`true`** Belirtilen aralıktaki öğelerin sıralı sırada olup olmadığını döndürür.|
|[iter_swap](algorithm-functions.md#iter_swap)|Belirtilen yineleyicilerin bir çifti tarafından başvurulan iki değeri birbiriyle değiştirir.|
|[lexicographical_compare](algorithm-functions.md#lexicographical_compare)|Daha küçük olanı belirlemek için iki diziyi öğe öğe karşılaştırır.|
|[lower_bound](algorithm-functions.md#lower_bound)|Sıralı bir aralıkta belirtilen değere eşit ya da daha büyük bir değere sahip ilk öğenin konumunu bulur, burada sıralama kriteri bir ikili koşula göre belirtilebilir.|
|[make_heap](algorithm-functions.md#make_heap)|Belirtilen bir aralıktaki öğeleri ilk öğenin en büyük olduğu ve onun için bir ikili koşula sahip bir sıralama ölçütünün belirtilebildiği bir yığına dönüştürür.|
|[Biçimlendir](algorithm-functions.md#max)|İki nesneyi karşılaştırır ve ikisinden büyük olanı döndürür, burada sıralama ölçütü ikili bir koşula göre belirtilebilir.|
|[max_element](algorithm-functions.md#max_element)|Belirtilen bir aralıktaki en büyük öğenin geçtiği ilk yeri bulur, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.|
|[birleþtirmek](algorithm-functions.md#merge)|İki sıralanmış kaynak aralıktaki tüm öğeleri tek bir sıralanmış aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.|
|[Min](algorithm-functions.md#min)|İki nesneyi karşılaştırır ve ikisinden küçük olanı döndürür, burada sıralama ölçütü ikili bir koşula göre belirtilebilir.|
|[min_element](algorithm-functions.md#min_element)|Belirtilen bir aralıktaki en küçük öğenin geçtiği ilk yeri bulur, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.|
|[MinMax](algorithm-functions.md#minmax)|İki giriş parametresini karşılaştırır ve bunları küçükten büyüğe bir çift olarak döndürür.|
|[minmax_element](algorithm-functions.md#minmax_element)|[Min_element](algorithm-functions.md#min_element) tarafından gerçekleştirilen çalışmayı gerçekleştirir ve tek bir çağrıda [max_element](algorithm-functions.md#max_element) .|
|[mez](algorithm-functions.md#mismatch)|Eşitlik ya da denklik için ikili bir koşul tarafından belirtildiği şekilde iki aralığı öğe öğe karşılaştırır ve farkın oluştuğu ilk yeri bulur.|
|[&lt;alg &gt; Taşı](algorithm-functions.md#alg_move)|Belirtilen aralıkla ilişkili öğeleri taşı.|
|[move_backward](algorithm-functions.md#move_backward)|Bir yineleyicinin öğelerini diğerine taşır. Hareket belirli bir aralıktaki son öğeyle başlar ve söz konusu aralıktaki ilk öğeyle biter.|
|[next_permutation](algorithm-functions.md#next_permutation)|Aralıktaki öğeleri yeniden sıralar, böylece özgün sıralama sözlüksel biçimde, varsa, bir sonraki permütasyon ile değiştirilir, burada sonraki bir ikili koşula göre belirtilebilir.|
|[none_of](algorithm-functions.md#none_of)|**`true`** Verilen aralıktaki öğeler arasında bir koşul hiçbir zaman mevcut olmadığında döndürür.|
|[nth_element](algorithm-functions.md#nth_element)|Aralıktaki sıranın *n*. öğesini doğru bir şekilde bulur ve bu sayede dizideki tüm öğelerin bu değerden küçük veya ona eşit olması ve dizide izleyen tüm öğelerin bu değerden büyük veya ona eşit olması için bir dizi öğeyi bölümler.|
|[partial_sort](algorithm-functions.md#partial_sort)|Bir aralıktaki daha küçük öğelerin belirtilen sayısını azalmayan şekilde veya bir ikili koşul tarafından belirtilen bir sıralama ölçütüne göre düzenler.|
|[partial_sort_copy](algorithm-functions.md#partial_sort_copy)|Öğeleri bir kaynak aralığından bir hedef aralığa kopyalar, burada kaynak öğeleri daha küçük olana ya da belirtilen başka bir ikili koşula göre sıralanır.|
|[bölümünüzün](algorithm-functions.md#partition)|Bir aralıktaki öğeleri, onları karşılamada yetersiz koşulu önceleyen birli koşulu sağlayan öğelerle iki ayrık kümede sınıflandırır.|
|[partition_copy](algorithm-functions.md#partition_copy)|Bir koşula ait olan öğeleri **`true`** ve koşulun başka bir hedefe olduğu öğeleri kopyalar **`false`** . Öğeler belirtilen bir aralıktan gelmelidir.|
|[partition_point](algorithm-functions.md#partition_point)|Koşulu karşılamayan verili aralıktaki ilk öğeyi döndürür. Öğeler koşulu karşılayanlar karşılamayanlardan önce gelecek şekilde sıralanır.|
|[pop_heap](algorithm-functions.md#pop_heap)|En büyük öğeyi bir yığının önünden aralıktaki bir sonraki son konuma kaldırır ve ardından kalan öğelerden yeni bir yığın oluşturur.|
|[prev_permutation](algorithm-functions.md#prev_permutation)|Aralıktaki öğeleri yeniden sıralar, böylece özgün sıralama sözlüksel biçimde, varsa, bir sonraki permütasyon ile değiştirilir, burada sonraki bir ikili koşula göre belirtilebilir.|
|[push_heap](algorithm-functions.md#push_heap)|Aralığın sonundaki bir öğeyi aralıktaki önceki öğeleri içeren mevcut yığına ekler.|
|[random_shuffle](algorithm-functions.md#random_shuffle)|Bir aralıktaki *n* öğe dizisini *n* öğelerinden birine yeniden düzenler. Rastgele seçilen olası düzenlemeler.|
|[temizlenmesine](algorithm-functions.md#remove)|Kalan öğelerin sırasını bozmadan ve belirtilen değerin yeni aralığının sonunu boş döndürerek verili aralıktaki belirtilen bir değeri ortadan kaldırır.|
|[remove_copy](algorithm-functions.md#remove_copy)|Öğeleri, belirtilen değerin kopyalanmayan öğeleri hariç, kalan öğelerin sırasını bozmadan ve yeni hedef aralığın sonuna döndürerek bir kaynak aralıktan bir hedef aralığa kopyalar.|
|[remove_copy_if](algorithm-functions.md#remove_copy_if)|Öğeleri, bir koşulu karşılayan kopyalanmayan öğeler hariç, kalan öğelerin sırasını bozmadan ve yeni hedef aralığın sonuna döndürerek bir kaynak aralıktan bir hedef aralığa kopyalar.|
|[remove_if](algorithm-functions.md#remove_if)|Kalan öğelerin sırasını bozmadan ve belirtilen değerin yeni aralığının sonunu boş döndürerek verili aralıktaki bir koşulu karşılayan öğeleri ortadan kaldırır.|
|[değiştirin](algorithm-functions.md#replace)|Bir aralıktaki tüm öğeleri inceler ve belirtilen bir değerle eşleşiyorsa değiştirir.|
|[replace_copy](algorithm-functions.md#replace_copy)|Bir kaynak aralığındaki her öğeyi inceler ve sonuç yeni bir hedef aralığına kopyalanırken öğe belirtilen değerle eşleşiyorsa, onu değiştirir.|
|[replace_copy_if](algorithm-functions.md#replace_copy_if)|Bir kaynak aralığındaki her öğeyi inceler ve sonuç yeni bir hedef aralığına kopyalanırken öğe belirtilen bir koşulu karşılıyorsa, onu değiştirir.|
|[replace_if](algorithm-functions.md#replace_if)|Bir aralıktaki tüm öğeleri inceler ve belirtilen bir koşulu karşılıyorsa değiştirir.|
|[tersini](algorithm-functions.md#reverse)|Bir aralık içindeki öğelerin sırasını tersine çevirir.|
|[reverse_copy](algorithm-functions.md#reverse_copy)|Bir hedef aralığına kopyalanırken bir kaynak aralığındaki öğelerin sırasını tersine çevirir|
|[Boyut](algorithm-functions.md#rotate)|İki bitişik aralık içindeki öğeleri birbiriyle değiştirir.|
|[rotate_copy](algorithm-functions.md#rotate_copy)|Bir kaynak aralık içindeki iki bitişik aralıktaki öğeleri birbiriyle değiştirir ve sonucu bir hedef aralığına kopyalar.|
|[örnekli](algorithm-functions.md#sample)||
|[search](algorithm-functions.md#search)|Öğeleri verili bir öğe dizisi içindekilerle eşit olan veya öğeleri verili bir dizi öğe için ikili bir koşula göre belirtildiği şekilde denk olan bir hedef aralığındaki dizinin ilk geçtiği yeri arar.|
|[search_n](algorithm-functions.md#search_n)|Belirli bir değere veya ikili bir koşula göre belirtilen değerle bir ilişkiye sahip olan öğelerin belirli bir sayısının aralığındaki ilk diziyi arar.|
|[set_difference](algorithm-functions.md#set_difference)|Sıralanmış ikinci bir kaynak aralığına sahip olanları değil, sıralanmış bir kaynak aralığına sahip öğelerin tümünü tek, sıralanmış bir hedef aralığı içinde birleştirir, burada sıralama ölçütü ikili bir koşula göre belirtilebilir.|
|[set_intersection](algorithm-functions.md#set_intersection)|Her iki sıralanmış kaynak aralığa sahip öğelerin tümünü tek, sıralanmış bir aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.|
|[set_symmetric_difference](algorithm-functions.md#set_symmetric_difference)|İki değil, tek bir sıralanmış kaynak aralığa sahip öğelerin tümünü tek, sıralanmış bir aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.|
|[set_union](algorithm-functions.md#set_union)|İki sıralanmış kaynak aralığından en az birine sahip öğelerin tümünü tek, sıralanmış bir aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.|
|[düzenine](algorithm-functions.md#sort)|Belirtilen bir aralıktaki öğeleri azalmayan şekilde veya bir ikili koşul tarafından belirtilen bir sıralama ölçütüne göre düzenler.|
|[shuffle](algorithm-functions.md#shuffle)|Rastgele sayı Oluşturucu kullanarak belirli bir Aralık için öğeleri karışık (yeniden düzenler).|
|[sort_heap](algorithm-functions.md#sort_heap)|Bir yığını sıralanmış bir aralığa dönüştürür.|
|[stable_partition](algorithm-functions.md#stable_partition)|Bir aralıktaki öğeleri, eşdeğer öğelerin göreli sırasını koruyaraktan, onları karşılamada yetersiz koşulu önceleyen birli koşulu sağlayan öğelerle iki ayrık kümede sınıflandırır.|
|[stable_sort](algorithm-functions.md#stable_sort)|Belirtilen bir aralıktaki öğeleri, eşdeğer öğelerin göreli sıralamasını koruyaraktan, azalmayan şekilde veya bir ikili koşul tarafından belirtilen bir sıralama ölçütüne göre düzenler.|
|[Kur](algorithm-functions.md#swap)|İlk nesnenin içeriğini ikinci nesneye ve ikinci nesneni içeriğini birinciye atayarak, nesnelerin iki türü arasındaki öğelerin değerlerini birbiriyle değiştirir.|
|[swap_ranges](algorithm-functions.md#swap_ranges)|Bir aralığın öğelerini eşit büyüklükteki bir diğerinin öğeleriyle değiştirir.|
|[Dönüşümler](algorithm-functions.md#transform)|Belirtilen işlev nesnesini bir kaynak aralıktaki her bir öğeye veya iki kaynak aralıktaki bir öğe çiftine uygular ve işlev nesnenin dönüş değerlerini bir hedef aralığa kopyalar.|
|[eşi](algorithm-functions.md#unique)|Belirli bir aralıktaki birbirine bitişik yinelenen öğeleri kaldırır.|
|[unique_copy](algorithm-functions.md#unique_copy)|Birbirine bitişik yinelenen öğeler hariç bir kaynak aralıktaki öğeleri hedef aralığa kopyalar.|
|[upper_bound](algorithm-functions.md#upper_bound)|Belirtilenden daha büyük bir değere sahip sıralı bir aralıktaki ilk öğenin konumunu bulur, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](cpp-standard-library-header-files.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](cpp-standard-library-reference.md)
