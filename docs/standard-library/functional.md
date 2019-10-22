---
title: '&lt;functional &gt;'
ms.date: 02/21/2019
f1_keywords:
- <functional>
- functional/std::<functional>
- std::<functional>
helpviewer_keywords:
- functors
- functional header
ms.assetid: 7dd463e8-a29f-49bc-aedd-8fa53b54bfbc
ms.openlocfilehash: 67b2ccf70b4d3045cecd13d9096875f77c4cde9a
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689627"
---
# <a name="ltfunctionalgt"></a>&lt;functional &gt;

*İşlev nesnelerinin*ve bunların ciltlerini oluşturmaya yardımcı olan standart kitaplık işlevlerini tanımlar. C++ İşlev nesnesi `operator()` tanımlayan bir türün nesnesidir. Bir işlev nesnesi bir işlev işaretçisi olabilir, ancak genellikle nesne, bir işlev çağrısı sırasında erişilebilen ek bilgileri depolamak için kullanılır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<functional >

**Ad alanı:** std

## <a name="remarks"></a>Açıklamalar

Algoritmalar iki tür işlev nesnesi gerektirir: *birli* ve *ikili*. Birli işlev nesneleri bir bağımsız değişken gerektirir ve ikili işlev nesneleri iki bağımsız değişken gerektirir. Bir işlev nesnesi ve işlev işaretçileri bir algoritmaya bir koşul olarak geçirilebilir, ancak işlev nesneleri de uyarlanabilir ve C++ standart kitaplığın kapsamını, esnekliğini ve verimliliğini artırır. Örneğin, bir algoritmaya geçirilmeden önce bir işleve bağlanması gereken bir değer varsa, bir işlev işaretçisi kullanılamadı. İşlev bağdaştırıcıları, işlev işaretçilerini bir değere bağlanabilen, uyarlanamaz işlev nesnelerine dönüştürür. Üst bilgi \<functional >, üye işlevlerinin uyarlanabilir tablo işlevi nesneleri olarak çağrılmasına izin veren üye işlev bağdaştırıcılarını de içerir. Bağımsız değişkenleri ve dönüş türlerini belirten iç içe tür bildirimlerine sahip olmaları durumunda işlevler uyarlanabilir. İşlev nesneleri ve bağdaştırıcıları, C++ standart kitaplığın mevcut uygulamaları yükseltmesine ve kitaplığı C++ programlama ortamıyla tümleştirmesine izin verir.

@No__t_0functional > işlev nesnelerinin uygulanması *saydam işleç*işlevlerini içerir. Standart işlev nesnelerinin özelleştirilmesi ve hiçbir şablon parametresi almaz ve işlev bağımsız değişkenlerinin kusursuz bir şekilde iletilmesini ve sonucun tam bir döndürmesini gerçekleştirir. Bu şablon Uzmanlıkları aritmetik, karşılaştırma, mantıksal ve bit düzeyinde işleç özelliklerini çağırdığınızda bağımsız değişken türlerini belirtmenizi gerektirmez. Kendi türlerinizin aritmetik, karşılaştırma, mantıksal veya bit düzeyinde operatörlerini aşırı yükleyebilir veya türlerin heterojen bileşimleri için, daha sonra saydam işleç işlevlerini işlev bağımsız değişkeni olarak kullanabilirsiniz. Örneğin, *MyType* türü `operator<` uygularsa, açıkça tür `sort(my_collection.begin(), my_collection.end(), less<MyType>())` belirtmek yerine `sort(my_collection.begin(), my_collection.end(), less<>())` çağırabilirsiniz.

Aşağıdaki özellikler C++ 11, C++ 14 ve C++ 17 ' ye eklenmiştir:

- *Çağrı imzası* , bir dönüş türünün, ardından sıfır veya daha fazla bağımsız değişken türündeki parantez içinde virgülle ayrılmış bir liste olan addır.

- *Çağrılabilir tür* bir işlev işaretçisi, üye işlevi işaretçisi, üye verilerine yönelik bir işaretçi veya nesneleri bir işlev çağrısı işlecinin hemen solunda görünebilen bir sınıf türü.

- *Çağrılabilir bir nesne* çağrılabilir bir türün nesnesidir.

- *Çağrı sarmalayıcı türü* , çağrılabilir bir nesneyi tutan ve bu nesneye ileten bir çağrı işlemini destekleyen bir türdür.

- *Çağrı sarmalayıcısı* , çağrı sarmalayıcı türünün bir nesnesidir.

- *Hedef nesne* , çağrı sarmalayıcı nesnesi tarafından tutulan çağrılabilir nesnedir.

Sözde işlev `INVOKE(f, t1, t2, ..., tN)`, aşağıdaki işlemlerden birini gösterir:

- `f`, `T` sınıfının üye işlevine yönelik bir işaretçi olduğunda ve `t1` `T` türünde bir nesne ya da `T` türünden türetilmiş bir tür nesnesine başvuru olduğunda `(t1.*f)(t2, ..., tN)`.

- `f`, `T` sınıfının üye işlevine yönelik bir işaretçi olduğunda `((*t1).*f)(t2, ..., tN)` ve `t1` önceki öğede açıklanan türlerden biri değildir.

- N = = 1 ve `f` bir sınıf `T` üye verilerine yönelik bir işaretçisiyse ve `t1`, `T` türünde bir nesne veya türetilmiş bir tür nesnesine bir başvuru olan bir `t1.*f`. `T`.

- N = = 1 ve `f` bir sınıf `T` üye verilerine yönelik işaretçisiyse ve `t1` önceki öğede açıklanan türlerden biri değilse `(*t1).*f`.

- diğer tüm durumlarda `f(t1, t2, ..., tN)`.

Sözde işlev `INVOKE(f, t1, t2, ..., tN, R)` `INVOKE(f, t1, t2, ..., tN)` örtük olarak `R` dönüştürülen anlamına gelir.

Bir çağrı sarmalayıcısı *zayıf bir sonuç türüne*sahipse, `result_type` üye türünün türü sarmalayıcının hedef nesnesinin `T` türüne göre aşağıdaki gibi olur:

- @No__t_0 bir işlev işaretçisiyse, `result_type` `T` dönüş türünün eşanlamlısıdır.

- @No__t_0 bir üye işlevi işaretçisiyse, `result_type` `T` dönüş türü için bir eş anlamlı olur.

- @No__t_0, `result_type` üye türüne sahip bir sınıf türüdür `result_type` `T::result_type` için bir eş anlamlı olur.

- Aksi takdirde, `result_type` üye yoktur.

Her çağrı sarmalayıcısı bir taşıma Oluşturucusu ve bir kopya Oluşturucu içerir. *Basit Çağrı sarmalayıcısı* , atama işleci olan ve kopya Oluşturucu, taşıma Oluşturucusu ve atama işleci özel durum oluşturmaz olmayan bir çağrı sarmalayıcısı. Bir *iletme çağrısı sarmalayıcısı* , rastgele bir bağımsız değişken listesi kullanılarak çağrılabilen ve sarmalanmış çağrılabilir nesnesine başvuru olarak gelen bağımsız değişkenleri teslim eden bir çağrı sarmalayıcısıdır. Tüm rvalue bağımsız değişkenleri, Rvalue başvuruları olarak dağıtılır ve lvalue bağımsız değişkenleri lvalue başvuruları olarak dağıtılır.

## <a name="members"></a>Üyeler

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[bad_function_call](../standard-library/bad-function-call-class.md)|Nesne boş olduğu için bir [işlev](../standard-library/function-class.md) nesnesi üzerinde `operator()` çağrısının başarısız olduğunu belirten bir özel durumu tanımlayan bir sınıf.|
|[binary_negate](../standard-library/binary-negate-class.md)|Belirtilen bir ikili işlevin dönüş değerini geçersiz hale getirmeden bir üye işlevi sağlayan bir sınıf şablonu.<br/> (C++ 17 ' de kullanım dışı.) |
|[binder1st](../standard-library/binder1st-class.md)|İkili işlevin ilk bağımsız değişkenini belirtilen bir değere bağlayarak bir ikili işlev nesnesini birli işlev nesnesine dönüştüren bir Oluşturucu sağlayan bir sınıf şablonu.<br/> (C++ 11 ' de kullanım dışı, C++ 17 ' de kullanımdan kaldırılmıştır.) |
|[binder2nd](../standard-library/binder2nd-class.md)|İkili işlevin ikinci bağımsız değişkenini belirtilen bir değere bağlayarak bir ikili işlev nesnesini birli işlev nesnesine dönüştüren bir Oluşturucu sağlayan bir sınıf şablonu.<br/> (C++ 11 ' de kullanım dışı, C++ 17 ' de kullanımdan kaldırılmıştır.) |
|[boyer_moore_horspool_searcher](../standard-library/boyer-moore-horspool-searcher-class.md)||
|[boyer_moore_searcher](../standard-library/boyer-moore-searcher-class.md)||
|[const_mem_fun_ref_t](../standard-library/const-mem-fun-ref-t-class.md)|Bir başvuru bağımsız değişkeniyle başlatıldığında birli işlev nesnesi olarak çağrılması için bağımsız değişken alan bir const üye işlevine izin veren bir bağdaştırıcı sınıfı.<br/> (C++ 11 ' de kullanım dışı, C++ 17 ' de kullanımdan kaldırılmıştır.) |
|[const_mem_fun_t](../standard-library/const-mem-fun-t-class.md)|Bir işaretçi bağımsız değişkeniyle başlatıldığında tek bir işlev nesnesi olarak çağrılması için bağımsız değişken alan bir const üye işlevine izin veren bir bağdaştırıcı sınıfı.<br/> (C++ 11 ' de kullanım dışı, C++ 17 ' de kullanımdan kaldırılmıştır.) |
|[const_mem_fun1_ref_t](../standard-library/const-mem-fun1-ref-t-class.md)|Bir başvuru bağımsız değişkeniyle başlatıldığında bir ikili işlev nesnesi olarak çağrılması için tek bir bağımsız değişken alan bir const üye işlevine izin veren bir bağdaştırıcı sınıfı.<br/> (C++ 11 ' de kullanım dışı, C++ 17 ' de kullanımdan kaldırılmıştır.) |
|[const_mem_fun1_t](../standard-library/const-mem-fun1-t-class.md)|Bir işaretçi bağımsız değişkeniyle başlatıldığında bir ikili işlev nesnesi olarak çağrılması için tek bir bağımsız değişken alan bir const üye işlevine izin veren bir bağdaştırıcı sınıfı.<br/> (C++ 11 ' de kullanım dışı, C++ 17 ' de kullanımdan kaldırılmıştır.) |
|[default_searcher](../standard-library/default-searcher-class.md)||
|[çalışmayacaktır](../standard-library/function-class.md)|Çağrılabilir bir nesneyi sarmalayan sınıf.|
|[yla](../standard-library/hash-class.md)|Bir değer için karma kodu hesaplayan sınıf.|
|[is_bind_expression](../standard-library/is-bind-expression-class.md)|@No__t_0 çağırarak belirli bir tür oluşturulursa test eden sınıf.|
|[is_placeholder](../standard-library/is-placeholder-class.md)|Belirli bir tür yer tutucu ise test eden bir sınıf.|
|[mem_fun_ref_t](../standard-library/mem-fun-ref-t-class.md)|Bir başvuru bağımsız değişkeniyle başlatıldığında bir birli işlev nesnesi olarak çağrılması için bağımsız değişken alan `non_const` üye işlevine izin veren bir bağdaştırıcı sınıfı.<br/> (C++ 11 ' de kullanım dışı, C++ 17 ' de kullanımdan kaldırılmıştır.) |
|[mem_fun_t](../standard-library/mem-fun-t-class.md)|Bir işaretçi bağımsız değişkeniyle başlatıldığında tek bir işlev nesnesi olarak çağrılması için bağımsız değişken alan bir `non_const` üye işlevine izin veren bir bağdaştırıcı sınıfı.<br/> (C++ 11 ' de kullanım dışı, C++ 17 ' de kullanımdan kaldırılmıştır.) |
|[mem_fun1_ref_t](../standard-library/mem-fun1-ref-t-class.md)|Bir başvuru bağımsız değişkeniyle başlatıldığında bir ikili işlev nesnesi olarak çağrılması için tek bir bağımsız değişken alan `non_const` üye işlevine izin veren bir bağdaştırıcı sınıfı.<br/> (C++ 11 ' de kullanım dışı, C++ 17 ' de kullanımdan kaldırılmıştır.) |
|[mem_fun1_t](../standard-library/mem-fun1-t-class.md)|Bir işaretçi bağımsız değişkeniyle başlatıldığında bir ikili işlev nesnesi olarak çağrılması için tek bir bağımsız değişken alan `non_const` üye işlevine izin veren bir bağdaştırıcı sınıfı.<br/> (C++ 11 ' de kullanım dışı, C++ 17 ' de kullanımdan kaldırılmıştır.) |
|[pointer_to_binary_function](../standard-library/pointer-to-binary-function-class.md)|Bir ikili işlev işaretçisini uyarlanabilir tablo ikili işlevine dönüştürür.<br/> (C++ 11 ' de kullanım dışı, C++ 17 ' de kullanımdan kaldırılmıştır.) |
|[pointer_to_unary_function](../standard-library/pointer-to-unary-function-class.md)|Birli işlev işaretçisini uyarlanabilir tablo birli işlevine dönüştürür.<br/> (C++ 11 ' de kullanım dışı, C++ 17 ' de kullanımdan kaldırılmıştır.) |
|[reference_wrapper](../standard-library/reference-wrapper-class.md)|Bir başvuruyu sarmalayan sınıf.|
|[unary_negate](../standard-library/unary-negate-class.md)|Belirtilen birli işlevin dönüş değerini geçersiz hale getirmeden bir üye işlevi sağlayan bir sınıf şablonu.<br/> (C++ 17 ' de kullanım dışı.)  |

### <a name="functions"></a>İşlevler

|||
|-|-|
|[bağladığınızda](../standard-library/functional-functions.md#bind)|Bağımsız değişkenleri çağrılabilir bir nesneye bağlar.|
|[bind1st](../standard-library/functional-functions.md#bind1st)|İkili işlevin ilk bağımsız değişkenini belirtilen bir değere bağlayarak bir ikili işlev nesnesini birli işlev nesnesine dönüştürmek için bir bağdaştırıcı oluşturan bir yardımcı şablon işlevi.<br/> (C++ 11 ' de kullanım dışı, C++ 17 ' de kullanımdan kaldırılmıştır.) |
|[bind2nd](../standard-library/functional-functions.md#bind2nd)|İkili işlevin ikinci bağımsız değişkenini belirtilen bir değere bağlayarak bir ikili işlev nesnesini birli işlev nesnesine dönüştürmek için bir bağdaştırıcı oluşturan bir yardımcı şablon işlevi.<br/> (C++ 11 ' de kullanım dışı, C++ 17 ' de kullanımdan kaldırılmıştır.) |
|[bit_and](../standard-library/functional-functions.md#bit_and)|İki parametrenin bit düzeyinde mantıksal ve (ikili işleç &) döndürür.|
|[bit_not](../standard-library/functional-functions.md#bit_not)|Parametrenin bit düzeyinde mantıksal tamamlama (işleç ~) değerini döndürür.<br/> (C++ 14 ' te eklenmiştir.) |
|[bit_or](../standard-library/functional-functions.md#bit_or)|İki parametrenin bit düzeyinde mantıksal OR (&#124;işleci) döndürür.|
|[bit_xor](../standard-library/functional-functions.md#bit_xor)|İki parametrenin bit düzeyinde mantıksal XOR (operator ^) değerini döndürür.|
|[cref](../standard-library/functional-functions.md#cref)|Bir bağımsız değişkenden const `reference_wrapper` oluşturur.|
|[Resync](../standard-library/functional-functions.md#invoke)||
|[mem_fn](../standard-library/functional-functions.md#mem_fn)|Basit bir çağrı sarmalayıcısı üretir.|
|[mem_fun](../standard-library/functional-functions.md#mem_fun)|İşaretçi bağımsız değişkenleriyle başlatıldığında üye işlevleri için işlev nesne bağdaştırıcıları oluşturmak için kullanılan yardımcı Şablon işlevleri.<br/> (C++ 11 ' de kullanım dışı, C++ 17 ' de kullanımdan kaldırılmıştır.) |
|[mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref)|Başvuru bağımsız değişkenleriyle başlatıldığında üye işlevleri için işlev nesne bağdaştırıcıları oluşturmak için kullanılan bir yardımcı şablon işlevi.|
|[Not1](../standard-library/functional-functions.md#not1)|Birli koşulun tamamlayıcısını döndürür.<br/> (C++ 17 ' de kullanım dışı.) |
|[NOT2](../standard-library/functional-functions.md#not2)|İkili koşulun tamamlayıcısını döndürür.<br/> (C++ 17 ' de kullanım dışı.) |
|[not_fn](../standard-library/functional-functions.md#not_fn)|İşlev nesnesinin sonucunun tamamlayıcısını döndürür.<br/> (C++ 17 ' de eklendi.) |
|[ptr_fun](../standard-library/functional-functions.md#ptr_fun)|Sırasıyla birli ve ikili işlev işaretçilerini tekil ve ikili Uyarlamalı tablo işlevlerine dönüştürmek için kullanılan bir yardımcı şablon işlevi.<br/> (C++ 11 ' de kullanım dışı, C++ 17 ' de kullanımdan kaldırılmıştır.) |
|[ref](../standard-library/functional-functions.md#ref)|Bağımsız değişkenden bir `reference_wrapper` oluşturur.|
|[Kur](../standard-library/functional-functions.md#swap)|İki `function` nesnesini değiştirir.|

### <a name="structs"></a>Yapılar

|||
|-|-|
|[binary_function](../standard-library/binary-function-struct.md)|Bir ikili işlev nesnesi sağlayan türetilmiş sınıf tarafından devralınabilir olabilecek türleri tanımlayan boş bir temel sınıf.<br/> (C++ 11 ' de kullanım dışı, C++ 17 ' de kullanımdan kaldırılmıştır.) |
|[bölme](../standard-library/divides-struct.md)|Sınıfı, belirtilen değer türünün öğelerinde bölümün aritmetik işlemini gerçekleştiren önceden tanımlanmış bir işlev nesnesi sağlar.|
|[equal_to](../standard-library/equal-to-struct.md)|Belirtilen türde bir değerin o türdeki başka bir değere eşit olup olmadığını test eden bir ikili koşul.|
|[ilerisi](../standard-library/greater-struct.md)|Belirtilen türde bir değerin o türdeki başka bir değerden büyük olup olmadığını test eden bir ikili koşul.|
|[greater_equal](../standard-library/greater-equal-struct.md)|Belirtilen türde bir değerin o türdeki başka bir değerden büyük veya ona eşit olup olmadığını test eden bir ikili koşul.|
|[büyüktür](../standard-library/less-struct.md)|Belirtilen türde bir değerin o türdeki başka bir değerden küçük olup olmadığını test eden bir ikili koşul.|
|[less_equal](../standard-library/less-equal-struct.md)|Belirtilen türde bir değerin o türdeki başka bir değerden küçük veya ona eşit olup olmadığını test eden bir ikili koşul.|
|[logical_and](../standard-library/logical-and-struct.md)|Sınıfı, belirli bir değer türünün öğelerine birlikte mantıksal işlem gerçekleştiren, önceden tanımlanmış bir işlev nesnesi sağlar ve sonucun gerçeği veya falsity için test eder.|
|[logical_not](../standard-library/logical-not-struct.md)|Sınıfı, belirli bir değer türünün öğelerinde Olumsuzlaştırma mantıksal işlemini gerçekleştiren, daha önceden tanımlanmış bir işlev nesnesi sağlar ve sonucun gerçeği veya falsity için test eder.|
|[logical_or](../standard-library/logical-or-struct.md)|Sınıfı, belirtilen bir değer türünün öğelerinde disbirleşimin mantıksal işlemini gerçekleştiren önceden tanımlanmış bir işlev nesnesi sağlar ve sonucun gerçeği veya falsity için test eder.|
|[dakini](../standard-library/minus-struct.md)|Sınıfı, belirtilen değer türünün öğelerinde çıkarma işleminin aritmetik işlemini gerçekleştiren önceden tanımlanmış bir işlev nesnesi sağlar.|
|[matematiksel](../standard-library/modulus-struct.md)|Sınıfı, belirtilen değer türünün öğeleri üzerinde mod 'un aritmetik işlemini gerçekleştiren önceden tanımlanmış bir işlev nesnesi sağlar.|
|[çarpan](../standard-library/multiplies-struct.md)|Sınıfı, belirtilen değer türünün öğelerinde çarpma işleminin aritmetik işlemini gerçekleştiren önceden tanımlanmış bir işlev nesnesi sağlar.|
|[Negate](../standard-library/negate-struct.md)|Sınıfı, bir öğe değerinin negatifini döndüren önceden tanımlanmış bir işlev nesnesi sağlar.|
|[not_equal_to](../standard-library/not-equal-to-struct.md)|Belirtilen türde bir değerin o türdeki başka bir değere eşit olup olmadığını test eden bir ikili koşul.|
|[artı](../standard-library/plus-struct.md)|Sınıfı, belirtilen bir değer türünün öğelerine eklenen aritmetik işlemi gerçekleştiren önceden tanımlanmış bir işlev nesnesi sağlar.|
|[unary_function](../standard-library/unary-function-struct.md)|Birli işlev nesnesi sağlayan türetilmiş sınıf tarafından devralınabilir olabilecek türleri tanımlayan boş bir temel sınıf.<br/> (C++ 11 ' de kullanım dışı, C++ 17 ' de kullanımdan kaldırılmıştır.) |

### <a name="objects"></a>Nesneler

|||
|-|-|
|[_1.. _D](../standard-library/1-object.md)|Değiştirilebilen bağımsız değişkenler için yer tutucular.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç = =](../standard-library/functional-operators.md#op_eq_eq)|Çağrılabilir nesnelerin eşitlik karşılaştırmasına izin vermez.|
|[operator!=](../standard-library/functional-operators.md#op_neq)|Çağrılabilir nesnelerin eşitsizlik karşılaştırmasına izin vermez.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md) \
[Standart kitaplıkta Iş parçacığı güvenliği \ C++ ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
