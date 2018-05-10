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
ms.openlocfilehash: 5c7d09615b5f9ec7f0f72acde965d5ffbd018c9c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="lttypetraitsgt"></a>&lt;type_traits&gt;

Tür bağımsız değişkenleri özellikleri hakkında bilgi verin veya üretmek derleme zamanı sabitleri türleri dönüştürülmüş sağlamak şablonları tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <type_traits>
```

## <a name="remarks"></a>Açıklamalar

Sınıfları ve şablonlar \<type_traits > tür çıkarımı, Sınıflandırma ve derleme zamanında, türü ile ilgili hataları algılar ve genel kodunuzu en iyi hale getirmenize yardımcı olmak için dönüşümünü desteklemek için kullanılır. Bu sınıfları ve şablonları bir türde bir özellik açıklayan birli tür özellikleri türleri ve bir türün bir özelliği değiştirmek dönüştürme nitelikler arasında bir ilişki tanımlamak ikili tür özellikleri içerir.

Tür özellikleri, bir yardımcı sınıfı desteklemek için `integral_constant`, tanımlanır. Şablon özelleştirmeleri olan `true_type` ve `false_type` tür koşulları için temel sınıflar oluşturur. A *türü koşulu* bir veya daha fazla tür bağımsız değişkenleri alır şablonudur. Türü koşulu zaman *doğru kalıp*, genel olarak, doğrudan veya dolaylı olarak, türetilmiş gelen [true_type](../standard-library/type-traits-typedefs.md#true_type). Türü koşulu zaman *false tutan*, genel olarak, doğrudan veya dolaylı olarak, türetilmiş gelen [false_type](../standard-library/type-traits-typedefs.md#false_type).

A *tür değiştiricisi* veya *dönüştürme ayırdedici nitelik* bir veya daha fazla şablon bağımsız değişken almayan bir şablonu ve bir üye sahip `type`, değiştirilmiş türü eşanlamlısı olduğu.

### <a name="alias-templates"></a>Diğer ad şablonları

Tür özellikleri ifadeleri, basitleştirmek için [diğer şablonları](../cpp/aliases-and-typedefs-cpp.md) için `typename some_trait<T>::type` , burada verilmiştir " `some_trait`" Şablon sınıfı adı. Örneğin, [add_const](../standard-library/add-const-class.md) kendi türü için bir diğer ad şablonun `add_const_t`, tanımlanmış olarak:

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

Yardımcı sınıfı ve tür tanımları

|||
|-|-|
|[integral_constant](../standard-library/integral-constant-class-bool-constant-class.md)|Bir integral, türü ve değeri sabit hale getirir.|
|[true_type](../standard-library/type-traits-typedefs.md#true_type)|Tam sayı sabit true değeri ile tutar.|
|[false_type](../standard-library/type-traits-typedefs.md#false_type)|Tam sayı sabit yanlış değer ile tutar.|

Birincil türü kategorileri

|||
|-|-|
|[is_void](../standard-library/is-void-class.md)|Türü olup olmadığını sınar `void`.|
|[is_null_pointer](../standard-library/is-null-pointer-class.md)|Türü olup olmadığını sınar `std::nullptr_t`.|
|[is_integral](../standard-library/is-integral-class.md)|Türü tam sayı olup olmadığını sınar.|
|[is_floating_point](../standard-library/is-floating-point-class.md)|Kayan nokta türü olup olmadığını sınar.|
|[is_array](../standard-library/is-array-class.md)|Bir dizi türü olup olmadığını sınar.|
|[is_pointer](../standard-library/is-pointer-class.md)|Bir işaretçi türü olup olmadığını sınar.|
|[is_lvalue_reference](../standard-library/is-lvalue-reference-class.md)|Testleri lvalue başvuru türüdür.|
|[is_rvalue_reference](../standard-library/is-rvalue-reference-class.md)|Testleri bir rvalue başvuru türüdür.|
|[is_member_object_pointer](../standard-library/is-member-object-pointer-class.md)|Üye nesnesi için bir işaretçi türü olup olmadığını sınar.|
|[is_member_function_pointer](../standard-library/is-member-function-pointer-class.md)|Üye işlevi için bir işaretçi türü olup olmadığını sınar.|
|[is_enum](../standard-library/is-enum-class.md)|Bir numaralandırma türü olup olmadığını sınar.|
|[is_union](../standard-library/is-union-class.md)|Bir birleşim türü olup olmadığını sınar.|
|[is_class](../standard-library/is-class-class.md)|Bir sınıf türü olup olmadığını sınar.|
|[is_function](../standard-library/is-function-class.md)|Tür bir işlev türü olup olmadığını sınar.|

Bileşik türü kategorileri

|||
|-|-|
|[is_reference](../standard-library/is-reference-class.md)|Bir başvuru türü olup olmadığını sınar.|
|[is_arithmetic](../standard-library/is-arithmetic-class.md)|Türü aritmetik olup olmadığını sınar.|
|[is_fundamental](../standard-library/is-fundamental-class.md)|Türü olup olmadığını sınar `void` veya aritmetik.|
|[is_object](../standard-library/is-object-class.md)|Türü bir nesne türü olup olmadığını sınar.|
|[is_scalar](../standard-library/is-scalar-class.md)|Türü skaler olup olmadığını sınar.|
|[is_compound](../standard-library/is-compound-class.md)|Türü skaler olup olmadığını sınar.|
|[is_member_pointer](../standard-library/is-member-pointer-class.md)|Üye için bir işaretçi türü olup olmadığını sınar.|

Tür özellikleri

|||
|-|-|
|[is_const](../standard-library/is-const-class.md)|Türü olup olmadığını sınar `const`.|
|[is_volatile](../standard-library/is-volatile-class.md)|Türü olup olmadığını sınar `volatile`.|
|[is_trivial](../standard-library/is-trivial-class.md)|Türü Önemsiz olup olmadığını sınar.|
|[is_trivially_copyable](../standard-library/is-trivially-copyable-class.md)|Türü trivially copyable olup olmadığını sınar.|
|[is_standard_layout](../standard-library/is-standard-layout-class.md)|Standart bir yerleşim türündeyse testleri yazın.|
|[is_pod](../standard-library/is-pod-class.md)|Türü bir POD olup olmadığını sınar.|
|[is_literal_type](../standard-library/is-literal-type-class.md)|Türü olabilir desteklemediğini test eden bir `constexpr` değişkeni ya da kullanılan bir `constexpr` işlevi.|
|[is_empty](../standard-library/is-empty-class.md)|Boş bir sınıf türü olup olmadığını sınar.|
|[is_polymorphic](../standard-library/is-polymorphic-class.md)|Tür çok biçimli bir sınıf olup olmadığını sınar.|
|[is_abstract](../standard-library/is-abstract-class.md)|Soyut bir sınıf türü olup olmadığını sınar.|
|[is_final](../standard-library/is-final-class.md)|Türü işaretli bir sınıf türü olup olmadığını sınar `final`.|
|[is_signed](../standard-library/is-signed-class.md)|Türü işaretli bir tam sayı olup olmadığını sınar.|
|[is_unsigned](../standard-library/is-unsigned-class.md)|İşaretsiz tamsayıya türü olup olmadığını sınar.|
|[is_constructible](../standard-library/is-constructible-class.md)|Belirtilen bağımsız değişken türleri kullanılarak oluşturulabilir türü olup olmadığını sınar.|
|[is_default_constructible](../standard-library/type-traits-functions.md#is_default_constructible)|Varsayılan bir oluşturucu türüne sahip olup olmadığını sınar.|
|[is_copy_constructible](../standard-library/type-traits-functions.md#is_copy_constructible)|Kopya Oluşturucu türüne sahip olup olmadığını sınar.|
|[is_move_constructible](../standard-library/type-traits-functions.md#is_move_constructible)|Bir taşıma oluşturucusuna türüne sahip olup olmadığını sınar.|
|[is_assignable](../standard-library/type-traits-functions.md#is_assignable)|İlk tür ikinci türünde bir değer atanabilir olup olmadığını sınar.|
|[is_copy_assignable](../standard-library/type-traits-functions.md#is_copy_assignable)|Bir tür türünde const başvuru değer atanabilir olup olmadığını sınar.|
|[is_move_assignable](../standard-library/type-traits-functions.md#is_move_assignable)|Rvalue başvuru türünde bir tür atanabilir olup olmadığını sınar.|
|[is_destructible](../standard-library/is-destructible-class.md)|Türü destructible olup olmadığını sınar.|
|[is_trivially_constructible](../standard-library/is-trivially-constructible-class.md)|Belirtilen türlerle kullanılarak oluşturulan zaman önemsiz olmayan bir işlem türü kullanıp kullanmadığını sınar.|
|[is_trivially_default_constructible](../standard-library/is-trivially-default-constructible-class.md)|Varsayılan oluşturulan Önemsiz olmayan bir işlem türü kullanır olup olmadığını sınar.|
|[is_trivially_copy_constructible](../standard-library/is-trivially-copy-constructible-class.md)|Kopya oluşturulan Önemsiz olmayan bir işlem türü kullanır olup olmadığını sınar.|
|[is_trivially_move_constructible](../standard-library/type-traits-functions.md#is_trivially_move_constructible)|Taşıma oluşturulan Önemsiz olmayan bir işlem türü kullanır olup olmadığını sınar.|
|[is_trivially_assignable](../standard-library/is-trivially-assignable-class.md)|Türleri atanabilir ve önemsiz olmayan bir işlem atamasını kullanan olup olmadığını sınar.|
|[is_trivially_copy_assignable](../standard-library/type-traits-functions.md#is_trivially_copy_assignable)|Test türü kopya atanabilir ve atama olup Önemsiz olmayan bir işlem kullanır.|
|[is_trivially_move_assignable](../standard-library/type-traits-functions.md#is_trivially_move_assignable)|Testleri Önemsiz olmayan bir işlem türü taşıma atanabilir ve atama olup kullanır.|
|[is_trivially_destructible](../standard-library/is-trivially-destructible-class.md)|Türü destructible yıkıcı Önemsiz olmayan bir işlem kullandığı ve olup olmadığını sınar.|
|[is_nothrow_constructible](../standard-library/is-nothrow-constructible-class.md)|Type oluşturulabilir ve belirtilen türleri kullanılarak oluşturulan zaman throw değil bilinen olup olmadığını sınar.|
|[is_nothrow_default_constructible](../standard-library/is-nothrow-default-constructible-class.md)|Testleri türü olup olmadığını oluşturulabilir varsayılan ve varsayılan oluşturulan zaman throw değil bilinmektedir.|
|[is_nothrow_copy_constructible](../standard-library/is-nothrow-copy-constructible-class.md)|Türü kopya oluşturulabilir ve kopya Oluşturucu değil throw bilinen olup olmadığını sınar.|
|[is_nothrow_move_constructible](../standard-library/is-nothrow-move-constructible-class.md)|Taşıma oluşturulabilir türüdür ve değil atmak için bilinen bir taşıma oluşturucusuna olup olmadığını sınar.|
|[is_nothrow_assignable](../standard-library/is-nothrow-assignable-class.md)|Türü belirtilen türü kullanarak atanabilir olan ve olmayan atmak için bilinen bir atama olup olmadığını sınar.|
|[is_nothrow_copy_assignable](../standard-library/is-nothrow-copy-assignable-class.md)|Kopya atanabilir türüdür ve değil atmak için bilinen bir atama olup olmadığını sınar.|
|[is_nothrow_move_assignable](../standard-library/type-traits-functions.md#is_nothrow_move_assignable)|Taşıma atanabilir türüdür ve değil atmak için bilinen bir atama olup olmadığını sınar.|
|[is_nothrow_destructible](../standard-library/is-nothrow-destructible-class.md)|Türü destructible olan ve olmayan atmak için bilinen bir yıkıcı olup olmadığını sınar.|
|[has_virtual_destructor](http://msdn.microsoft.com/en-us/c0f85f0b-c63c-410d-a046-72eeaf44f7eb)|Bir sanal yıkıcı türüne sahip olup olmadığını sınar.|

Tür özelliği sorguları

|||
|-|-|
|[alignment_of](../standard-library/alignment-of-class.md)|Bir tür hizalamasını alır.|
|[RANK](../standard-library/rank-class.md)|Dizi boyutları sayısını alır.|
|[Kapsam](../standard-library/extent-class.md)|Belirtilen dizinin boyut öğe sayısını alır.|

Tür ilişkileri

|||
|-|-|
|[is_same](../standard-library/is-same-class.md)|İki tür aynı olup olmadığını sınar.|
|[is_base_of](../standard-library/is-base-of-class.md)|Başka bir bir taban bir türü olup olmadığını sınar.|
|[is_convertible](../standard-library/is-convertible-class.md)|Bir türü diğerine dönüştürülebilir olup olmadığını sınar.|

Const geçici değişiklikler

|||
|-|-|
|[add_const](../standard-library/add-const-class.md)|Üreten bir `const` türünden türü.|
|[add_volatile](../standard-library/add-volatile-class.md)|Üreten bir `volatile` türünden türü.|
|[add_cv](../standard-library/add-cv-class.md)|Üreten bir `const volatile` türünden türü.|
|[remove_const](../standard-library/remove-const-class.md)|Const olmayan türü türünden üretir.|
|[remove_volatile](../standard-library/remove-volatile-class.md)|Türünden bir geçici olmayan türü üretir.|
|[remove_cv](../standard-library/remove-cv-class.md)|Const olmayan geçici olmayan türünden türü üretir.|

Başvuru değişiklikler

|||
|-|-|
|[add_lvalue_reference](../standard-library/add-lvalue-reference-class.md)|Türünden yazmanız için bir başvuru üretir.|
|[add_rvalue_reference](../standard-library/add-rvalue-reference-class.md)|Türünden yazmanız için bir rvalue başvuru üretir|
|[remove_reference](../standard-library/remove-reference-class.md)|Türünden bir başvuru olmayan türü üretir.|

Oturum değişiklikler

|||
|-|-|
|[make_signed](../standard-library/make-signed-class.md)|Kaydolduysanız türünden, veya en küçük imzalı değerinden büyük veya eşit boyutta türü üretir.|
|[make_unsigned](../standard-library/make-unsigned-class.md)|İmzasız yoksa türe veya en küçük işaretsiz tür değerinden büyük veya eşit boyutta türü üretir.|

Dizi değişiklikler

|||
|-|-|
|[remove_all_extents](../standard-library/remove-all-extents-class.md)|Bir dizi türü bir dizi olmayan tür üretir.|
|[remove_extent](../standard-library/remove-extent-class.md)|Bir dizi türünden öğe türü üretir.|

İşaretçi değişiklikler

|||
|-|-|
|[add_pointer](../standard-library/add-pointer-class.md)|Türünden yazmanız için bir işaretçi üretir.|
|[remove_pointer](../standard-library/remove-pointer-class.md)|Türü için bir işaretçi bir türden üretir.|

Diğer dönüşümleri

|||
|-|-|
|[aligned_storage](../standard-library/aligned-storage-class.md)|Başlatılmamış bellek için hizalanmış bir türe ayırır.|
|[aligned_union](../standard-library/aligned-union-class.md)|Önemsiz olmayan Oluşturucusu veya yıkıcı hizalanmış bir birleşim için başlatılmamış bellek ayırır.|
|[common_type](../standard-library/common-type-class.md)|Parametre paketinin tüm türleri yaygın türü üretir.|
|[Koşullu](../standard-library/conditional-class.md)|Koşul doğru ise, ilk belirtilen tür, aksi takdirde ikinci belirtilen türü üretir.|
|[decay](../standard-library/decay-class.md)|Değere göre geçti olarak türü üretir. Başvuru olmayan, sabit olmayan veya geçici olmayan türü yapan veya yazmak için bir işaretçi yapar.|
|[enable_if](../standard-library/enable-if-class.md)|Koşul doğru ise, belirtilen tür, aksi takdirde türü yok üretir.|
|[result_of](../standard-library/result-of-class.md)|Belirtilen bağımsız değişken türleri alır aranabilir türü dönüş türünü belirler.|
|[underlying_type](../standard-library/underlying-type-class.md)|Bir numaralandırma türü için temel alınan tam sayı tür üretir.|

## <a name="see-also"></a>Ayrıca bkz.

[\<işlev >](../standard-library/functional.md)<br/>
