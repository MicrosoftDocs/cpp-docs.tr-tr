---
title: "&lt;işlev&gt; | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <functional>
- functional/std::<functional>
- std::<functional>
dev_langs: C++
helpviewer_keywords:
- functors
- functional header
ms.assetid: 7dd463e8-a29f-49bc-aedd-8fa53b54bfbc
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 036da9664c7b61e55e1322f12de3d9c8f72c3f53
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ltfunctionalgt"></a>&lt;işlev&gt;
Oluşturmaya yardımcı olması C++ Standart Kitaplığı işlevleri tanımlar *işlev nesneleri*— olarak da bilinen functors — ve bunların bağlayıcıları. Nesneyi tanımlayan bir türde bir işlev nesnesidir `operator()`. İşlev nesnesi bir işlev işaretçisi olabilir, ancak nesne daha tipik olarak, bir işlev çağrısı sırasında erişilebilir ek bilgi depolamak için kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#include <functional>  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Algoritmalar gerektiren işlev nesneleri iki tür: Birli ve ikili. Birli işlev nesneleri bir bağımsız değişken gerektirir ve ikili işlev nesneleri iki bağımsız değişken gerektirir. İşlev nesnesi ve işlev işaretçileri bir algoritma için bir koşul geçirilebilir, ancak işlev nesneleri de uyarlanabilir ve kapsam, esneklik ve C++ Standart Kitaplığı verimliliğini artırır. Örneğin, bir değer için bir algoritma iletilmeden önce bir işleve bağlanması gerekirse, bir işlev işaretçisi kullanılamadı. İşlev bağdaştırıcıları değerine bağlı uyarlanabilir işlev nesneleri işlev işaretçileri dönüştürün. Üstbilgi \<işlevsel > üye izin uyarlanabilir işlevi nesneler olarak çağrılacak işlevler üyesi işlevi bağdaştırıcıları de içerir. İşlevleri iç içe geçmiş tür bildirimleri kendi bağımsız değişkeni belirtme varsa uyarlanabilir ve dönüş türleri. C++ Standart unary_function veya binary_function temel sınıflardan devralan tüm standart nesne sınıfları sağlayarak bu uyumluluk uygulanır gerektirir. İşlev nesneleri ve bunların bağdaştırıcıları mevcut uygulamaları yükseltme ve kitaplığı C++ programlama ortamına tümleştirmenize yardımcı olmak C++ Standart Kitaplığı izin verir.  
  
 Visual C++ uygulaması işlevi nesnelerinin \<işlevsel > içerir *saydam işleci functors*, hangi özelleştirmeleri standart işlev nesneleri ve hiç şablon parametre almaz ve işlev bağımsız değişkenleri, kusursuz iletme ve sonucun kusursuz return gerçekleştirin. Bu özellik, C ++ 14 taslak standart belirtimi bir parçasıdır. Bu şablon özelleştirmeleri aritmetik, karşılaştırma, mantıksal ve bit düzeyinde işleci functors çağırdığınızda bağımsız değişken türleri belirtmeniz gerekmez. Aritmetik, karşılaştırma, mantıksal veya bit düzeyinde işleçler türleri heterojen birleşimlerini ya da kendi türleri için aşırı yükleme ve saydam işleci functors işlev bağımsız değişkenleri olarak kullanın. Örneğin, varsa türünüz *MyType* uygulayan `operator<`, çağırabilirsiniz `sort(my_collection.begin(), my_collection.end(), less<>())` açıkça türünü belirtme yerine `sort(my_collection.begin(), my_collection.end(), less<MyType>())`.  
  
## <a name="c11c14-implementation"></a>C ++ 11 / C ++ 14 uygulama  
 C ++ 14 11 / C ++ Visual C++ uygulamasında aşağıdaki özellikler eklendi:  
  
-   A *çağrısı imza* parantez içine alınmış virgülle ayrılmış listesini sıfır veya daha fazla bağımsız değişken türleri tarafından izlenen bir dönüş türü adıdır.  
  
-   A *aranabilir türü* gösteren bir işaretçidir işlevi, üye işlevi için bir işaretçi, üye verilerini gösteren bir işaretçi veya bir sınıf türü, nesneleri bir işlev çağırma işleci soluna hemen görüntülenebilir.  
  
-   A *aranabilir nesne* aranabilir türünde bir nesnedir.  
  
-   A *çağrısı sarmalayıcı türü* aranabilir nesnesi tutar ve bu nesneye ileten bir çağrı işlemi destekleyen bir türüdür.  
  
-   A *çağrısı sarmalayıcı* çağrısı sarmalayıcı türünde bir nesnedir.  
  
-   A *hedef nesne* bir çağrı sarmalayıcı nesnesi tarafından tutulan aranabilir nesnesi.  
  
 Sözde işlevi `INVOKE(f, t1, t2, ..., tN)` aşağıdakilerden birini anlamına gelir:  
  
- `(t1.*f)(t2, ..., tN)`zaman `f` gösteren bir işaretçidir sınıfının üye işlevini `T` ve `t1` türünde bir nesne `T` veya türünde bir nesne başvurusu `T` veya türetilmiş bir türün bir nesneye bir başvurusu `T`.  
  
- `((*t1).*f)(t2, ..., tN)`zaman `f` gösteren bir işaretçidir sınıfının üye işlevini `T` ve `t1` önceki öğede açıklanan türlerinden biri değil.  
  
- `t1.*f`zaman N 1 == ve `f` gösteren bir işaretçidir bir sınıf üyesi verilerinin `T` ve `t1` türünde bir nesne `T` veya türünde bir nesne başvurusu `T` veya türetilmiş bir türün bir nesneye bir başvurusu `T`.  
  
- `(*t1).*f`zaman N 1 == ve `f` gösteren bir işaretçidir bir sınıf üyesi verilerinin `T` ve `t1` önceki öğede açıklanan türlerinden biri değil.  
  
- `f(t1, t2, ..., tN)`Diğer durumlarda.  
  
 Sözde işlevi `INVOKE(f, t1, t2, ..., tN, R)` anlamına gelir `INVOKE(f, t1, t2, ..., tN)` örtük olarak dönüştürülebilir `R`.  
  
 Çağrı sarmalayıcı varsa bir *zayıf sonuç türü*, kendi üye türündeki `result_type` türüne göre `T` şekilde sarmalayıcı hedef nesnenin:  
  
-   Varsa `T` gösteren bir işaretçidir işlevi, `result_type` dönüş türü için eş anlamlı olduğundan `T`.  
  
-   Varsa `T` gösteren bir işaretçidir üye işlevi `result_type` dönüş türü için eş anlamlı olduğundan `T`.  
  
-   Varsa `T` üye türüne sahip bir sınıf türü `result_type`, ardından `result_type` eşanlamlısı olduğu `T::result_type`.  
  
-   Aksi takdirde, hiç üye yok `result_type`.  
  
 Her çağrı sarmalayıcı bir taşıma oluşturucusuna ve kopya Oluşturucu vardır. A *basit aramayı sarmalayıcı* atama işleci ve, kopya Oluşturucu, taşıma oluşturucusuna ve atama işleci değil throw özel durumlara sahip bir çağrı sarmalayıcı değil. A *çağrısı sarmalayıcı iletme* bir rastgele bağımsız değişken listesi kullanılarak çağrılabilir bir çağrı sarmalayıcı olduğunu ve bağımsız değişkenler başvuru olarak Sarmalanan aranabilir nesnesine sunan. Tüm rvalue bağımsız değişkenleri rvalue başvuru olarak teslim edilir ve lvalue bağımsız değişkenleri lvalue başvuru olarak teslim edilir.  
  
### <a name="classes"></a>Sınıflar  
  
|||  
|-|-|  
|[bad_function_call](../standard-library/bad-function-call-class.md)|Çağrı belirtmek için bir özel durum tanımlayan bir sınıf `operator()` üzerinde bir [işlevi](../standard-library/function-class.md) nesne nesne boş olduğundan başarısız oldu.|  
|[binary_negate](../standard-library/binary-negate-class.md)|Belirtilen ikili işlevinin dönüş değeri üzerindeki geçersiz kılar üye işlevi sağlayan bir şablon sınıfı.|  
|[binder1st](../standard-library/binder1st-class.md)|İkili işlevinin ilk bağımsız değişken belirtilen değere bağlama tarafından ikili işlev nesnesi bir birli işlevi nesnesine dönüştürür bir oluşturucu sağlayan bir şablon sınıfı.|  
|[binder2nd](../standard-library/binder2nd-class.md)|İkili işlevinin ikinci bağımsız değişkeni belirtilen değere bağlama tarafından ikili işlev nesnesi bir birli işlevi nesnesine dönüştürür bir oluşturucu sağlayan bir şablon sınıfı.|  
|[const_mem_fun_ref_t](../standard-library/const-mem-fun-ref-t-class.md)|Bir başvuru bağımsız değişkeni ile hazırlarken birli işlevi nesnesi olarak çağrılacak bağımsız değişken almayan const bir üye işlevi sağlayan bir bağdaştırıcı sınıfı.|  
|[const_mem_fun_t](../standard-library/const-mem-fun-t-class.md)|Bir işaretçi bağımsız değişkeni ile hazırlarken birli işlevi nesnesi olarak çağrılacak bağımsız değişken almayan const bir üye işlevi sağlayan bir bağdaştırıcı sınıfı.|  
|[const_mem_fun1_ref_t](../standard-library/const-mem-fun1-ref-t-class.md)|Bir başvuru bağımsız değişkeni ile hazırlarken ikili işlevi nesnesi olarak çağrılacak tek bir bağımsız değişken const bir üye işlevi sağlayan bir bağdaştırıcı sınıfı.|  
|[const_mem_fun1_t](../standard-library/const-mem-fun1-t-class.md)|Bir işaretçi bağımsız değişkeni ile hazırlarken ikili işlevi nesnesi olarak çağrılacak tek bir bağımsız değişken const bir üye işlevi sağlayan bir bağdaştırıcı sınıfı.|  
|[işlevi](../standard-library/function-class.md)|Aranabilir nesne saran bir sınıf.|  
|[karma](../standard-library/hash-class.md)|Bir değer için bir karma kod hesaplar bir sınıf.|  
|[is_bind_expression](../standard-library/is-bind-expression-class.md)|Belirli bir tür çağırarak oluşturulursa, testleri bir sınıf `bind`.|  
|[is_placeholder](../standard-library/is-placeholder-class.md)|Belirli bir türün bir yer tutucu ise testleri bir sınıf.|  
|[mem_fun_ref_t](../standard-library/mem-fun-ref-t-class.md)|Sağlayan bir bağdaştırıcı sınıfı bir **non_const** bir başvuru bağımsız değişkeni ile hazırlarken birli işlevi nesnesi olarak çağrılacak bağımsız değişken almayan üye işlevi.|  
|[mem_fun_t](../standard-library/mem-fun-t-class.md)|Sağlayan bir bağdaştırıcı sınıfı bir **non_const** bir işaretçi bağımsız değişkeni ile hazırlarken birli işlevi nesnesi olarak çağrılacak bağımsız değişken almayan üye işlevi.|  
|[mem_fun1_ref_t](../standard-library/mem-fun1-ref-t-class.md)|Sağlayan bir bağdaştırıcı sınıfı bir **non_const** bir başvuru bağımsız değişkeni ile hazırlarken ikili işlevi nesnesi olarak çağrılacak tek bir bağımsız değişken üye işlevi.|  
|[mem_fun1_t](../standard-library/mem-fun1-t-class.md)|Sağlayan bir bağdaştırıcı sınıfı bir **non_const** bir işaretçi bağımsız değişkeni ile hazırlarken ikili işlevi nesnesi olarak çağrılacak tek bir bağımsız değişken üye işlevi.|  
|[pointer_to_binary_function](../standard-library/pointer-to-binary-function-class.md)|Bir ikili işlev işaretçisi uyarlanabilir ikili işlevdeki dönüştürür.|  
|[pointer_to_unary_function](../standard-library/pointer-to-unary-function-class.md)|Birli işlev işaretçisi uyarlanabilir birli işlevdeki dönüştürür.|  
|[reference_wrapper](../standard-library/reference-wrapper-class.md)|Bir başvuru saran bir sınıf.|  
|[unary_negate](../standard-library/unary-negate-class.md)|Belirtilen birli işlevinin dönüş değeri üzerindeki geçersiz kılar üye işlevi sağlayan bir şablon sınıfı.|  
  
### <a name="functions"></a>İşlevler  
  
|||  
|-|-|  
|[bağlama](../standard-library/functional-functions.md#bind)|Bağımsız değişkenler aranabilir nesnesine bağlar.|  
|[bind1st](../standard-library/functional-functions.md#bind1st)|İkili işlevinin ilk bağımsız değişken belirtilen değere bağlama tarafından ikili işlev nesnesi bir birli işlevi nesnesine dönüştürmek için bir bağdaştırıcı oluşturur Yardımcısı şablon işlevi.|  
|[bind2nd](../standard-library/functional-functions.md#bind2nd)|İkili işlevinin ikinci bağımsız değişkeni belirtilen değere bağlama tarafından ikili işlev nesnesi bir birli işlevi nesnesine dönüştürmek için bir bağdaştırıcı oluşturur Yardımcısı şablon işlevi.|  
|[bit_and](../standard-library/functional-functions.md#bit_and)|Bit düzeyinde mantıksal AND döndürür (ikili işleç &) iki parametre.|  
|[bit_not](../standard-library/functional-functions.md#bit_not)|Bit düzeyinde mantıksal tamamlama döndürür (işleci ~) parametre.|  
|[bit_or](../standard-library/functional-functions.md#bit_or)|Bit düzeyinde mantıksal OR döndürür (işleci &#124;) iki parametre.|  
|[bit_xor](../standard-library/functional-functions.md#bit_xor)|Bit düzeyinde mantıksal XOR döndürür (operator ^) iki parametre.|  
|[cref](../standard-library/functional-functions.md#cref)|Bir const yapıları `reference_wrapper` gelen bir bağımsız değişken.|  
|[mem_fn](../standard-library/functional-functions.md#mem_fn)|Basit Arama sarmalayıcı oluşturur.|  
|[mem_fun](../standard-library/functional-functions.md#mem_fun)|İşlev nesnesi bağdaştırıcıları işaretçi bağımsız değişkenlerle hazırlarken üye işlevleri için oluşturmak için kullanılan yardımcı şablon işlevleri.|  
|[mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref)|İşlev nesnesi bağdaştırıcıları başvuru bağımsız değişkenlerle hazırlarken üye işlevleri için oluşturmak için kullanılan yardımcı şablonu bir işlev.|  
|[Not1](../standard-library/functional-functions.md#not1)|Birli koşul tamamlama döndürür.|  
|[not2](../standard-library/functional-functions.md#not2)|İkili karşılaştırma tamamlama döndürür.|  
|[ptr_fun](../standard-library/functional-functions.md#ptr_fun)|Bir yardımcı şablon işlevi birli ve ikili uyarlanabilir işlevleri, işaretçileri, sırasıyla dönüştürme birli ve ikili işlevi için kullanılır.|  
|[ref](../standard-library/functional-functions.md#ref)|Oluşturan bir `reference_wrapper` gelen bir bağımsız değişken.|  
|[değiştirme](../standard-library/functional-functions.md#swap)|İki değiştirir `function` nesneleri.|  
  
### <a name="structs"></a>Yapılar  
  
|||  
|-|-|  
|[binary_function](../standard-library/binary-function-struct.md)|Bir ikili işlevi nesnesi sağlar türetilmiş sınıf tarafından devralınan türlerini tanımlar boş bir temel sınıf.|  
|[böler](../standard-library/divides-struct.md)|Sınıf belirtilen değer türü öğelerde bölümünün aritmetik işlemi gerçekleştiren bir önceden tanımlanmış işlev nesnesi sağlar.|  
|[equal_to](../standard-library/equal-to-struct.md)|Belirtilen türde bir değer türü başka bir değere eşit olup olmadığını sınar ikili koşulu.|  
|[büyük](../standard-library/greater-struct.md)|Belirtilen türde bir değer olup olmadığını sınar ikili bir koşul türü başka bir değerden daha büyük.|  
|[greater_equal](../standard-library/greater-equal-struct.md)|Belirtilen türde bir değer sıfırdan büyük veya bu türdeki başka bir değere eşit olup olmadığını sınar ikili koşulu.|  
|[daha az](../standard-library/less-struct.md)|Belirtilen türde bir değer olup olmadığını sınar ikili bir koşul türü başka bir değerden küçüktür.|  
|[less_equal](../standard-library/less-equal-struct.md)|Belirtilen türde bir değer küçük veya bu türdeki başka bir değere eşit olup olmadığını sınar ikili koşulu.|  
|[logical_and](../standard-library/logical-and-struct.md)|Sınıf belirtilen değer türü ve gerçekte için testleri öğelerini veya sonucunun falsity birlikte mantıksal işlemi gerçekleştiren bir önceden tanımlanmış işlev nesnesi sağlar.|  
|[logical_not](../standard-library/logical-not-struct.md)|Sınıf belirtilen değer türü ve gerçekte için testleri öğelerini veya falsity sonucunun değilleme mantıksal işlemi gerçekleştiren bir önceden tanımlanmış işlevi nesnesi sağlar.|  
|[logical_or](../standard-library/logical-or-struct.md)|Sınıf belirtilen değer türü ve gerçekte için testleri öğelerini veya falsity sonucunun ayrım mantıksal işlemi gerçekleştiren bir önceden tanımlanmış işlevi nesnesi sağlar.|  
|[eksi](../standard-library/minus-struct.md)|Sınıfı, belirtilen değer türü öğelerde çıkarma aritmetik işlemi gerçekleştiren bir önceden tanımlanmış işlevi nesnesi sağlar.|  
|[modulus](../standard-library/modulus-struct.md)|Sınıf belirtilen değer türü öğelerde modulus aritmetik işlemi gerçekleştiren bir önceden tanımlanmış işlev nesnesi sağlar.|  
|[çarpar](../standard-library/multiplies-struct.md)|Sınıf belirtilen değer türü öğelerde çarpma aritmetik işlemi gerçekleştiren bir önceden tanımlanmış işlev nesnesi sağlar.|  
|[negate](../standard-library/negate-struct.md)|Sınıfı bir öğe değerini negatif döndürür önceden tanımlanmış işlevi nesnesi sağlar.|  
|[not_equal_to](../standard-library/not-equal-to-struct.md)|Belirtilen türde bir değer olup olmadığını sınar ikili bir koşul türü başka bir değere eşit değil.|  
|[artı](../standard-library/plus-struct.md)|Sınıf belirtilen değer türü öğelerde toplama aritmetik işlemi gerçekleştiren bir önceden tanımlanmış işlev nesnesi sağlar.|  
|[unary_function](../standard-library/unary-function-struct.md)|Birli işlev nesnesi sağlar türetilmiş sınıf tarafından devralınan türlerini tanımlar boş bir temel sınıf.|  
  
### <a name="objects"></a>Nesneler  
  
|||  
|-|-|  
|[_1.._M](../standard-library/1-object.md)|Yer tutucuları değiştirebilen bağımsız değişkenler için.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[operator ==](../standard-library/functional-operators.md#op_eq_eq)|Eşitlik karşılaştırması aranabilir nesnelerin izin vermez.|  
|[operator!=](../standard-library/functional-operators.md#op_neq)|Eşitsizlik karşılaştırma aranabilir nesnelerin izin vermez.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)

