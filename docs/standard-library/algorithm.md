---
title: '&lt;algoritma&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <algorithm>
dev_langs:
- C++
helpviewer_keywords:
- algorithm header [C++]
- C++ Standard Library, algorithms
- <algorithm> header
ms.assetid: 19f97711-7a67-4a65-8fd1-9a2bd3ca327d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc5e181a933c0c511802a0270026635a1766a7be
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="ltalgorithmgt"></a>&lt;Algoritması&gt;

Algoritmalar gerçekleştirmek C++ Standart Kitaplığı kapsayıcı şablon işlevleri tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
(see relevant links below for specific algorithm syntax)
```

## <a name="remarks"></a>Açıklamalar

C++ Standart Kitaplığı algoritmaları genel olduklarından veri yapılarını çeşitli üzerinde çalışabilir. Üzerinde çalışabilir veri yapılarını gibi yalnızca C++ Standart Kitaplığı kapsayıcı sınıfları içeren `vector` ve `list`, ancak aynı zamanda programı tarafından tanımlanan veri yapılarını ve belirli gereksinimleri karşılaması öğelerinin diziler algoritma. C++ Standart Kitaplığı algoritmaları erişme ve yineleyiciler üzerinden dolaylı olarak bir kapsayıcı öğelerini geçiş tarafından bu sayılanların genel düzeyde elde edin.

C++ Standart Kitaplığı algoritmalar genellikle kendi başına veya konumlar bitiş belirtilen yineleyici aralıkları işleyin. Aralıklardaki tüm işaretçilerin tekrar başvurulabilir olması ve her aralığın dizisinde olması gerekliliği bakımından, başvurulan aralıkların geçerli olması gerekir; son konum da artış yoluyla birinciden erişilebilir olmalıdır.

C++ Standart Kitaplığı algoritmaları işlemleri ve her C++ Standart Kitaplığı kapsayıcı üye işlevleri tarafından desteklenen eylemleri genişletmek ve, örneğin, kapsayıcı nesneleri aynı anda farklı türde çalışma izin verir. İki sonek, algoritmaların amacı hakkında bilgi iletmek için kullanılmıştır.

- `_if` Soneki belirten algoritma öğelerinin değerlerini yerine öğelerin kendilerini değerleri işletim işlevi nesneleriyle kullanılır. `find_if` Algoritması değerleri işlev nesnesi tarafından belirtilen ölçütü karşılayan öğelerini arar ve `find` belirli bir değeri algoritması arar.

- _Copy soneki algoritmanın yalnızca öğelerinin değerlerini yönetmeyeceğini, aynı zamanda değiştirilen değerlerin bir hedef aralığına da kopyalayacağını belirtir. `reverse` Algoritması bir aralıkta öğelerin sırasını tersine çevirir ve `reverse_copy` algoritması da bir hedef aralığına sonucu kopyalar.

C++ Standart Kitaplığı algoritmalar genellikle kendi amaç veya gereksinimleri hakkında bir şey belirtmek grupları sınıflandırılır. Bu öğeleri değiştirme karşılaştırıldığında değerini değiştirme algoritmaları değiştirme dahil olmayan algoritmaları. Algoritmaların değiştirilmesi öğelerin sırasını değiştirir, ancak kendi öğelerinin değerlerini değiştirmez. Algoritmaların kaldırılması bir aralıktaki ya da aralıktaki bir kopyadaki öğeleri yok sayabilir. Algoritmalar sıralama çeşitli şekillerde bir aralıktaki öğeleri yeniden sıralamak ve sıralanmış aralığı algoritmaları yalnızca belirli bir şekilde öğeleri sıralanmıştır aralıkları hareket.

Kendi üstbilgi dosyası sayısal işlemek için sağlanan C++ Standart Kitaplığı sayısal algoritmalarına sahip [ \<sayısal >](../standard-library/numeric.md), ve işlev nesneleri ve bağdaştırıcıları başlığında tanımlanır [ \<işlev >](../standard-library/functional.md) Boole değerleri döndüren işlev nesneleri koşul olarak bilinir. Karşılaştırma varsayılan ikili koşulu olup `operator<`. Genelde, sıralanan öğelerin küçüktür biçiminde karşılaştırılabilir olması gerekir; böylece, herhangi iki öğe belirtildiğinde, eşit oldukları (yani birinin diğerinden daha küçük olmadığı anlamında) veya birinin diğerinden küçük olduğu belirlenebilir. Bu eşdeğer olmayan öğeler arasında bir sıralamaya neden olur.

### <a name="function-templates"></a>İşlev şablonları

|İşlev şablonu|Açıklama|
|-|-|
|[adjacent_find](../standard-library/algorithm-functions.md#adjacent_find)|Eşit ya da belirli bir koşulu karşılayan iki bitişik öğeyi arar.|
|[all_of](../standard-library/algorithm-functions.md#all_of)|Döndürür `true` bir koşul olduğunda verilen aralıktaki her öğede mevcut.|
|[any_of](../standard-library/algorithm-functions.md#any_of)|Döndürür `true` bir koşul olduğunda öğeleri belirtilen aralık içinde en az bir kez mevcut.|
|[binary_search](../standard-library/algorithm-functions.md#binary_search)|Belirtilen değere eşit sıralanmış bir aralıkta bir öğe olup olmadığını ya da bir ikili koşula göre belirtilen anlamda ona eşdeğer bir öğe olup olmadığını sınar.|
|[Kopyalama](../standard-library/algorithm-functions.md#copy)|Bir kaynak aralığındaki öğe değerlerini bir hedef aralığına atayarak, öğelerin kaynak sırası boyunca yineler ve bunları yeni konumlarına ileri yönde atar.|
|[copy_backward](../standard-library/algorithm-functions.md#copy_backward)|Bir kaynak aralığındaki öğe değerlerini bir hedef aralığına atayarak, öğelerin kaynak sırası boyunca yineler ve bunları yeni konumlarına geri yönde atar.|
|[copy_if](../standard-library/algorithm-functions.md#copy_if)|Tüm öğeleri test belirli bir aralıkta kopyalamak `true` belirtilen bir koşul için|
|[copy_n](../standard-library/algorithm-functions.md#copy_n)|Belirtilen sayıda öğeyi kopyalar.|
|[Sayısı](../standard-library/algorithm-functions.md#count)|Değerleri belirtilen bir değerle eşleşen bir aralıktaki öğelerin sayısını döndürür.|
|[count_if](../standard-library/algorithm-functions.md#count_if)|Değerleri belirtilen bir koşulla eşleşen bir aralıktaki öğelerin sayısını döndürür.|
|[Eşittir](../standard-library/algorithm-functions.md#equal)|Bir ikili koşula göre belirtilen anlamda eşitlik ya da denklik için iki aralık öğesini öğeye göre karşılaştırır.|
|[equal_range](../standard-library/algorithm-functions.md#equal_range)|Sıralanmış aralıktaki konumların çiftini bulur, birinci belirtilen bir öğenin konumundan küçük veya ona eşittir ve ikinci öğenin konumundan büyüktür, burada dizideki konumlar oluşturmak için kullanılan denkliğin veya sıralamanın anlamı bir ikili koşula göre belirtilebilir.|
|[doldurma](../standard-library/algorithm-functions.md#fill)|Aynı yeni değeri belirtilen bir aralıktaki her öğeye atar.|
|[fill_n](../standard-library/algorithm-functions.md#fill_n)|Belirli bir öğeyle başlayan bir aralıktaki belirli öğe sayısına yeni bir değer atar.|
|[Bul](../standard-library/algorithm-functions.md#find)|Bir öğenin belirli bir değere sahip olan aralıktaki ilk geçtiği konumu bulur.|
|[find_end](../standard-library/algorithm-functions.md#find_end)|Belirli bir diziye özdeş veya bir ikili koşula göre belirtildiği şekilde denk olan son dizi için bir aralık arar.|
|[find_first_of](../standard-library/algorithm-functions.md#find_first_of)|Bir hedef aralığındaki çeşitli değerlerden herhangi birinin ilk geçtiği yeri veya bir ikili koşula göre belirtilen bir öğeler kümesine belirtildiği şekilde denk olan çeşitli öğelerin geçtiği ilk yeri arar.|
|[find_if](../standard-library/algorithm-functions.md#find_if)|Bir öğenin belirli bir koşulu karşıladığı aralıktaki ilk geçtiği konumu bulur.|
|[find_if_not](../standard-library/algorithm-functions.md#find_if_not)|Bir koşulu karşılamayan belirtilen aralıktaki ilk öğeyi döndürür.|
|[for_each](../standard-library/algorithm-functions.md#for_each)|Bir aralıktaki ileriye doğru sıradaki her öğeye belirli bir işlev uygular ve işlev nesnesini döndürür.|
|[Oluştur](../standard-library/algorithm-functions.md#generate)|Bir işlev nesnesi tarafından oluşturulan değerleri bir aralıktaki her öğeye atar.|
|[generate_n](../standard-library/algorithm-functions.md#generate_n)|Bir işlev nesnesi tarafından oluşturulan değerleri bir aralıktaki belirtilen öğe sayısına atar ve birinin son atanan değere geçirdiği konuma döner.|
|[İçerir](../standard-library/algorithm-functions.md#includes)|Sıralanmış bir aralığın ikinci bir sıralanmış aralıkta kapsanan tüm öğeleri içerip içermediğini sınar, burada öğeler arasındaki sıralama veya denklik ölçütü bir ikili koşula göre belirlenebilir.|
|[inplace_merge](../standard-library/algorithm-functions.md#inplace_merge)|Ardışık iki sıralanmış aralıktaki öğeleri tek bir sıralanmış aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.|
|[is_heap](../standard-library/algorithm-functions.md#is_heap)|Döndürür `true` yığın form Belirtilen aralıktaki öğelerinin durumunda.|
|[is_heap_until](../standard-library/algorithm-functions.md#is_heap_until)|Döndürür `true` belirtilen aralık kadar son öğe yığın oluşturuyorsa.|
|[is_partitioned](../standard-library/algorithm-functions.md#is_partitioned)|Döndürür `true` verilen aralıktaki tüm öğeleri test durumunda `true` bir koşul gelen için test herhangi bir öğe önce `false`.|
|[is_permutation](../standard-library/algorithm-functions.md#is_permutation)|Geçerli bir nesne form öğelerinin belirli bir aralık içinde olup olmadığını belirler.|
|[is_sorted](../standard-library/algorithm-functions.md#is_sorted)|Döndürür `true` Belirtilen aralıktaki öğeleri sıralanmış olarak ise.|
|[is_sorted_until](../standard-library/algorithm-functions.md#is_sorted_until)|Döndürür `true` Belirtilen aralıktaki öğeleri sıralanmış olarak ise.|
|[iter_swap](../standard-library/algorithm-functions.md#iter_swap)|Belirtilen yineleyicilerin bir çifti tarafından başvurulan iki değeri birbiriyle değiştirir.|
|[lexicographical_compare](../standard-library/algorithm-functions.md#lexicographical_compare)|Daha küçük olanı belirlemek için iki diziyi öğe öğe karşılaştırır.|
|[lower_bound](../standard-library/algorithm-functions.md#lower_bound)|Sıralı bir aralıkta belirtilen değere eşit ya da daha büyük bir değere sahip ilk öğenin konumunu bulur, burada sıralama kriteri bir ikili koşula göre belirtilebilir.|
|[make_heap](../standard-library/algorithm-functions.md#make_heap)|Belirtilen bir aralıktaki öğeleri ilk öğenin en büyük olduğu ve onun için bir ikili koşula sahip bir sıralama ölçütünün belirtilebildiği bir yığına dönüştürür.|
|[max](../standard-library/algorithm-functions.md#max)|İki nesneyi karşılaştırır ve ikisinden büyük olanı döndürür, burada sıralama ölçütü ikili bir koşula göre belirtilebilir.|
|[max_element](../standard-library/algorithm-functions.md#max_element)|Belirtilen bir aralıktaki en büyük öğenin geçtiği ilk yeri bulur, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.|
|[Birleştirme](../standard-library/algorithm-functions.md#merge)|İki sıralanmış kaynak aralıktaki tüm öğeleri tek bir sıralanmış aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.|
|[Min](../standard-library/algorithm-functions.md#min)|İki nesneyi karşılaştırır ve ikisinden küçük olanı döndürür, burada sıralama ölçütü ikili bir koşula göre belirtilebilir.|
|[min_element](../standard-library/algorithm-functions.md#min_element)|Belirtilen bir aralıktaki en küçük öğenin geçtiği ilk yeri bulur, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.|
|[minmax](../standard-library/algorithm-functions.md#minmax)|İki giriş parametresini karşılaştırır ve bunları küçükten büyüğe bir çift olarak döndürür.|
|[minmax_element](../standard-library/algorithm-functions.md#minmax_element)|Tarafından gerçekleştirilen çalışma gerçekleştirir [min_element](../standard-library/algorithm-functions.md#min_element) ve [max_element](../standard-library/algorithm-functions.md#max_element) bir çağrısında.|
|[uyuşmazlığı](../standard-library/algorithm-functions.md#mismatch)|Eşitlik ya da denklik için ikili bir koşul tarafından belirtildiği şekilde iki aralığı öğe öğe karşılaştırır ve farkın oluştuğu ilk yeri bulur.|
|[&lt;algoritma&gt; Taşı](../standard-library/algorithm-functions.md#alg_move)|Belirtilen aralıkla ilişkili öğeleri taşı.|
|[move_backward](../standard-library/algorithm-functions.md#move_backward)|Bir yineleyicinin öğelerini diğerine taşır. Hareket belirli bir aralıktaki son öğeyle başlar ve söz konusu aralıktaki ilk öğeyle biter.|
|[next_permutation](../standard-library/algorithm-functions.md#next_permutation)|Aralıktaki öğeleri yeniden sıralar, böylece özgün sıralama sözlüksel biçimde, varsa, bir sonraki permütasyon ile değiştirilir, burada sonraki bir ikili koşula göre belirtilebilir.|
|[none_of](../standard-library/algorithm-functions.md#none_of)|Döndürür `true` bir koşul olduğunda hiçbir zaman belirtilen aralıkta öğeler arasında mevcut.|
|[nth_element](../standard-library/algorithm-functions.md#nth_element)|Öğeleri doğru bulma, çeşitli bölümlerini *n*th öğesi aralığında sırasının küçük veya ona eşit ve sırayla izlenmesi tüm öğelerin önünde tüm öğeleri; böylece daha büyük veya eşit kendisine.|
|[partial_sort](../standard-library/algorithm-functions.md#partial_sort)|Bir aralıktaki daha küçük öğelerin belirtilen sayısını azalmayan şekilde veya bir ikili koşul tarafından belirtilen bir sıralama ölçütüne göre düzenler.|
|[partial_sort_copy](../standard-library/algorithm-functions.md#partial_sort_copy)|Öğeleri bir kaynak aralığından bir hedef aralığa kopyalar, burada kaynak öğeleri daha küçük olana ya da belirtilen başka bir ikili koşula göre sıralanır.|
|[Bölüm](../standard-library/algorithm-functions.md#partition)|Bir aralıktaki öğeleri, onları karşılamada yetersiz koşulu önceleyen birli koşulu sağlayan öğelerle iki ayrık kümede sınıflandırır.|
|[partition_copy](../standard-library/algorithm-functions.md#partition_copy)|Bir koşul olduğu öğeleri kopyalar `true` bir hedefe ve koşul olan `false` başka bir. Öğeler belirtilen bir aralıktan gelmelidir.|
|[partition_point](../standard-library/algorithm-functions.md#partition_point)|Koşulu karşılamayan verili aralıktaki ilk öğeyi döndürür. Öğeler koşulu karşılayanlar karşılamayanlardan önce gelecek şekilde sıralanır.|
|[pop_heap](../standard-library/algorithm-functions.md#pop_heap)|En büyük öğeyi bir yığının önünden aralıktaki bir sonraki son konuma kaldırır ve ardından kalan öğelerden yeni bir yığın oluşturur.|
|[prev_permutation](../standard-library/algorithm-functions.md#prev_permutation)|Aralıktaki öğeleri yeniden sıralar, böylece özgün sıralama sözlüksel biçimde, varsa, bir sonraki permütasyon ile değiştirilir, burada sonraki bir ikili koşula göre belirtilebilir.|
|[push_heap](../standard-library/algorithm-functions.md#push_heap)|Aralığın sonundaki bir öğeyi aralıktaki önceki öğeleri içeren mevcut yığına ekler.|
|[random_shuffle](../standard-library/algorithm-functions.md#random_shuffle)|Bir dizi yeniden düzenler *N* birini aralığına öğelerinde *N*! olası düzenlemeleri rastgele seçilmiş.|
|[remove](../standard-library/algorithm-functions.md#remove)|Kalan öğelerin sırasını bozmadan ve belirtilen değerin yeni aralığının sonunu boş döndürerek verili aralıktaki belirtilen bir değeri ortadan kaldırır.|
|[remove_copy](../standard-library/algorithm-functions.md#remove_copy)|Öğeleri, belirtilen değerin kopyalanmayan öğeleri hariç, kalan öğelerin sırasını bozmadan ve yeni hedef aralığın sonuna döndürerek bir kaynak aralıktan bir hedef aralığa kopyalar.|
|[remove_copy_if](../standard-library/algorithm-functions.md#remove_copy_if)|Öğeleri, bir koşulu karşılayan kopyalanmayan öğeler hariç, kalan öğelerin sırasını bozmadan ve yeni hedef aralığın sonuna döndürerek bir kaynak aralıktan bir hedef aralığa kopyalar.|
|[remove_if](../standard-library/algorithm-functions.md#remove_if)|Kalan öğelerin sırasını bozmadan ve belirtilen değerin yeni aralığının sonunu boş döndürerek verili aralıktaki bir koşulu karşılayan öğeleri ortadan kaldırır.|
|[Değiştir](../standard-library/algorithm-functions.md#replace)|Bir aralıktaki tüm öğeleri inceler ve belirtilen bir değerle eşleşiyorsa değiştirir.|
|[replace_copy](../standard-library/algorithm-functions.md#replace_copy)|Bir kaynak aralığındaki her öğeyi inceler ve sonuç yeni bir hedef aralığına kopyalanırken öğe belirtilen değerle eşleşiyorsa, onu değiştirir.|
|[replace_copy_if](../standard-library/algorithm-functions.md#replace_copy_if)|Bir kaynak aralığındaki her öğeyi inceler ve sonuç yeni bir hedef aralığına kopyalanırken öğe belirtilen bir koşulu karşılıyorsa, onu değiştirir.|
|[replace_if](../standard-library/algorithm-functions.md#replace_if)|Bir aralıktaki tüm öğeleri inceler ve belirtilen bir koşulu karşılıyorsa değiştirir.|
|[Ters Çevir](../standard-library/algorithm-functions.md#reverse)|Bir aralık içindeki öğelerin sırasını tersine çevirir.|
|[reverse_copy](../standard-library/algorithm-functions.md#reverse_copy)|Bir hedef aralığına kopyalanırken bir kaynak aralığındaki öğelerin sırasını tersine çevirir|
|[döndürme](../standard-library/algorithm-functions.md#rotate)|İki bitişik aralık içindeki öğeleri birbiriyle değiştirir.|
|[rotate_copy](../standard-library/algorithm-functions.md#rotate_copy)|Bir kaynak aralık içindeki iki bitişik aralıktaki öğeleri birbiriyle değiştirir ve sonucu bir hedef aralığına kopyalar.|
|[Arama](../standard-library/algorithm-functions.md#search)|Öğeleri verili bir öğe dizisi içindekilerle eşit olan veya öğeleri verili bir dizi öğe için ikili bir koşula göre belirtildiği şekilde denk olan bir hedef aralığındaki dizinin ilk geçtiği yeri arar.|
|[search_n](../standard-library/algorithm-functions.md#search_n)|Belirli bir değere veya ikili bir koşula göre belirtilen değerle bir ilişkiye sahip olan öğelerin belirli bir sayısının aralığındaki ilk diziyi arar.|
|[set_difference](../standard-library/algorithm-functions.md#set_difference)|Sıralanmış ikinci bir kaynak aralığına sahip olanları değil, sıralanmış bir kaynak aralığına sahip öğelerin tümünü tek, sıralanmış bir hedef aralığı içinde birleştirir, burada sıralama ölçütü ikili bir koşula göre belirtilebilir.|
|[set_intersection](../standard-library/algorithm-functions.md#set_intersection)|Her iki sıralanmış kaynak aralığa sahip öğelerin tümünü tek, sıralanmış bir aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.|
|[set_symmetric_difference](../standard-library/algorithm-functions.md#set_symmetric_difference)|İki değil, tek bir sıralanmış kaynak aralığa sahip öğelerin tümünü tek, sıralanmış bir aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.|
|[set_union](../standard-library/algorithm-functions.md#set_union)|İki sıralanmış kaynak aralığından en az birine sahip öğelerin tümünü tek, sıralanmış bir aralıkta birleştirir, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.|
|[Sıralama](../standard-library/algorithm-functions.md#sort)|Belirtilen bir aralıktaki öğeleri azalmayan şekilde veya bir ikili koşul tarafından belirtilen bir sıralama ölçütüne göre düzenler.|
|[karışık](../standard-library/algorithm-functions.md#shuffle)|Rastgele sayı oluşturucusunu kullanarak belirli bir aralık için seçeneği (yeniden düzenler) öğeleri.|
|[sort_heap](../standard-library/algorithm-functions.md#sort_heap)|Bir yığını sıralanmış bir aralığa dönüştürür.|
|[stable_partition](../standard-library/algorithm-functions.md#stable_partition)|Bir aralıktaki öğeleri, eşdeğer öğelerin göreli sırasını koruyaraktan, onları karşılamada yetersiz koşulu önceleyen birli koşulu sağlayan öğelerle iki ayrık kümede sınıflandırır.|
|[stable_sort](../standard-library/algorithm-functions.md#stable_sort)|Belirtilen bir aralıktaki öğeleri, eşdeğer öğelerin göreli sıralamasını koruyaraktan, azalmayan şekilde veya bir ikili koşul tarafından belirtilen bir sıralama ölçütüne göre düzenler.|
|[Değiştirme](../standard-library/algorithm-functions.md#swap)|İlk nesnenin içeriğini ikinci nesneye ve ikinci nesneni içeriğini birinciye atayarak, nesnelerin iki türü arasındaki öğelerin değerlerini birbiriyle değiştirir.|
|[swap_ranges](../standard-library/algorithm-functions.md#swap_ranges)|Bir aralığın öğelerini eşit büyüklükteki bir diğerinin öğeleriyle değiştirir.|
|[transform](../standard-library/algorithm-functions.md#transform)|Belirtilen işlev nesnesini bir kaynak aralıktaki her bir öğeye veya iki kaynak aralıktaki bir öğe çiftine uygular ve işlev nesnenin dönüş değerlerini bir hedef aralığa kopyalar.|
|[Benzersiz](../standard-library/algorithm-functions.md#unique)|Belirli bir aralıktaki birbirine bitişik yinelenen öğeleri kaldırır.|
|[unique_copy](../standard-library/algorithm-functions.md#unique_copy)|Birbirine bitişik yinelenen öğeler hariç bir kaynak aralıktaki öğeleri hedef aralığa kopyalar.|
|[upper_bound](../standard-library/algorithm-functions.md#upper_bound)|Belirtilenden daha büyük bir değere sahip sıralı bir aralıktaki ilk öğenin konumunu bulur, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
