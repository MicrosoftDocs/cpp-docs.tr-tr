---
title: '&lt;type_traits&gt;'
ms.date: 02/21/2019
f1_keywords:
- <type_traits>
helpviewer_keywords:
- typetrait header
- type_traits
ms.assetid: 2260b51f-8160-4c66-a82f-00b534cb60d4
ms.openlocfilehash: 42c94daf331fd9a17e050067e4c4e495af180b0c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841707"
---
# <a name="lttype_traitsgt"></a>&lt;type_traits&gt;

Tür bağımsız değişkenlerinin özellikleri hakkında bilgi veren derleme zamanı sabitlerinin şablonlarını tanımlar veya dönüştürülmüş türler üretir.

## <a name="syntax"></a>Syntax

```cpp
#include <type_traits>
```

## <a name="remarks"></a>Açıklamalar

İçindeki sınıflar ve şablonlar, \<type_traits> derleme zamanında tür çıkarımı, sınıflandırma ve dönüştürmeyi desteklemek için kullanılır. Bunlar ayrıca, türle ilgili hataları algılamak ve genel kodunuzu iyileştirmenize yardımcı olmak için kullanılır. Birli tür nitelikleri bir türün özelliğini betimleyen, ikili tür nitelikleri türler arasındaki ilişkiyi tanımlıyor ve dönüştürme nitelikleri bir türün özelliğini değiştirir.

Yardımcı sınıfı `integral_constant` ve şablonu, `true_type` `false_type` tür koşullarına yönelik temel sınıfları özelleştirmeler ve oluşturur. *Tür koşulu* bir veya daha fazla tür bağımsız değişkeni alan bir şablondur. Bir tür koşulu *doğru taşıdığı*zaman, [true_type](../standard-library/type-traits-typedefs.md#true_type)doğrudan veya dolaylı olarak, genel olarak türetilir. Bir tür koşulu *yanlış taşıdığı*zaman, [false_type](../standard-library/type-traits-typedefs.md#false_type)doğrudan veya dolaylı olarak, genel olarak türetilir.

Bir *tür değiştirici* veya *dönüştürme nitelik* , bir veya daha fazla şablon bağımsız değişkeni alan ve `type` değiştirilmiş tür için bir eş anlamlı olan bir üyeye sahip olan bir şablondur.

### <a name="alias-templates"></a>Diğer ad şablonları

Tür nitelikleri ifadelerini basitleştirmek için, için [diğer ad şablonları](../cpp/aliases-and-typedefs-cpp.md) `typename some_trait<T>::type` sağlanır; burada *some_trait* sınıf şablonu adıdır. Örneğin [add_const](../standard-library/add-const-class.md) , türü için bir diğer ad şablonuna sahiptir, `add_const_t` şöyle tanımlanır:

```cpp
template <class T>
using add_const_t = typename add_const<T>::type;
```

Üyeler için belirtilen diğer adlar şunlardır `type` :

:::row:::
   :::column:::
      `add_const_t`\
      `add_cv_t`\
      `add_lvalue_reference_t`\
      `add_pointer_t`\
      `add_rvalue_reference_t`\
      `add_volatile_t`\
      `aligned_storage_t`\
      `aligned_union_t`\
   :::column-end:::
   :::column:::
      `common_type_t`\
      `conditional_t`\
      `decay_t`\
      `enable_if_t`\
      `invoke_result_t`\
      `make_signed_t`\
      `make_unsigned_t`\
      `remove_all_extents_t`\
   :::column-end:::
   :::column:::
      `remove_const_t`\
      `remove_cv_t`\
      `remove_extent_t`\
      `remove_pointer_t`\
      `remove_reference_t`\
      `remove_volatile_t`\
      `result_of_t`\
      `underlying_type_t`\
   :::column-end:::
:::row-end:::

### <a name="classes"></a>Sınıflar

Yardımcı sınıfı ve tür tanımları

|Ad|Açıklama|
|-|-|
|[integral_constant](../standard-library/integral-constant-class-bool-constant-class.md)|Bir tür ve değerden integral sabiti oluşturur.|
|[true_type](../standard-library/type-traits-typedefs.md#true_type)|Gerçek değer ile integral sabiti barındırır.|
|[false_type](../standard-library/type-traits-typedefs.md#false_type)|Tamsayı sabiti yanlış değerle tutar.|

Birincil tür kategorileri

|Ad|Açıklama|
|-|-|
|[is_void](../standard-library/is-void-class.md)|Türün olup olmadığını test eder **`void`** .|
|[is_null_pointer](../standard-library/is-null-pointer-class.md)|Türün olup olmadığını test eder `std::nullptr_t` .|
|[is_integral](../standard-library/is-integral-class.md)|Türün integral olup olmadığını test eder.|
|[is_floating_point](../standard-library/is-floating-point-class.md)|Türün kayan nokta olup olmadığını sınar.|
|[is_array](../standard-library/is-array-class.md)|Türün bir dizi olup olmadığını test eder.|
|[is_pointer](../standard-library/is-pointer-class.md)|Türün bir işaretçi olup olmadığını test eder.|
|[is_lvalue_reference](../standard-library/is-lvalue-reference-class.md)|Türün bir lvalue başvurusu olup olmadığını test eder.|
|[is_rvalue_reference](../standard-library/is-rvalue-reference-class.md)|Türün bir rvalue başvurusu olup olmadığını test eder.|
|[is_member_object_pointer](../standard-library/is-member-object-pointer-class.md)|Türün bir üye nesnesine bir işaretçi olup olmadığını test eder.|
|[is_member_function_pointer](../standard-library/is-member-function-pointer-class.md)|Türün bir üye işlevine yönelik bir işaretçi olup olmadığını test eder.|
|[is_enum](../standard-library/is-enum-class.md)|Türün bir numaralandırma olup olmadığını test eder.|
|[is_union](../standard-library/is-union-class.md)|Türün bir birleşim olup olmadığını test eder.|
|[is_class](../standard-library/is-class-class.md)|Türün bir sınıf olup olmadığını test eder.|
|[is_function](../standard-library/is-function-class.md)|Türün bir işlev türü olup olmadığını test eder.|

Bileşik tür kategorileri

|Ad|Açıklama|
|-|-|
|[is_reference](../standard-library/is-reference-class.md)|Türün bir başvuru olup olmadığını test eder.|
|[is_arithmetic](../standard-library/is-arithmetic-class.md)|Türün aritmetik olup olmadığını test eder.|
|[is_fundamental](../standard-library/is-fundamental-class.md)|Türün mi yoksa aritmetik mi olduğunu sınar **`void`** .|
|[is_object](../standard-library/is-object-class.md)|Türün bir nesne türü olup olmadığını test eder.|
|[is_scalar](../standard-library/is-scalar-class.md)|Türün skaler olup olmadığını test eder.|
|[is_compound](../standard-library/is-compound-class.md)|Türün skaler olup olmadığını test eder.|
|[is_member_pointer](../standard-library/is-member-pointer-class.md)|Türün bir üyeye işaretçi olup olmadığını test eder.|

Tür özellikleri

|Ad|Açıklama|
|-|-|
|[is_const](../standard-library/is-const-class.md)|Türün olup olmadığını test eder **`const`** .|
|[is_volatile](../standard-library/is-volatile-class.md)|Türün olup olmadığını test eder **`volatile`** .|
|[is_trivial](../standard-library/is-trivial-class.md)|Türün önemsiz olup olmadığını test eder.|
|[is_trivially_copyable](../standard-library/is-trivially-copyable-class.md)|Türün Üçlü kopyalanabilir olup olmadığını test eder.|
|[is_standard_layout](../standard-library/is-standard-layout-class.md)|Türün Standart Düzen türü olup olmadığını sınar.|
|[is_pod](../standard-library/is-pod-class.md)|Türün POD olup olmadığını test eder.|
|[is_literal_type](../standard-library/is-literal-type-class.md)|Türün bir **`constexpr`** değişken ya da bir işlevde kullanılıp kullanılamayacağını sınar **`constexpr`** .|
|[is_empty](../standard-library/is-empty-class.md)|Türün boş bir sınıf olup olmadığını test eder.|
|[is_polymorphic](../standard-library/is-polymorphic-class.md)|Türün çok biçimli bir sınıf olup olmadığını sınar.|
|[is_abstract](../standard-library/is-abstract-class.md)|Türün soyut bir sınıf olup olmadığını test eder.|
|[is_final](../standard-library/is-final-class.md)|Türün işaretlenmiş bir sınıf türü olup olmadığını sınar `final` .|
|[is_aggregate](../standard-library/is-aggregate-class.md)||
|[is_signed](../standard-library/is-signed-class.md)|Türün işaretli bir tamsayı olup olmadığını test eder.|
|[is_unsigned](../standard-library/is-unsigned-class.md)|Türün işaretsiz bir tamsayı olup olmadığını test eder.|
|[is_constructible](../standard-library/is-constructible-class.md)|Türün belirtilen bağımsız değişken türlerini kullanarak oluşturulabilir olup olmadığını test eder.|
|[is_default_constructible](../standard-library/type-traits-functions.md#is_default_constructible)|Türün varsayılan bir oluşturucuya sahip olup olmadığını sınar.|
|[is_copy_constructible](../standard-library/type-traits-functions.md#is_copy_constructible)|Türün bir kopya oluşturucusuna sahip olup olmadığını sınar.|
|[is_move_constructible](../standard-library/type-traits-functions.md#is_move_constructible)|Türün bir taşıma oluşturucusuna sahip olup olmadığını sınar.|
|[is_assignable](../standard-library/type-traits-functions.md#is_assignable)|İlk türe ikinci türden bir değer atanıp atanamayacağını sınar.|
|[is_copy_assignable](../standard-library/type-traits-functions.md#is_copy_assignable)|Türe bir tür const başvuru değeri atanıp atanamayacağını sınar.|
|[is_move_assignable](../standard-library/type-traits-functions.md#is_move_assignable)|Türe bir tür rvalue başvurusu atanıp atanamayacağını sınar.|
|[is_swappable](../standard-library/type-traits-functions.md#is_swappable)||
|[is_swappable_with](../standard-library/type-traits-functions.md#is_swappable_with)||
|[is_destructible](../standard-library/is-destructible-class.md)|Türün geri çevrilebilir olup olmadığını test eder.|
|[is_trivially_constructible](../standard-library/is-trivially-constructible-class.md)|Türün, belirtilen türleri kullanarak oluşturulduğunda önemsiz olmayan işlemler kullanıp kullanmadığını sınar.|
|[is_trivially_default_constructible](../standard-library/is-trivially-default-constructible-class.md)|Varsayılan oluşturulduğunda türün önemsiz olmayan işlemler kullanıp kullanmadığını sınar.|
|[is_trivially_copy_constructible](../standard-library/is-trivially-copy-constructible-class.md)|Kopya oluşturulduğunda türün önemsiz olmayan işlemler kullanıp kullanmadığını sınar.|
|[is_trivially_move_constructible](../standard-library/type-traits-functions.md#is_trivially_move_constructible)|Bir taşıma oluşturulduğunda türün önemsiz olmayan işlemler kullanıp kullanmadığını sınar.|
|[is_trivially_assignable](../standard-library/is-trivially-assignable-class.md)|Türlerin atanabilir olup olmadığını ve atamanın önemsiz olmayan işlemler kullanıp kullanmadığını sınar.|
|[is_trivially_copy_assignable](../standard-library/type-traits-functions.md#is_trivially_copy_assignable)|Türün kopyalanıp kopyalanmayacağını ve atamanın önemsiz olmayan işlemler kullanıp kullanmadığını sınar.|
|[is_trivially_move_assignable](../standard-library/type-traits-functions.md#is_trivially_move_assignable)|Tür için bir atama yapılıp yapılmayacağını ve atamanın önemsiz olmayan işlemler kullanmadığını sınar.|
|[is_trivially_destructible](../standard-library/is-trivially-destructible-class.md)|Türün geri dönüşlü ve yıkıcının önemsiz olmayan işlemler kullanıp kullanmadığını sınar.|
|[is_nothrow_constructible](../standard-library/is-nothrow-constructible-class.md)|Türün oluşturulabilir olup olmadığını test eder ve belirtilen türler kullanılarak oluşturulduğunda throw olarak bilinir.|
|[is_nothrow_default_constructible](../standard-library/is-nothrow-default-constructible-class.md)|Türün varsayılan oluşturulabilir olup olmadığını sınar ve varsayılan oluşturulduğunda throw olarak bilinir.|
|[is_nothrow_copy_constructible](../standard-library/is-nothrow-copy-constructible-class.md)|Türün kopya oluşturulabilir olup olmadığını test eder ve kopya Oluşturucu throw olarak bilinir.|
|[is_nothrow_move_constructible](../standard-library/is-nothrow-move-constructible-class.md)|Türe göre hareket edilip edilmeyeceğini sınar ve taşıma Oluşturucu throw olarak bilinir.|
|[is_nothrow_assignable](../standard-library/is-nothrow-assignable-class.md)|Türün belirtilen tür kullanılarak atanabilir olup olmadığını ve atamanın throw olarak bilinmediğini test eder.|
|[is_nothrow_copy_assignable](../standard-library/is-nothrow-copy-assignable-class.md)|Türün kopyalanıp kopyalanmayacağını ve atamanın throw olarak bilinmediğini test eder.|
|[is_nothrow_move_assignable](../standard-library/type-traits-functions.md#is_nothrow_move_assignable)|Türün eklenip eklenmeyeceğini ve atamanın throw olarak bilinmediğini sınar.|
|[is_nothrow_swappable](../standard-library/type-traits-functions.md#is_nothrow_swappable)||
|[is_nothrow_swappable_with](../standard-library/type-traits-functions.md#is_nothrow_swappable_with)||
|[is_nothrow_destructible](../standard-library/is-nothrow-destructible-class.md)|Türün geri çevrilebilir olup olmadığını ve yıkıcının throw olarak bilinmediğini sınar.|
|`has_virtual_destructor`|Türün bir sanal yok ediciye sahip olup olmadığını sınar.|
|`has_unique_object_representations`||
| [is_invocable](is-invocable-classes.md) | Çağrılabilir bir türün belirtilen bağımsız değişken türleri kullanılarak çağrılabileceğini sınar.<br/> C++ 17 ' ye eklenmiştir. |
| [is_invocable_r](is-invocable-classes.md) | Çağrılabilir bir türün belirtilen bağımsız değişken türleri kullanılarak çağrılabileceğini ve sonucun belirtilen türe dönüştürülebilir olup olmadığını sınar.<br/> C++ 17 ' ye eklenmiştir. |
| [is_nothrow_invocable](is-invocable-classes.md) | Çağrılabilir bir türün belirtilen bağımsız değişken türleri kullanılarak çağranıp çağrılameyeceğini ve özel durum throw olarak bilinmediğini sınar.<br/> C++ 17 ' ye eklenmiştir. |
| [is_nothrow_invocable_r](is-invocable-classes.md) | Çağrılabilir bir türün belirtilen bağımsız değişken türleri kullanılarak çağrılabileceğini ve özel durum throw olarak bilinmediğini ve sonucun belirtilen türe dönüştürülebilir olduğunu sınar.<br/> C++ 17 ' ye eklenmiştir. |

Tür özelliği sorguları

|Ad|Açıklama|
|-|-|
|[alignment_of](../standard-library/alignment-of-class.md)|Bir türün hizalamasını alır.|
|[sırası](../standard-library/rank-class.md)|Dizi boyutlarının sayısını alır.|
|[genişliğini](../standard-library/extent-class.md)|Belirtilen dizi boyutundaki öğelerin sayısını alır.|

Tür ilişkileri

|Ad|Açıklama|
|-|-|
|[is_same](../standard-library/is-same-class.md)|İki türün aynı olup olmadığını sınar.|
|[is_base_of](../standard-library/is-base-of-class.md)|Bir türün diğerinin temeli olup olmadığını sınar.|
|[is_convertible](../standard-library/is-convertible-class.md)|Bir türün diğerine dönüştürülebilir olup olmadığını test eder.|

Const geçici değişiklikler

|Ad|Açıklama|
|-|-|
|[add_const](../standard-library/add-const-class.md)|Türden bir **`const`** tür üretir.|
|[add_volatile](../standard-library/add-volatile-class.md)|Türden bir **`volatile`** tür üretir.|
|[add_cv](../standard-library/add-cv-class.md)|Türden bir **`const volatile`** tür üretir.|
|[remove_const](../standard-library/remove-const-class.md)|Türden const olmayan bir tür üretir.|
|[remove_volatile](../standard-library/remove-volatile-class.md)|Türden geçici olmayan bir tür üretir.|
|[remove_cv](../standard-library/remove-cv-class.md)|Türden const olmayan geçici olmayan bir tür üretir.|

Başvuru değişiklikleri

|Ad|Açıklama|
|-|-|
|[add_lvalue_reference](../standard-library/add-lvalue-reference-class.md)|Türünden türe bir başvuru üretir.|
|[add_rvalue_reference](../standard-library/add-rvalue-reference-class.md)|Türünden türe yazmak için bir rvalue başvurusu üretir|
|[remove_reference](../standard-library/remove-reference-class.md)|Türden başvuru olmayan bir tür üretir.|

Değişiklikleri imzala

|Ad|Açıklama|
|-|-|
|[make_signed](../standard-library/make-signed-class.md)|İmzalanmışsa türü ya da türüne eşit veya daha büyük olan en küçük türü üretir.|
|[make_unsigned](../standard-library/make-unsigned-class.md)|İmzasız türü ya da türüne eşit veya daha büyük olan en küçük işaretsiz türü üretir.|

Dizi değişiklikleri

|Ad|Açıklama|
|-|-|
|[remove_all_extents](../standard-library/remove-all-extents-class.md)|Dizi türünden dizi olmayan bir tür üretir.|
|[remove_extent](../standard-library/remove-extent-class.md)|Dizi türünden öğe türü üretir.|

İşaretçi değişiklikleri

|Ad|Açıklama|
|-|-|
|[add_pointer](../standard-library/add-pointer-class.md)|Türünden türe bir işaretçi üretir.|
|[remove_pointer](../standard-library/remove-pointer-class.md)|Türe işaretçiden bir tür üretir.|

Diğer dönüşümler

|Ad|Açıklama|
|-|-|
|[aligned_storage](../standard-library/aligned-storage-class.md)|Hizalanmış bir tür için başlatılmamış belleği ayırır.|
|[aligned_union](../standard-library/aligned-union-class.md)|Önemsiz olmayan bir oluşturucuya veya yıkıcıya sahip hizalanmış bir birleşim için başlatılmamış belleği ayırır.|
|[common_type](../standard-library/common-type-class.md)|Parametre paketinin tüm türlerinin ortak türünü üretir.|
|[Oluştur](../standard-library/conditional-class.md)|Koşul doğru ise, belirtilen ikinci türü, aksi halde ikinci belirtilen türü üretir.|
|[Decay](../standard-library/decay-class.md)|Türü değeri geçti olarak üretir. Başvuru olmayan, const olmayan veya geçici olmayan tür yapar veya tür işaretçisi yapmaz.|
|[enable_if](../standard-library/enable-if-class.md)|Koşul doğru ise, belirtilen türü üretir, aksi takdirde tür yoktur.|
|[invoke_result](invoke-result-class.md)|Belirtilen bağımsız değişken türlerini alan çağrılabilir türün dönüş türünü belirler. <br/>C++ 17 ' ye eklenmiştir. |
|[result_of](../standard-library/result-of-class.md)|Belirtilen bağımsız değişken türlerini alan çağrılabilir türün dönüş türünü belirler. <br/>C++ 14 ' te eklenmiştir ve C++ 17 ' de kullanımdan kaldırılmıştır. |
|[underlying_type](../standard-library/underlying-type-class.md)|Bir numaralandırma türü için temeldeki integral türünü üretir.|

Mantıksal işleç nitelikleri

|Ad|Açıklama|
|-|-|
|[ýn](../standard-library/conjunction-class.md)||
|[veya işlecini uygular](../standard-library/disjunction-class.md)||
|[anlaşma](../standard-library/negation-class.md)||

## <a name="see-also"></a>Ayrıca bkz.

[\<functional>](../standard-library/functional.md)
