---
title: '&lt;type_traits&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <type_traits>
dev_langs:
- C++
helpviewer_keywords:
- typetrait header
- type_traits
ms.assetid: 2260b51f-8160-4c66-a82f-00b534cb60d4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fed2cad9c96b20313617ef57e4373de16712aa34
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43218858"
---
# <a name="lttypetraitsgt"></a>&lt;type_traits&gt;

Tür bağımsız değişkenlerinin özellikleri hakkında bilgi verin ya da üretmek derleme zamanı sabitleri türleri dönüştürülür sağlayan şablonları tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <type_traits>
```

## <a name="remarks"></a>Açıklamalar

Sınıfları ve şablonlarında \<type_traits > tür çıkarımı, Sınıflandırma ve derleme zamanında, genel kodunuzu iyileştirmenize yardımcı olmak ve türü ile ilgili hataları algılamak için dönüştürme desteklemek için kullanılır. Bu sınıflar ve şablonları, bir türden bir özelliği açıklamaktadır birli türü nitelikler türleri ve bir türün bir özelliği değiştirmek dönüştürme nitelikler arasında bir ilişki tanımlamak ikili tür özellikleri içerir.

Tür özellikleri, bir yardımcı sınıfı desteklemek için `integral_constant`, tanımlanır. Şablon uzmanlıkları sahip `true_type` ve `false_type` tür koşulları için temel sınıflar oluşturur. A *tür koşulu* bir veya daha fazla tür bağımsız değişkenlerini alan bir şablondur. Bir tür koşulu, *korumadıkça*, genel olarak, doğrudan veya dolaylı olarak türetilmiş gelen [true_type](../standard-library/type-traits-typedefs.md#true_type). Bir tür koşulu, *yanlışlığını korumadıkça*, genel olarak, doğrudan veya dolaylı olarak türetilmiş gelen [false_type](../standard-library/type-traits-typedefs.md#false_type).

A *tür değiştiricisi* veya *nitelik dönüştürme* şablondan bir veya daha fazla şablon bağımsız değişkeni alır ve bir üye `type`, değiştirilen türü için bir eşanlamlı olduğu.

### <a name="alias-templates"></a>Diğer ad şablonları

Türü nitelikler ifadeleri basitleştirmek için [diğer ad şablonları](../cpp/aliases-and-typedefs-cpp.md) için `typename some_trait<T>::type` , burada sağlanan " `some_trait`" Şablon sınıfı adı. Örneğin, [add_const](../standard-library/add-const-class.md) kendi türü için bir diğer ad şablonda `add_const_t`, olarak tanımlanır:

```cpp
template <class T>
using add_const_t = typename add_const<T>::type;
```

|||||
|-|-|-|-|
|add_const_t|aligned_storage_t|make_signed_t|remove_pointer_t|
|add_cv_t|aligned_union_t|make_unsigned_t|remove_reference_t|
|add_lvalue_reference_t|common_type_t|remove_all_extents_t|remove_volatile_t|
|add_pointer_t|conditional_t|remove_const_t|result_of_t|
|add_rvalue_reference_t|decay_t|remove_cv_t|underlying_type_t|
|add_volatile_t|enable_if_t|remove_extent_t||

### <a name="classes"></a>Sınıflar

Yardımcısı sınıfı ve tür tanımları

|||
|-|-|
|[integral_constant](../standard-library/integral-constant-class-bool-constant-class.md)|Bir integral türü ve değeri sabit yapar.|
|[true_type](../standard-library/type-traits-typedefs.md#true_type)|True değerine sahip tam sayı sabiti tutar.|
|[false_type](../standard-library/type-traits-typedefs.md#false_type)|False değeri ile tamsayı sabiti tutar.|

Birincil tür kategorileri

|||
|-|-|
|[is_void](../standard-library/is-void-class.md)|Türü olup olmadığını sınar **void**.|
|[is_null_pointer](../standard-library/is-null-pointer-class.md)|Türü olup olmadığını sınar `std::nullptr_t`.|
|[is_integral](../standard-library/is-integral-class.md)|İntegral türü olup olmadığını sınar.|
|[is_floating_point](../standard-library/is-floating-point-class.md)|Kayan nokta türü olup olmadığını sınar.|
|[is_array](../standard-library/is-array-class.md)|Bir dizi türü olup olmadığını sınar.|
|[is_pointer](../standard-library/is-pointer-class.md)|Bir işaretçi türü olup olmadığını sınar.|
|[is_lvalue_reference](../standard-library/is-lvalue-reference-class.md)|Lvalue başvuru türü olup olmadığını sınar.|
|[is_rvalue_reference](../standard-library/is-rvalue-reference-class.md)|Rvalue başvuru türü olup olmadığını sınar.|
|[is_member_object_pointer](../standard-library/is-member-object-pointer-class.md)|Üye nesnesine bir işaretçi türü olup olmadığını sınar.|
|[is_member_function_pointer](../standard-library/is-member-function-pointer-class.md)|Bir üye işlev işaretçisi türü olup olmadığını sınar.|
|[is_enum](../standard-library/is-enum-class.md)|Bir numaralandırma türü olup olmadığını sınar.|
|[is_union](../standard-library/is-union-class.md)|Bir birleşim türü olup olmadığını sınar.|
|[is_class](../standard-library/is-class-class.md)|Bir sınıf türü olup olmadığını sınar.|
|[is_function](../standard-library/is-function-class.md)|Türü bir işlev türü olup olmadığını sınar.|

Bileşik tür kategorileri

|||
|-|-|
|[is_reference](../standard-library/is-reference-class.md)|Bir başvuru türü olup olmadığını sınar.|
|[is_arithmetic](../standard-library/is-arithmetic-class.md)|Aritmetik türü olup olmadığını sınar.|
|[is_fundamental](../standard-library/is-fundamental-class.md)|Türü olup olmadığını sınar **void** veya aritmetik.|
|[is_object](../standard-library/is-object-class.md)|Türü bir nesne türü olup olmadığını sınar.|
|[is_scalar](../standard-library/is-scalar-class.md)|Skalar türü olup olmadığını sınar.|
|[is_compound](../standard-library/is-compound-class.md)|Türü skaler olup olmadığını test eder.|
|[is_member_pointer](../standard-library/is-member-pointer-class.md)|Bir üye işaretçisi türü olup olmadığını sınar.|

Tür özellikleri

|||
|-|-|
|[is_const](../standard-library/is-const-class.md)|Türü olup olmadığını sınar **const**.|
|[is_volatile](../standard-library/is-volatile-class.md)|Türü olup olmadığını sınar **geçici**.|
|[is_trivial](../standard-library/is-trivial-class.md)|Türü, Önemsiz olup olmadığını sınar.|
|[is_trivially_copyable](../standard-library/is-trivially-copyable-class.md)|Türü artık önemsiz olarak kopyalanabilir olup olmadığını sınar.|
|[is_standard_layout](../standard-library/is-standard-layout-class.md)|Standart düzen türünü türü olup olmadığını sınar.|
|[is_pod](../standard-library/is-pod-class.md)|Bir POD türü olup olmadığını sınar.|
|[is_literal_type](../standard-library/is-literal-type-class.md)|Türü olup olmadığını test bir `constexpr` değişken veya kullanılan bir `constexpr` işlevi.|
|[is_empty](../standard-library/is-empty-class.md)|Boş bir sınıf türü olup olmadığını sınar.|
|[is_polymorphic](../standard-library/is-polymorphic-class.md)|Çok biçimli bir sınıf türü olup olmadığını sınar.|
|[is_abstract](../standard-library/is-abstract-class.md)|Soyut bir sınıf türü olup olmadığını sınar.|
|[is_final](../standard-library/is-final-class.md)|Türü olarak işaretlenmiş bir sınıf türü olup olmadığını sınar `final`.|
|[is_signed](../standard-library/is-signed-class.md)|İmzalı bir tamsayı türü olup olmadığını sınar.|
|[is_unsigned](../standard-library/is-unsigned-class.md)|İşaretsiz bir tamsayı türü olup olmadığını sınar.|
|[is_constructible](../standard-library/is-constructible-class.md)|Belirtilen bağımsız değişken türleri kullanarak atmamalıdır türü olup olmadığını sınar.|
|[is_default_constructible](../standard-library/type-traits-functions.md#is_default_constructible)|Varsayılan bir oluşturucu türüne sahip olup olmadığını sınar.|
|[is_copy_constructible](../standard-library/type-traits-functions.md#is_copy_constructible)|Kopya Oluşturucu türüne sahip olup olmadığını sınar.|
|[is_move_constructible](../standard-library/type-traits-functions.md#is_move_constructible)|Türü bir taşıma oluşturucusuna sahip olup olmadığını test eder.|
|[is_assignable](../standard-library/type-traits-functions.md#is_assignable)|İlk tür ikinci türünde bir değer atanabilir olup olmadığını sınar.|
|[is_copy_assignable](../standard-library/type-traits-functions.md#is_copy_assignable)|Bir türü türün const bir başvuru değeri atanabilir olup olmadığını sınar.|
|[is_move_assignable](../standard-library/type-traits-functions.md#is_move_assignable)|Bir türü bir rvalue başvuru türü atanabilir olup olmadığını sınar.|
|[is_destructible](../standard-library/is-destructible-class.md)|Yıkıcı türü olup olmadığını sınar.|
|[is_trivially_constructible](../standard-library/is-trivially-constructible-class.md)|Belirtilen türlerini kullanarak bir yapıda, Önemsiz olmayan bir işlem türünü kullanan olup olmadığını sınar.|
|[is_trivially_default_constructible](../standard-library/is-trivially-default-constructible-class.md)|Varsayılan oluşturulan Önemsiz olmayan bir işlem türü kullanır olup olmadığını sınar.|
|[is_trivially_copy_constructible](../standard-library/is-trivially-copy-constructible-class.md)|Kopyalama oluşturulmuş Önemsiz olmayan bir işlem türü kullanır olup olmadığını sınar.|
|[is_trivially_move_constructible](../standard-library/type-traits-functions.md#is_trivially_move_constructible)|Türü taşıma oluşturulmuş Önemsiz olmayan bir işlem kullanır olup olmadığını sınar.|
|[is_trivially_assignable](../standard-library/is-trivially-assignable-class.md)|Atanabilir türleri ve önemsiz olmayan bir işlem ataması kullanan olup olmadığını sınar.|
|[is_trivially_copy_assignable](../standard-library/type-traits-functions.md#is_trivially_copy_assignable)|Test türü atanabilir kopyalama ve atama olup Önemsiz olmayan bir işlem kullanır.|
|[is_trivially_move_assignable](../standard-library/type-traits-functions.md#is_trivially_move_assignable)|Testler, Önemsiz olmayan bir işlem türü taşıma atanabilir ve atama olup kullanır.|
|[is_trivially_destructible](../standard-library/is-trivially-destructible-class.md)|Yıkıcı bir türdür ve önemsiz olmayan bir işlem yok Edicisi kullanan olup olmadığını sınar.|
|[is_nothrow_constructible](../standard-library/is-nothrow-constructible-class.md)|Type atmamalıdır ve belirtilen türü kullanarak oluşturulan zaman oluşturması beklenmiyor bilinen olup olmadığını sınar.|
|[is_nothrow_default_constructible](../standard-library/is-nothrow-default-constructible-class.md)|Test türü olup olmadığını atmamalıdır varsayılan ve varsayılan oluşturulmuş olduğunda oluşturması beklenmiyor bilinmektedir.|
|[is_nothrow_copy_constructible](../standard-library/is-nothrow-copy-constructible-class.md)|Kopyalama atmamalıdır türüdür ve değil atmak için bilinen bir kopya Oluşturucu olup olmadığını sınar.|
|[is_nothrow_move_constructible](../standard-library/is-nothrow-move-constructible-class.md)|Türü taşıma atmamalıdır ve taşıma oluşturucusu olmayan throw bilinen olup olmadığını sınar.|
|[is_nothrow_assignable](../standard-library/is-nothrow-assignable-class.md)|Belirtilen türü kullanarak atanabilir bir türdür ve atama değil throw bilinen olup olmadığını sınar.|
|[is_nothrow_copy_assignable](../standard-library/is-nothrow-copy-assignable-class.md)|Türü kopya atanabilir ve atama değil throw bilinen olup olmadığını sınar.|
|[is_nothrow_move_assignable](../standard-library/type-traits-functions.md#is_nothrow_move_assignable)|Türü taşıma atanabilir ve atama değil throw bilinen olup olmadığını sınar.|
|[is_nothrow_destructible](../standard-library/is-nothrow-destructible-class.md)|Yıkıcı bir türdür ve yok edici değil throw bilinen olup olmadığını sınar.|
|[has_virtual_destructor](https://msdn.microsoft.com/c0f85f0b-c63c-410d-a046-72eeaf44f7eb)|Sanal bir yıkıcı türüne sahip olup olmadığını sınar.|

Tür özelliği sorguları

|||
|-|-|
|[alignment_of](../standard-library/alignment-of-class.md)|Bir tür hizalamasını alır.|
|[boyut sayısı](../standard-library/rank-class.md)|Dizi boyut sayısını alır.|
|[Kapsam](../standard-library/extent-class.md)|Belirtilen dizinin boyutun öğe sayısını alır.|

Tür ilişkileri

|||
|-|-|
|[is_same](../standard-library/is-same-class.md)|İki tür aynı olup olmadığını test eder.|
|[is_base_of](../standard-library/is-base-of-class.md)|Başka bir taban bir türü olup olmadığını sınar.|
|[is_convertible](../standard-library/is-convertible-class.md)|Bir türden diğerine dönüştürülebilir olup olmadığını sınar.|

Const-volatile değişiklikler

|||
|-|-|
|[add_const](../standard-library/add-const-class.md)|Üreten bir **const** türünden türü.|
|[add_volatile](../standard-library/add-volatile-class.md)|Üreten bir **geçici** türünden türü.|
|[add_cv](../standard-library/add-cv-class.md)|Üreten bir **const volatile** türünden türü.|
|[remove_const](../standard-library/remove-const-class.md)|Türünden bir sabit olmayan türe üretir.|
|[remove_volatile](../standard-library/remove-volatile-class.md)|Türünden bir geçici olmayan tür üretir.|
|[remove_cv](../standard-library/remove-cv-class.md)|Türden sabit olmayan bir geçici olmayan türe üretir.|

Başvuru değişiklikler

|||
|-|-|
|[add_lvalue_reference](../standard-library/add-lvalue-reference-class.md)|Türünden bir başvuru oluşturur.|
|[add_rvalue_reference](../standard-library/add-rvalue-reference-class.md)|Türünden bir rvalue başvuru oluşturur|
|[remove_reference](../standard-library/remove-reference-class.md)|Türünden bir başvuru olmayan türü üretir.|

Oturum değişiklikler

|||
|-|-|
|[make_signed](../standard-library/make-signed-class.md)|Oturum türü veya en küçük işaretli bir türe büyük veya buna eşit boyutta türüne üretir.|
|[make_unsigned](../standard-library/make-unsigned-class.md)|İşaretsiz türünde veya küçük işaretsiz türe büyük veya buna eşit boyutta türüne üretir.|

Dizi değişiklikler

|||
|-|-|
|[remove_all_extents](../standard-library/remove-all-extents-class.md)|Bir dizi türü bir dizi olmayan tür üretir.|
|[remove_extent](../standard-library/remove-extent-class.md)|Bir dizi türünden öğe türü oluşturur.|

İşaretçi değişiklikler

|||
|-|-|
|[add_pointer](../standard-library/add-pointer-class.md)|Bir işaretçi türünden üretir.|
|[remove_pointer](../standard-library/remove-pointer-class.md)|Bir türü arasında bir işaretçi üretir.|

Diğer dönüşümleri

|||
|-|-|
|[aligned_storage](../standard-library/aligned-storage-class.md)|Hizalanmış bir tür için başlatılmamış bellek ayırır.|
|[aligned_union](../standard-library/aligned-union-class.md)|Önemsiz olmayan bir oluşturucu veya yıkıcı hizalanmış bir birleşim için başlatılmamış bellek ayırır.|
|[common_type](../standard-library/common-type-class.md)|Parametre paketi tüm türleri ortak türü üretir.|
|[Koşullu](../standard-library/conditional-class.md)|Koşul true ise ilk belirtilen tür, aksi takdirde ikinci belirtilen türü üretir.|
|[decay](../standard-library/decay-class.md)|Türü, değer olarak geçilemez olarak oluşturur. Başvuru olmayan, sabit olmayan veya geçici olmayan tür veya tür işaretçisi yapar.|
|[enable_if](../standard-library/enable-if-class.md)|Koşul true ise, belirtilen tür, aksi takdirde hiçbir tür üretir.|
|[result_of](../standard-library/result-of-class.md)|Belirtilen bağımsız değişken türleri alan çağrılabilir türü dönüş türünü belirler.|
|[underlying_type](../standard-library/underlying-type-class.md)|Bir numaralandırma türünün temel alınan integral türü üretir.|

## <a name="see-also"></a>Ayrıca bkz.

[\<işlev >](../standard-library/functional.md)<br/>
