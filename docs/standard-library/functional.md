---
title: '&lt;işlev&gt;'
ms.date: 02/21/2019
f1_keywords:
- <functional>
- functional/std::<functional>
- std::<functional>
helpviewer_keywords:
- functors
- functional header
ms.assetid: 7dd463e8-a29f-49bc-aedd-8fa53b54bfbc
ms.openlocfilehash: 317344db856a7a0568aca422ecfe8280b80db097
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159424"
---
# <a name="ltfunctionalgt"></a>&lt;işlev&gt;

Oluşturmaya yardımcı olan C++ Standart Kitaplığı işlevleri tanımlar *işlev nesneleri*olarak da bilinen *işlev nesneleri*ve bunların bağlayıcılar. Bir nesne tanımlayan bir tür bir işlev nesnesidir `operator()`. Bir işlev nesnesi bir işlev işaretçisi olabilir, ancak nesne daha genel bir işlev çağrısı sırasında erişilebilir ek bilgileri depolamak için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <functional>
```

## <a name="remarks"></a>Açıklamalar

İşlev nesneleri iki tür algoritmalar gerektirir: *birli* ve *ikili*. Birli işlevi nesneleri bir bağımsız değişken gerektirir ve ikili fonksiyon nesneleri iki bağımsız değişken gerektirir. İşlev işaretçileri ve işlev nesnesi bir koşul için bir algoritma geçirilebilir, ancak işlev nesneleri de uyarlanabilir ve kapsam, esneklik ve C++ Standart Kitaplığı verimliliğini artırın. Örneğin, bir algoritmaya geçirilmeden önce bir işleve bağlanacak bir değer gerekli olursa, işlev işaretçisi kullanılamadı. İşlev bağdaştırıcıları değerine bağlı uyarlanabilir işlev nesneleri işlev işaretçilerinin dönüştürün. Üst bilgi \<işlevsel > üye işlevleri uyarlanabilir işlev nesneleri çağrılacak izin üye işlevi bağdaştırıcıları de içerir. İşlevler, kendi bağımsız değişkenini belirleyen iç içe geçmiş tür bildirimleri oluşturulduysa uyarlanabilir ve dönüş türleri. İşlev nesneleri ve bunların bağdaştırıcıları mevcut uygulamaları yükseltebilir ve kitaplığı C++ programlama ortamına tümleştirmenize yardımcı C++ Standart Kitaplığı izin verir.

İşlev nesneleri uygulamasını \<işlevsel > içerir *saydam işleç işlev nesneleri*. Standart işlev nesneleri uzmanlıkları ve hiçbir şablon parametre ve işlev bağımsız değişkenlerinin kusursuz iletme ve sonucun mükemmel dönüş gerçekleştirebilirsiniz. Bu şablon uzmanlıkları aritmetik, mantıksal, karşılaştırma ve bit düzeyinde işleç işlev nesneleri çağırdığınızda, bağımsız değişken türleri belirtmenizi gerektirmez. Kendi türlerinizi veya heterojen birleşimlerini türleri aritmetik, mantıksal, karşılaştırma veya bit düzeyinde işleçler aşırı ve saydam işleç işlev nesneleri işlev bağımsız değişkenleri kullanın. Örneğin, türünüz *MyType* uygulayan `operator<`, çağırabilirsiniz `sort(my_collection.begin(), my_collection.end(), less<>())` türü açıkça belirtmeyi yerine `sort(my_collection.begin(), my_collection.end(), less<MyType>())`.

Aşağıdaki özellikler, C ++ 11, C ++ 14 ve C ++ 17 eklenir:

- A *çağrı imzası* parantez içinde virgülle ayrılmış listesini sıfır veya daha fazla bağımsız değişken türleri tarafından izlenen bir dönüş türü adıdır.

- A *çağrılabilir türü* işlevi, üye işlevi işaretçisi, üye verilerine bir işaretçi veya bir sınıf türü nesneleri bir işlev çağrısı işleci soldan hemen görüntülenebilir işaretçisidir.

- A *çağrılabilir nesne* çağrılabilir türünde bir nesnedir.

- A *çağrı sarmalayıcı türü* çağrılabilir nesnesi tutar ve bu nesneye ileten bir çağrı işlemi destekleyen bir türdür.

- A *çağrı sarmalayıcı* çağrı sarmalayıcı türü bir nesnedir.

- A *hedef nesne* çağrı sarmalayıcı nesne tarafından tutulan çağrılabilir nesnesi.

Sözde işlevi `INVOKE(f, t1, t2, ..., tN)` aşağıdaki şeylerden biri anlamına gelir:

- `(t1.*f)(t2, ..., tN)` zaman `f` sınıfının üye işlevinde işaretçisidir `T` ve `t1` türünde bir nesnedir `T` veya türünde bir nesne başvurusu `T` veya türetilmiş bir türde bir nesne başvuru `T`.

- `((*t1).*f)(t2, ..., tN)` zaman `f` sınıfının üye işlevinde işaretçisidir `T` ve `t1` önceki öğede açıklanan türlerinden biri değil.

- `t1.*f` zaman N 1 == ve `f` bir sınıfın üye verileri işaretçisidir `T` ve `t1` türünde bir nesnedir `T` veya türünde bir nesne başvurusu `T` veya türetilmiş bir türde bir nesne başvuru `T`.

- `(*t1).*f` zaman N 1 == ve `f` bir sınıfın üye verileri işaretçisidir `T` ve `t1` önceki öğede açıklanan türlerinden biri değil.

- `f(t1, t2, ..., tN)` Diğer durumlarda.

Sözde işlevi `INVOKE(f, t1, t2, ..., tN, R)` anlamına gelir `INVOKE(f, t1, t2, ..., tN)` örtük olarak dönüştürülebilir `R`.

Çağrı sarmalayıcı varsa bir *zayıf sonuç türü*, üye türünü türünü `result_type` türüne göre `T` aşağıdaki gibi sarmalayıcı hedef nesnenin:

- Varsa `T` işlev işaretçisidir `result_type` dönüş türünü eşanlamlıdır `T`.

- Varsa `T` üye işlevi işaretçisi olan `result_type` dönüş türünü eşanlamlıdır `T`.

- Varsa `T` üye türüne sahip bir sınıf türü `result_type`, ardından `result_type` eşanlamlıdır `T::result_type`.

- Aksi takdirde, hiç üye yok `result_type`.

Her çağrı sarmalayıcı bir taşıma oluşturucusuna ve kopya Oluşturucusu vardır. A *basit çağrısı sarmalayıcı* atama işleci ve, kopya Oluşturucu, taşıma oluşturucu ve atama işleci değil throw özel durumları olan bir çağrı sarmalayıcıdır. A *çağrı sarmalayıcı iletme* Sarmalanan çağrılabilir nesnesine başvuru olarak bağımsız değişkenler sunan ve rastgele bağımsız değişken listesi kullanılarak çağrılabilen bir çağrı sarmalayıcıdır. Tüm rvalue bağımsız değişken rvalue başvuruları teslim edilir ve lvalue bağımsız değişkenlerini lvalue başvuruları sunulur.

## <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[bad_function_call](../standard-library/bad-function-call-class.md)|Bir çağrı göstermek için bir özel durum tanımlayan bir sınıfı `operator()` üzerinde bir [işlevi](../standard-library/function-class.md) nesne nesnesi boş olduğundan başarısız oldu.|
|[binary_negate](../standard-library/binary-negate-class.md)|Belirtilen bir ikili fonksiyon dönüş değeri verilerek bir üye işlevi sağlayan bir şablon sınıfı.<br/> (C ++ 17'de kullanım dışı) |
|[binder1st](../standard-library/binder1st-class.md)|Bir ikili fonksiyon nesnesi belirtilen değere ikili işlevinin ilk bağımsız değişkeni bağlayarak birli nesnesine dönüştürür. bir oluşturucu sağlayan bir şablon sınıfı.<br/> (C ++ 17 sürümünde kaldırılmıştır C ++ 11 ' de kullanımdan.) |
|[binder2nd](../standard-library/binder2nd-class.md)|Bir ikili fonksiyon nesnesi belirtilen değere ikili işlevinin ikinci bağımsız değişkeni bağlayarak birli nesnesine dönüştürür. bir oluşturucu sağlayan bir şablon sınıfı.<br/> (C ++ 17 sürümünde kaldırılmıştır C ++ 11 ' de kullanımdan.) |
|[const_mem_fun_ref_t](../standard-library/const-mem-fun-ref-t-class.md)|Bir başvuru bağımsız değişkeni ile hazırlarken bir birli işlev nesnesi olarak çağrılacak hiçbir bağımsız değişken const bir üye işlevi sağlayan bir bağdaştırıcı sınıfı.<br/> (C ++ 17 sürümünde kaldırılmıştır C ++ 11 ' de kullanımdan.) |
|[const_mem_fun_t](../standard-library/const-mem-fun-t-class.md)|Hiçbir bağımsız değişken bir işaretçi bağımsız değişkeni ile hazırlarken bir birli işlev nesnesi olarak çağrılacak const bir üye işlevi sağlayan bir bağdaştırıcı sınıfı.<br/> (C ++ 17 sürümünde kaldırılmıştır C ++ 11 ' de kullanımdan.) |
|[const_mem_fun1_ref_t](../standard-library/const-mem-fun1-ref-t-class.md)|Bir başvuru bağımsız değişkeni ile hazırlarken bir ikili fonksiyon nesnesi olarak çağrılan tek bir bağımsız değişken alan sabit bir üye işlevi sağlayan bir bağdaştırıcı sınıfı.<br/> (C ++ 17 sürümünde kaldırılmıştır C ++ 11 ' de kullanımdan.) |
|[const_mem_fun1_t](../standard-library/const-mem-fun1-t-class.md)|Bir işaretçi bağımsız değişkeni ile hazırlarken bir ikili fonksiyon nesnesi olarak çağrılan tek bir bağımsız değişken alan sabit bir üye işlevi sağlayan bir bağdaştırıcı sınıfı.<br/> (C ++ 17 sürümünde kaldırılmıştır C ++ 11 ' de kullanımdan.) |
|[İşlevi](../standard-library/function-class.md)|Çağrılabilir nesnesini saran bir sınıf.|
|[Karma](../standard-library/hash-class.md)|Bir değer için bir karma kod hesaplar sınıfı.|
|[is_bind_expression](../standard-library/is-bind-expression-class.md)|Belirli bir tür çağırarak oluşturulursa, testleri bir sınıf `bind`.|
|[is_placeholder](../standard-library/is-placeholder-class.md)|Bir yer tutucu belirli bir tür olup olmadığını test eden bir sınıf.|
|[mem_fun_ref_t](../standard-library/mem-fun-ref-t-class.md)|İzin veren bir bağdaştırıcı sınıfı bir `non_const` hiçbir bağımsız değişken olarak bir başvuru bağımsız değişkeni ile hazırlarken bir birli işlev nesnesi çağrılacak üye işlevi.<br/> (C ++ 17 sürümünde kaldırılmıştır C ++ 11 ' de kullanımdan.) |
|[mem_fun_t](../standard-library/mem-fun-t-class.md)|İzin veren bir bağdaştırıcı sınıfı bir `non_const` hiçbir bağımsız değişken bir işaretçi bağımsız değişkeni ile hazırlarken bir birli işlev nesnesi olarak çağrılacak üye işlevi.<br/> (C ++ 17 sürümünde kaldırılmıştır C ++ 11 ' de kullanımdan.) |
|[mem_fun1_ref_t](../standard-library/mem-fun1-ref-t-class.md)|İzin veren bir bağdaştırıcı sınıfı bir `non_const` bir başvuru bağımsız değişkeni ile hazırlarken bir ikili fonksiyon nesnesi olarak çağrılan tek bir bağımsız değişken alan üye işlevi.<br/> (C ++ 17 sürümünde kaldırılmıştır C ++ 11 ' de kullanımdan.) |
|[mem_fun1_t](../standard-library/mem-fun1-t-class.md)|İzin veren bir bağdaştırıcı sınıfı bir `non_const` bir işaretçi bağımsız değişkeni ile hazırlarken bir ikili fonksiyon nesnesi olarak çağrılan tek bir bağımsız değişken alan üye işlevi.<br/> (C ++ 17 sürümünde kaldırılmıştır C ++ 11 ' de kullanımdan.) |
|[pointer_to_binary_function](../standard-library/pointer-to-binary-function-class.md)|Bir ikili fonksiyon işaretçi ikili uyarlanabilir bir işleve dönüştürür.<br/> (C ++ 17 sürümünde kaldırılmıştır C ++ 11 ' de kullanımdan.) |
|[pointer_to_unary_function](../standard-library/pointer-to-unary-function-class.md)|Birli işlevi işaretçisi uyarlanabilir birli bir işleve dönüştürür.<br/> (C ++ 17 sürümünde kaldırılmıştır C ++ 11 ' de kullanımdan.) |
|[reference_wrapper](../standard-library/reference-wrapper-class.md)|Bir başvuru saran bir sınıf.|
|[unary_negate](../standard-library/unary-negate-class.md)|Belirtilen birli işlevi dönüş değeri verilerek bir üye işlevi sağlayan bir şablon sınıfı.<br/> (C ++ 17'de kullanım dışı)  |

## <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[bağlama](../standard-library/functional-functions.md#bind)|Bağımsız değişkenler çağrılabilir nesnesine bağlar.|
|[bind1st](../standard-library/functional-functions.md#bind1st)|Bir ikili fonksiyon nesnesi belirtilen değere ikili işlevinin ilk bağımsız değişkeni bağlayarak birli nesnesine dönüştürmek için bir bağdaştırıcı oluşturan yardımcı şablonu işlev.<br/> (C ++ 17 sürümünde kaldırılmıştır C ++ 11 ' de kullanımdan.) |
|[bind2nd](../standard-library/functional-functions.md#bind2nd)|Bir ikili fonksiyon nesnesi belirtilen değere ikili işlevinin ikinci bağımsız değişkeni bağlayarak birli nesnesine dönüştürmek için bir bağdaştırıcı oluşturan yardımcı şablonu işlev.<br/> (C ++ 17 sürümünde kaldırılmıştır C ++ 11 ' de kullanımdan.) |
|[bit_and](../standard-library/functional-functions.md#bit_and)|Mantıksal AND bit düzeyinde döndürür (ikili işleç &) iki parametre.|
|[bit_not](../standard-library/functional-functions.md#bit_not)|Mantıksal bit düzeyinde tamamlayıcı döndürür (işleci ~) parametre.<br/> (C ++ 14'te eklenir.) |
|[bit_or](../standard-library/functional-functions.md#bit_or)|Bit Mantıksal OR döndürür (işleci&#124;) iki parametre.|
|[bit_xor](../standard-library/functional-functions.md#bit_xor)|Mantıksal bit düzeyinde XOR döndürür (operator ^) iki parametre.|
|[cref](../standard-library/functional-functions.md#cref)|Bir const yapıları `reference_wrapper` bir bağımsız.|
|[mem_fn](../standard-library/functional-functions.md#mem_fn)|Basit Arama bir sarmalayıcı oluşturur.|
|[mem_fun](../standard-library/functional-functions.md#mem_fun)|İşaretçi bağımsız değişkenler ile hazırlarken üye işlevler için işlev nesnesi bağdaştırıcıları oluşturmak için kullanılan yardımcı şablon işlevleri.<br/> (C ++ 17 sürümünde kaldırılmıştır C ++ 11 ' de kullanımdan.) |
|[mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref)|İşlev nesnesi bağdaştırıcılarını başvuru bağımsız değişkenleri ile hazırlarken üye işlevleri oluşturmak için kullanılan bir yardımcı şablon işlevi.|
|[Not1](../standard-library/functional-functions.md#not1)|Birli koşulu tümleme döndürür.<br/> (C ++ 17'de kullanım dışı) |
|[not2](../standard-library/functional-functions.md#not2)|Bir ikili koşula tümleme döndürür.<br/> (C ++ 17'de kullanım dışı) |
|[not_fn](../standard-library/functional-functions.md#not_fn)|Kendi işlev nesnesinin sonucu tümleme döndürür.<br/> (C ++ 17'de eklenir.) |
|[ptr_fun](../standard-library/functional-functions.md#ptr_fun)|Yardımcı bir şablonu işlev tekli veya ikili uyarlanabilir işlevleri, işaretçiler, sırasıyla dönüştürme birli ve ikili fonksiyon için kullanılır.<br/> (C ++ 17 sürümünde kaldırılmıştır C ++ 11 ' de kullanımdan.) |
|[ref](../standard-library/functional-functions.md#ref)|Oluşturur bir `reference_wrapper` bir bağımsız.|
|[değiştirme](../standard-library/functional-functions.md#swap)|İki değiştirir `function` nesneleri.|

## <a name="structs"></a>Yapılar

|Yapı|Açıklama|
|-|-|
|[binary_function](../standard-library/binary-function-struct.md)|Bir ikili bir işlev nesnesi sağlayan türetilmiş sınıf tarafından devralınan türlerini tanımlar boş bir temel sınıf.<br/> (C ++ 17 sürümünde kaldırılmıştır C ++ 11 ' de kullanımdan.) |
|[bölen](../standard-library/divides-struct.md)|Sınıfı, belirtilen değer türü öğeleri üzerinde bölümünün aritmetik işlemi gerçekleştiren bir önceden tanımlanmış bir işlev nesnesi sağlar.|
|[equal_to](../standard-library/equal-to-struct.md)|Belirtilen türde bir değer olup olmadığını test bir ikili koşul türü başka bir değere eşittir.|
|[daha büyük](../standard-library/greater-struct.md)|Belirtilen türde bir değer olup olmadığını test bir ikili koşul türü başka bir değerden büyüktür.|
|[greater_equal](../standard-library/greater-equal-struct.md)|Bir değeri belirtilen bir türün değerinden büyük veya bu türün başka bir değere eşit olup olmadığını test bir ikili koşul.|
|[daha az](../standard-library/less-struct.md)|Belirtilen türde bir değer olup olmadığını test bir ikili koşula başka bir değer türü'dan küçük.|
|[less_equal](../standard-library/less-equal-struct.md)|Belirtilen türde bir değer ya da başka bir değer türü eşit olup olmadığını test bir ikili koşul.|
|[logical_and](../standard-library/logical-and-struct.md)|Sınıf birlikte'nın mantıksal işleyişini öğeleri belirtilen değer türü ve testler için basit veya sonucun falsity gerçekleştirir. önceden tanımlanmış bir işlev nesnesi sağlar.|
|[logical_not](../standard-library/logical-not-struct.md)|Sınıf, öğeler belirtilen değer türü ve testler için basit veya sonucun falsity mantıksal değilleme işlemi gerçekleştiren bir önceden tanımlanmış bir işlev nesnesi sağlar.|
|[logical_or](../standard-library/logical-or-struct.md)|Sınıf, öğeler belirtilen değer türü ve testler için basit veya sonucun falsity mantıksal veya işlecini işlemi gerçekleştiren bir önceden tanımlanmış bir işlev nesnesi sağlar.|
|[eksi](../standard-library/minus-struct.md)|Sınıfı, belirtilen değer türü öğeleri üzerinde aritmetik çıkarma işlemi gerçekleştiren bir önceden tanımlanmış bir işlev nesnesi sağlar.|
|[mod](../standard-library/modulus-struct.md)|Sınıfı, belirtilen değer türü öğeleri üzerinde modulus aritmetik işlemi gerçekleştiren bir önceden tanımlanmış bir işlev nesnesi sağlar.|
|[multiplies](../standard-library/multiplies-struct.md)|Sınıfı, belirtilen değer türü öğeleri üzerinde aritmetik çarpma işlemi gerçekleştiren bir önceden tanımlanmış bir işlev nesnesi sağlar.|
|[negate](../standard-library/negate-struct.md)|Sınıf, negatif bir öğe değeri döndüren bir önceden tanımlanmış bir işlev nesnesi sağlar.|
|[not_equal_to](../standard-library/not-equal-to-struct.md)|Belirtilen türde bir değer olup olmadığını test bir ikili koşula bu türün başka bir değerine eşit değil.|
|[artı](../standard-library/plus-struct.md)|Sınıfı, belirtilen değer türü öğeleri üzerinde aritmetik toplama işlemi gerçekleştiren bir önceden tanımlanmış bir işlev nesnesi sağlar.|
|[unary_function](../standard-library/unary-function-struct.md)|Birli işlev nesnesi sağlayan türetilmiş sınıf tarafından devralınan türlerini tanımlar boş bir temel sınıf.<br/> (C ++ 17 sürümünde kaldırılmıştır C ++ 11 ' de kullanımdan.) |

## <a name="objects"></a>Nesneler

|Nesne|Açıklama|
|-|-|
|[_1.._M](../standard-library/1-object.md)|Değiştirilebilir bağımsız değişkenleri için yer tutucu.|

## <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator==](../standard-library/functional-operators.md#op_eq_eq)|Eşitlik karşılaştırma çağrılabilir nesnelerin izin vermiyor.|
|[operator!=](../standard-library/functional-operators.md#op_neq)|Eşitsizlik karşılaştırma çağrılabilir nesnelerin izin vermiyor.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
