---
description: 'Daha fazla bilgi edinin: C++ Temel Yönergeleri denetleyicisi başvurusu'
title: C++ Temel Yönergeleri denetleyicisi başvurusu
ms.date: 03/22/2018
ms.topic: reference
helpviewer_keywords:
- code analysis, C++ core check
ms.assetid: f1429463-136e-41ed-8a75-a8dbf0b4fd89
ms.openlocfilehash: 40d0e713d8064a952c785ca44ac5a7ba60f41b61
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151586"
---
# <a name="c-core-guidelines-checker-reference"></a>C++ Temel Yönergeleri denetleyicisi başvurusu

Bu bölümde C++ Temel Yönergeleri denetleyicisi uyarıları listelenmektedir. Kod Analizi hakkında daha fazla bilgi için bkz. [ `/analyze` (kod analizi)](../build/reference/analyze-code-analysis.md) ve [hızlı başlangıç: C/C++ için kod analizi](../code-quality/quick-start-code-analysis-for-c-cpp.md).

> [!NOTE]
> Bazı uyarılar birden fazla gruba aittir ve tüm uyarıların tamamı bir başvuru konusuna sahip değildir.

## <a name="owner_pointer-group"></a>OWNER_POINTER grubu

[C26402 DONT_HEAP_ALLOCATE_MOVABLE_RESULT](C26402.md)\
Bir taşıma Oluşturucusu varsa, yığın olarak ayrılmış bir nesne yerine kapsamlı bir nesne döndürün. Bkz. [C++ temel yönergeleri R. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr).

[C26403 RESET_OR_DELETE_OWNER](C26403.md)\
\<T>'*Değişken*' sahip işaretçisini sıfırlayın veya açıkça silin. Bkz. [C++ temel yönergeleri R. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr).

[C26404 DONT_DELETE_INVALID](C26404.md)\
Geçersiz durumda olabilecek bir sahibi silmeyin \<T> . Bkz. [C++ temel yönergeleri R. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr).

[C26405 DONT_ASSIGN_TO_VALID](C26405.md)\
Geçerli durumda olabilecek bir sahibe atamayın \<T> . Bkz. [C++ temel yönergeleri R. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr).

[C26406 DONT_ASSIGN_RAW_TO_OWNER](C26406.md)\
Bir sahibe ham işaretçi atamayın \<T> . Bkz. [C++ temel yönergeleri R. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr).

[C26407 DONT_HEAP_ALLOCATE_UNNECESSARILY](C26407.md)\
Kapsamlı nesneleri tercih edin, gereksiz yere ayrılmayın. Bkz. [C++ temel yönergeleri R. 5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-scoped).

[C26429 USE_NOTNULL](C26429.md)\
'*Symbol*' sembolü hiçbir şekilde yok edilebilir için sınanmamıştır, not_null olarak işaretlenebilir. Bkz. [C++ temel yönergeleri F. 23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).

[C26430 TEST_ON_ALL_PATHS](C26430.md)\
'*Symbol*' sembolü tüm yollarda nulllik için sınanmamıştır. Bkz. [C++ temel yönergeleri F. 23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).

[C26431 DONT_TEST_NOTNULL](C26431.md)\
'*Expr*' ifadesinin türü zaten GSL:: not_null. Bu dosyayı nulllik için test etme. Bkz. [C++ temel yönergeleri F. 23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).

## <a name="raw_pointer-group"></a>RAW_POINTER grubu

[C26400 NO_RAW_POINTER_ASSIGNMENT](c26400.md)\
Sahip dönüş değeri olan bir ayırma veya işlev çağrısının sonucunu \<T> Ham işaretçiye atamayın; \<T> bunun yerine Owner kullanın. Bkz. [ı. 11 C++ temel yönergeleri](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Ri-raw).

[C26401 DONT_DELETE_NON_OWNER](c26401.md)\
Sahip olmayan bir ham işaretçiyi silmeyin \<T> . Bkz. [ı. 11 C++ temel yönergeleri](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Ri-raw).

[C26402 DONT_HEAP_ALLOCATE_MOVABLE_RESULT](C26402.md)\
Bir taşıma Oluşturucusu varsa, yığın olarak ayrılmış bir nesne yerine kapsamlı bir nesne döndürün. Bkz. [C++ temel yönergeleri R. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr).

[C26408 NO_MALLOC_FREE](C26408.md)\
Malloc () ve Free () kullanmaktan kaçının, delete ile New 'in nothrow sürümünü tercih edin. Bkz. [C++ temel yönergeleri R. 10](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-mallocfree).

[C26409 NO_NEW_DELETE](C26409.md)\
Yeni ve silmeyi açık bir şekilde çağırarak, bunun yerine std:: make_unique kullanın \<T> . Bkz. [C++ temel yönergeleri R. 11](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-newdelete).

[C26429 USE_NOTNULL](C26429.md)\
'*Symbol*' sembolü hiçbir şekilde yok edilebilir için sınanmamıştır, not_null olarak işaretlenebilir. Bkz. [C++ temel yönergeleri F. 23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).

[C26430 TEST_ON_ALL_PATHS](C26430.md)\
'*Symbol*' sembolü tüm yollarda nulllik için sınanmamıştır. Bkz. [C++ temel yönergeleri F. 23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).

[C26431 DONT_TEST_NOTNULL](C26431.md)\
'*Expr*' ifadesinin türü zaten GSL:: not_null. Bu dosyayı nulllik için test etme. Bkz. [C++ temel yönergeleri F. 23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).

[C26481 NO_POINTER_ARITHMETIC](C26481.md)\
İşaretçi aritmetiği kullanmayın. Bunun yerine span kullanın. Bkz [. C++ temel yönergeleri sınırları. 1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds).

[C26485 NO_ARRAY_TO_POINTER_DECAY](C26485.md)\
'*Expr*' ifadesi: Işaretçiden işaretçiye hiçbir dizi yok. Bkz [. C++ temel yönergeleri sınırları. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds).

## <a name="unique_pointer-group"></a>UNIQUE_POINTER grubu

[C26410 NO_REF_TO_CONST_UNIQUE_PTR](C26410.md)\
'*Parameter*' parametresi, benzersiz bir işaretçiye başvurudur `const` , bunun yerine const t * veya const t& kullanın. Bkz. [C++ temel yönergeleri R. 32](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-uniqueptrparam).

[C26411 NO_REF_TO_UNIQUE_PTR](C26411.md)\
'*Parameter*' parametresi benzersiz bir işaretçiye başvurudur ve bu parametre hiçbir şekilde yeniden atanmaz veya sıfırlanmaz, bunun yerine t * veya t& kullanın. Bkz. [C++ temel yönergeleri R. 33](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-reseat).

[C26414 RESET_LOCAL_SMART_PTR](C26414.md)\
Yerel bir akıllı işaretçi '*sembolünü*' taşıyın, kopyalayın, yeniden atayın veya sıfırlayın. Bkz. [C++ temel yönergeleri R. 5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-scoped).

[C26415 SMART_PTR_NOT_NEEDED](C26415.md)\
'*Symbol*' akıllı işaretçi parametresi yalnızca içerilen işaretçiye erişmek için kullanılır. Bunun yerine T * veya T& kullanın. Bkz. [C++ temel yönergeleri R. 30](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-smartptrparam).

## <a name="shared_pointer-group"></a>SHARED_POINTER grubu

[C26414 RESET_LOCAL_SMART_PTR](C26414.md)\
Yerel bir akıllı işaretçi '*sembolünü*' taşıyın, kopyalayın, yeniden atayın veya sıfırlayın. Bkz. [C++ temel yönergeleri R. 5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-scoped).

[C26415 SMART_PTR_NOT_NEEDED](C26415.md)\
'*Symbol*' akıllı işaretçi parametresi yalnızca içerilen işaretçiye erişmek için kullanılır. Bunun yerine T * veya T& kullanın. Bkz. [C++ temel yönergeleri R. 30](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-smartptrparam).

[C26416 NO_RVALUE_REF_SHARED_PTR](C26416.md)\
'*Symbol*' paylaşılan işaretçi parametresi rvalue başvurusuyla geçirildi. Bunun yerine değere göre geçirin. Bkz. [C++ temel yönergeleri R. 34](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-sharedptrparam-owner).

[C26417 NO_LVALUE_REF_SHARED_PTR](C26417.md)\
'*Symbol*' paylaşılan işaretçi parametresi, başvuruya göre geçirilir ve sıfırlanmaz veya yeniden atanmaz. Bunun yerine T * veya T& kullanın. Bkz. [C++ temel yönergeleri R. 35](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-sharedptrparam).

[C26418 NO_VALUE_OR_CONST_REF_SHARED_PTR](C26418.md)\
'*Symbol*' paylaşılan işaretçi parametresi kopyalanmadı veya taşınmadı. Bunun yerine T * veya T& kullanın. Bkz. [C++ temel yönergeleri R. 36](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-sharedptrparam-const).

## <a name="declaration-group"></a>BILDIRIM grubu

[C26426 NO_GLOBAL_INIT_CALLS](C26426.md)\
Genel Başlatıcı, constexpr olmayan '*symbol*' işlevini çağırır. Bkz. [C++ temel yönergeleri I. 22](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#i22-avoid-complex-initialization-of-global-objects).

[C26427 NO_GLOBAL_INIT_EXTERNS](C26427.md)\
Genel Başlatıcı, '*symbol*' extern nesnesine erişir. Bkz. [C++ temel yönergeleri I. 22](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#i22-avoid-complex-initialization-of-global-objects).

[C26444 NO_UNNAMED_RAII_OBJECTS](c26444.md)\
Özel oluşturma ve yok etme özellikli adsız nesnelerden kaçının. Bkz [. es. 84: yerel bir değişkeni adı olmadan bildirme (deneyin)](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md).

## <a name="class-group"></a>SıNıF grubu

[C26432 DEFINE_OR_DELETE_SPECIAL_OPS](C26432.md)\
'*Symbol*' türünde herhangi bir varsayılan işlem tanımlar veya silerseniz, tümünü tanımlayın veya silin. Bkz. [C++ temel yönergeleri C. 21](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c21-if-you-define-or-delete-any-default-operation-define-or-delete-them-all).

[C26433 OVERRIDE_EXPLICITLY](c26433.md)\
'*Symbol*' işlevi ' override ' ile işaretlenmelidir. Bkz. [C. 128: sanal işlevler tam olarak bir sanal, geçersiz kılma veya son belirtilmelidir](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c128-virtual-functions-should-specify-exactly-one-of-virtual-override-or-final).

[C26434 DONT_HIDE_METHODS](C26434.md)\
'*Symbol_1*' işlevi sanal olmayan '*symbol_2*' işlevini gizliyor. Bkz. [C++ temel yönergeleri C. 128](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c128-virtual-functions-should-specify-exactly-one-of-virtual-override-or-final).

[C26435 SINGLE_VIRTUAL_SPECIFICATION](c26435.md)\
'*Symbol*' işlevi, tam olarak bir ' Virtual ', ' override ' veya ' final ' belirtmelidir. Bkz. [C. 128: sanal işlevler tam olarak bir sanal, geçersiz kılma veya son belirtilmelidir](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md).

[C26436 NEED_VIRTUAL_DTOR](C26436.md)\
Sanal işlevi olan '*symbol*' türü, ortak sanal veya korumalı sanal olmayan yok edici olmalıdır. Bkz. [C++ temel yönergeleri C. 35](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c35-a-base-class-destructor-should-be-either-public-and-virtual-or-protected-and-nonvirtual).

[C26443 NO_EXPLICIT_DTOR_OVERRIDE](c26443.md)\
Geçersiz kılma yıkıcısı açık ' override ' veya ' Virtual ' belirticileri kullanmamalıdır. Bkz. [C. 128: sanal işlevler tam olarak bir sanal, geçersiz kılma veya son belirtilmelidir](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md).

## <a name="style-group"></a>STIL grubu

[C26438 NO_GOTO](C26438.md)\
Önleyin `goto` . Bkz [. C++ temel YÖNERGELERI es. 76](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es76-avoid-goto).

## <a name="function-group"></a>Işlev grubu

[C26439 SPECIAL_NOEXCEPT](C26439.md)\
Bu tür bir işlev, fırlamayabilir. Bildirin **`noexcept`** . Bkz. [C++ temel yönergeleri F. 6](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f6-if-your-function-may-not-throw-declare-it-noexcept).

[C26440 DECLARE_NOEXCEPT](C26440.md)\
'*Symbol*' işlevi bildirilebilecek **`noexcept`** . Bkz. [C++ temel yönergeleri F. 6](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f6-if-your-function-may-not-throw-declare-it-noexcept).

[C26447 DONT_THROW_IN_NOEXCEPT](c26447.md)\
İşlev bildirilmiştir **`noexcept`** ancak özel durum oluşturabilecek bir işlev çağırır.
Bkz. [C++ temel yönergeleri: F. 6: işleviniz oluşturmayabilir, noexcept olarak bildirin](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f6-if-your-function-may-not-throw-declare-it-noexcept).

## <a name="concurrency-group"></a>EŞZAMANLıLıK grubu

[C26441 NO_UNNAMED_GUARDS](C26441.md)\
Guard nesnelerinin adlandırılması gerekir. Bkz. [C++ temel yönergeleri CP. 44](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#cp44-remember-to-name-your-lock_guards-and-unique_locks).

## <a name="const-group"></a>CONST grubu

[C26460 USE_CONST_REFERENCE_ARGUMENTS](c26460.md)\
'*Function*' işlevi için '*Argument*' başvuru bağımsız değişkeni olarak işaretlenebilir `const` . Bkz. [C++ temel yönergeleri Con. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rconst-ref).

[C26461 USE_CONST_POINTER_ARGUMENTS](c26461.md): \
'*Function*' işlevinin '*Argument*' işaretçi bağımsız değişkeni, için bir işaretçi olarak işaretlenebilir `const` . Bkz. [C++ temel yönergeleri Con. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rconst-ref).

[C26462 USE_CONST_POINTER_FOR_VARIABLE](c26462.md)\
'*Variable*' tarafından işaret edilen değer yalnızca bir kez atanır, bir işaretçi olarak işaretleyin `const` . Bkz. [C++ temel yönergeleri Con. 4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction).

[C26463 USE_CONST_FOR_ELEMENTS](c26463.md)\
'*Array*' dizisinin öğeleri yalnızca bir kez atanır, öğeleri işaretleyin `const` . Bkz. [C++ temel yönergeleri Con. 4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction).

[C26464 USE_CONST_POINTER_FOR_ELEMENTS](c26464.md)\
'*Array*' dizisinin öğeleri tarafından işaret edilen değerler yalnızca bir kez atanır, öğeleri işaretçisi olarak işaretleyin `const` . Bkz. [C++ temel yönergeleri Con. 4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction).

[C26496 USE_CONST_FOR_VARIABLE](c26496.md)\
'*Variable*' değişkeni yalnızca bir kez atanır, olarak işaretleyin `const` . Bkz. [C++ temel yönergeleri Con. 4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction).

[C26497 USE_CONSTEXPR_FOR_FUNCTION](c26497.md)\
Bu işlev *işlevi* , `constexpr` derleme zamanı değerlendirmesi isteniyorsa işaretlenebilir. Bkz. [C++ temel yönergeleri F. 4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rf-constexpr).

[C26498 USE_CONSTEXPR_FOR_FUNCTIONCALL](c26498.md)\
Bu işlev çağrısı *işlevi* , `constexpr` derleme zamanı değerlendirmesi isteniyorsa kullanılabilir. Bkz. [C++ temel yönergeleri Con. 5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rconst-constexpr).

## <a name="type-group"></a>TÜR grubu

[C26437 DONT_SLICE](C26437.md)\
Dilimlemeyin. Bkz [. C++ temel YÖNERGELERI es. 63](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es63-dont-slice).

[C26465 NO_CONST_CAST_UNNECESSARY](c26465.md)\
`const_cast`Dönüştürmek için kullanmayın `const` . `const_cast` gerekli değildir; sabitlik veya Vola, bu dönüşüm tarafından kaldırılmıyor. Bkz [. C++ temel yönergeleri türü. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-constcast).

[C26466 NO_STATIC_DOWNCAST_POLYMORPHIC](c26466.md)\
Küçük işlemleri kullanmayın `static_cast` . Polimorfik bir türden dönüştürme dynamic_cast kullanmalıdır. [C++ temel yönergeleri türü. 2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-downcast)' ye bakın.

[C26471 NO_REINTERPRET_CAST_FROM_VOID_PTR](c26471.md)\
Kullanmayın `reinterpret_cast` . Void * öğesinden bir atama kullanabilir `static_cast` . Bkz [. C++ temel yönergeleri türü. 1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast).

[C26472 NO_CASTS_FOR_ARITHMETIC_CONVERSION](C26472.md)\
`static_cast`Aritmetik dönüştürmeler için kullanmayın. Ayraç başlatma, GSL:: narrow_cast veya GSL:: dar kullanın. Bkz [. C++ temel yönergeleri türü. 1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast).

[C26473 NO_IDENTITY_CAST](C26473.md)\
Kaynak türü ve hedef türünün aynı olduğu işaretçi türleri arasında dönüştürme yapmayın. Bkz [. C++ temel yönergeleri türü. 1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast).

[C26474 NO_IMPLICIT_CAST](C26474.md)\
Dönüştürme örtük olabilecek işaretçi türleri arasında dönüştürme yapmayın. Bkz [. C++ temel yönergeleri türü. 1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast).

[C26475 NO_FUNCTION_STYLE_CASTS](C26475.md)\
İşlev stili C-yayınları kullanmayın. Bkz [. C++ temel YÖNERGELERI es. 49](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es49-if-you-must-use-a-cast-use-a-named-cast).

[C26490 NO_REINTERPRET_CAST](c26490.md)\
Kullanmayın `reinterpret_cast` . Bkz [. C++ temel yönergeleri türü. 1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).

[C26491 NO_STATIC_DOWNCAST](c26490.md)\
Küçük işlemleri kullanmayın `static_cast` . [C++ temel yönergeleri türü. 2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type)' ye bakın.

[C26492 NO_CONST_CAST](c26492.md)\
`const_cast`Dönüştürmek için kullanmayın `const` . Bkz [. C++ temel yönergeleri türü. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).

[C26493 NO_CSTYLE_CAST](c26493.md)\
C stili atamalar kullanmayın. Bkz [. C++ temel yönergeleri türü. 4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).

[C26494 VAR_USE_BEFORE_INIT](c26494.md)\
'*Variable*' değişkeni başlatılmamış. Her zaman bir nesne başlatın. Bkz [. C++ temel yönergeleri Type. 5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).

[C26495 MEMBER_UNINIT](c26495.md)\
'*Variable*' değişkeni başlatılmamış. Bir üye değişkenini her zaman başlatın. Bkz [. C++ temel yönergeleri Type. 6](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).

## <a name="bounds-group"></a>SıNıR grubu

[C26446 USE_GSL_AT](c26446.md)\
`gsl::at()`İşaretlenmemiş indis işleci yerine kullanmayı tercih edin. Bkz [. C++ temel yönergeleri: sınır. 4: standart kitaplık işlevleri ve sınır işaretli olmayan türler kullanmayın](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#probounds-bounds-safety-profile).

[C26481 NO_POINTER_ARITHMETIC](C26481.md)\
İşaretçi aritmetiği kullanmayın. Bunun yerine span kullanın. [C++ temel yönergeleri sınırlara bakın. 1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)

[C26482 NO_DYNAMIC_ARRAY_INDEXING](c26482.md)\
Yalnızca sabit ifadeler kullanılarak dizilere dizinler. Bkz [. C++ temel yönergeleri sınırları. 2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)

[C26483 STATIC_INDEX_OUT_OF_RANGE](c26483.md)\
Değer *değeri* , '*Variable*' değişkeninin sınırları (0, *sınır*) dışında. Yalnızca dizi sınırları içindeki sabit ifadeleri kullanarak dizilere dizin ekleyin. Bkz [. C++ temel yönergeleri sınırları. 2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)

[C26485 NO_ARRAY_TO_POINTER_DECAY](C26485.md)\
'*Expr*' ifadesi: Işaretçiden işaretçiye hiçbir dizi yok. [C++ temel yönergeleri sınırlara bakın. 3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)

## <a name="gsl-group"></a>GSL grubu

[C26445 NO_SPAN_REF](c26445.md)\
`gsl::span`Ya da bir `std::string_view` geçerlilik süresi sorunu göstergesi olabilir.
Bkz [. C++ temel yönergeleri GSL. View: views](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#gslview-views)

[C26446 USE_GSL_AT](c26446.md)\
`gsl::at()`İşaretlenmemiş indis işleci yerine kullanmayı tercih edin. Bkz [. C++ temel yönergeleri: sınır. 4: standart kitaplık işlevleri ve sınır işaretli olmayan türler kullanmayın](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#probounds-bounds-safety-profile).

[C26448 USE_GSL_FINALLY](c26448.md)\
`gsl::finally`Son eylem amaçlanıyorsa kullanmayı düşünün. Bkz. [C++ temel yönergeleri: GSL. util: Utilities](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-utilities).

[C26449 NO_SPAN_FROM_TEMPORARY](c26449.md)\
`gsl::span` Aksi `std::string_view` , geçici bir değer geçersiz kılınmadıysa geçersiz olur. Bkz. [C++ temel yönergeleri: GSL. View: views](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#gslview-views).

## <a name="deprecated-warnings"></a>Kullanım dışı uyarıları

Aşağıdaki uyarılar, temel kılavuz denetleyicinin erken deneysel kural kümesinde bulunur, ancak artık kullanımdan kaldırılmıştır ve güvenle yoksayılabilir. Yukarıdaki listede yer alan uyarılar, uyarıların yerini alır.

- 26412 DEREF_INVALID_POINTER
- 26413 DEREF_NULLPTR
- 26420 ASSIGN_NONOWNER_TO_EXPLICIT_OWNER
- 26421 ASSIGN_VALID_OWNER
- 26422 VALID_OWNER_LEAVING_SCOPE
- 26423 ALLOCATION_NOT_ASSIGNED_TO_OWNER
- 26424 VALID_ALLOCATION_LEAVING_SCOPE
- 26425 ASSIGNING_TO_STATIC
- 26499 NO_LIFETIME_TRACKING

## <a name="see-also"></a>Ayrıca bkz.

[C++ Temel Yönergeleri denetleyicilerini kullanma](using-the-cpp-core-guidelines-checkers.md)
