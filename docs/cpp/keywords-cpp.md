---
title: Anahtar Sözcükler (C++)
description: C++ standart dil anahtar sözcüklerini, Microsoft 'a özgü anahtar kelimeleri ve içeriğe özgü anahtar sözcükleri listeler.
ms.custom: index-page
ms.date: 07/25/2020
helpviewer_keywords:
- keywords [C++]
ms.assetid: d7ca94a8-f785-41ce-9f73-d3c4fd508489
ms.openlocfilehash: 1144558a6a4847e158579bf453e3bf3b45c0a199
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102465521"
---
# <a name="keywords-c"></a>Anahtar Sözcükler (C++)

Anahtar sözcükler özel anlamlara sahip önceden tanımlanmış ayrılmış tanımlayıcılardır. Bunlar, programınızda tanımlayıcı olarak kullanılamaz. Aşağıdaki anahtar sözcükler Microsoft C++ için ayrılmıştır. Önde gelen alt çizgiler ve C++/CX ve C++/CLı için belirtilen adlara sahip adlar Microsoft uzantılarıdır.

## <a name="standard-c-keywords"></a>Standart C++ anahtar sözcükleri

:::row:::
    :::column:::
        [`alignas`](align-cpp.md)\
        [`alignof`](alignof-operator.md)\
        [`and`](bitwise-and-operator-amp.md)<sup>b</sup>\
        [`and_eq`](assignment-operators.md)<sup>b</sup>\
        [`asm`](../assembler/inline/asm.md)<sup>bir</sup>\
        [`auto`](./auto-cpp.md)\
        [`bitand`](bitwise-and-operator-amp.md)<sup>b</sup>\
        [`bitor`](bitwise-inclusive-or-operator-pipe.md)<sup>b</sup>\
        [`bool`](bool-cpp.md)\
        [`break`](break-statement-cpp.md)\
        [`case`](switch-statement-cpp.md)\
        [`catch`](try-throw-and-catch-statements-cpp.md)\
        [`char`](fundamental-types-cpp.md)\
        [`char8_t`](fundamental-types-cpp.md)<sup>c</sup>\
        [`char16_t`](char-wchar-t-char16-t-char32-t.md)\
        [`char32_t`](char-wchar-t-char16-t-char32-t.md)\
        [`class`](class-cpp.md)\
        [`compl`](one-s-complement-operator-tilde.md)<sup>b</sup>\
        **`concept`**<sup>c</sup>\
        [`const`](const-cpp.md)\
        [`const_cast`](const-cast-operator.md)\
        **`consteval`**<sup>c</sup>\
        [`constexpr`](constexpr-cpp.md)
    :::column-end:::
    :::column:::
        **`constinit`**<sup>c</sup>\
        [`continue`](continue-statement-cpp.md)\
        **`co_await`**<sup>c</sup>\
        **`co_return`**<sup>c</sup>\
        **`co_yield`**<sup>c</sup>\
        [`decltype`](decltype-cpp.md)\
        [`default`](switch-statement-cpp.md)\
        [`delete`](delete-operator-cpp.md)\
        [`do`](do-while-statement-cpp.md)\
        [`double`](fundamental-types-cpp.md)\
        [`dynamic_cast`](dynamic-cast-operator.md)\
        [`else`](if-else-statement-cpp.md)\
        [`enum`](enumerations-cpp.md)\
        [`explicit`](user-defined-type-conversions-cpp.md)\
        **`export`**<sup>c</sup>\
        [`extern`](./extern-cpp.md)\
        [`false`](false-cpp.md)\
        [`float`](fundamental-types-cpp.md)\
        [`for`](for-statement-cpp.md)\
        [`friend`](friend-cpp.md)\
        [`goto`](goto-statement-cpp.md)\
        [`if`](if-else-statement-cpp.md)\
        [`inline`](inline-functions-cpp.md)
    :::column-end:::
    :::column:::
        [`int`](fundamental-types-cpp.md)\
        [`long`](fundamental-types-cpp.md)\
        [`mutable`](mutable-data-members-cpp.md)\
        [`namespace`](namespaces-cpp.md)\
        [`new`](new-operator-cpp.md)\
        [`noexcept`](noexcept-cpp.md)\
        [`not`](logical-negation-operator-exclpt.md)<sup>b</sup>\
        [`not_eq`](equality-operators-equal-equal-and-exclpt-equal.md)<sup>b</sup>\
        [`nullptr`](nullptr.md)\
        [`operator`](operator-overloading.md)\
        [`or`](logical-or-operator-pipe-pipe.md)<sup>b</sup>\
        [`or_eq`](assignment-operators.md)<sup>b</sup>\
        [`private`](private-cpp.md)\
        [`protected`](protected-cpp.md)\
        [`public`](public-cpp.md)\
        [`register`](storage-classes-cpp.md#register) [`reinterpret_cast`](reinterpret-cast-operator.md)\
        **`requires`**<sup>c</sup>\
        [`return`](return-statement-cpp.md)\
        [`short`](fundamental-types-cpp.md)\
        [`signed`](fundamental-types-cpp.md)\
        [`sizeof`](sizeof-operator.md)\
        [`static`](storage-classes-cpp.md)\
        [`static_assert`](static-assert.md)
    :::column-end:::
    :::column:::
        [`static_cast`](static-cast-operator.md)\
        [`struct`](struct-cpp.md)\
        [`switch`](switch-statement-cpp.md)\
        [`template`](templates-cpp.md)\
        [`this`](this-pointer.md)\
        [`thread_local`](storage-classes-cpp.md#thread_local)\
        [`throw`](try-throw-and-catch-statements-cpp.md)\
        [`true`](true-cpp.md)\
        [`try`](try-throw-and-catch-statements-cpp.md)\
        [`typedef`](aliases-and-typedefs-cpp.md)\
        [`typeid`](typeid-operator.md)\
        [`typename`](typename.md)\
        [`union`](unions.md)\
        [`unsigned`](fundamental-types-cpp.md)\
        [`using`](using-declaration.md) bağımsız
        [`using`](namespaces-cpp.md#using_directives) deki
        [`virtual`](virtual-cpp.md)\
        [`void`](void-cpp.md)\
        [`volatile`](volatile-cpp.md)\
        [`wchar_t`](fundamental-types-cpp.md)\
        [`while`](while-statement-cpp.md)\
        [`xor`](bitwise-exclusive-or-operator-hat.md)<sup>b</sup>\
        [`xor_eq`](assignment-operators.md)<sup>b</sup>
    :::column-end:::
:::row-end:::

<sup></sup> Microsoft 'a özgü **`__asm`** anahtar sözcüğü C++ **`asm`** söz dizimini değiştirir. **`asm`** diğer C++ uygulamalarıyla uyumluluk için ayrılmıştır, ancak uygulanmaz. **`__asm`** X86 hedeflerinde satır içi derleme için kullanın. Microsoft C++, diğer hedefler için satır Içi derlemeyi desteklemez.

<sup>b</sup> Genişletilmiş operatör eş anlamlıları [`/permissive-`](../build/reference/permissive-standards-conformance.md) [ `/Za` \( dil uzantıları olduğunda veya devre dışı](../build/reference/za-ze-disable-language-extensions.md) bırakıldığında anahtar kelimelerdir. Microsoft uzantıları etkinleştirildiğinde anahtar kelimelerdir.

belirtildiğinde <sup>c</sup> desteklenir [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) .

## <a name="microsoft-specific-c-keywords"></a>Microsoft 'a özgü C++ anahtar sözcükleri

C++ ' da, iki ardışık alt çizgi içeren tanımlayıcılar derleyici uygulamaları için ayrılmıştır. Microsoft kuralı, Microsoft 'a özgü anahtar sözcüklerden önce iki alt çizgi ile önce gelmelidir. Bu sözcükler tanımlayıcı adı olarak kullanılamaz.

Microsoft uzantıları varsayılan olarak etkinleştirilmiştir. Programlarınızın tamamen taşınabilir olmasını sağlamak için [`/permissive-`](../build/reference/permissive-standards-conformance.md) derleme sırasında veya [ `/Za` \( dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) seçeneğini belirleyerek Microsoft uzantılarını devre dışı bırakabilirsiniz. Bu seçenekler, Microsoft 'a özgü bazı anahtar kelimeleri devre dışı bırakır.

Microsoft uzantıları etkinleştirildiğinde, programlarınızda Microsoft 'a özgü anahtar sözcüklerini kullanabilirsiniz. ANSI uyumluluğu için bu anahtar sözcükler bir çift alt çizgi ile önceden başlar. Geriye dönük uyumluluk için, çift altı puanlanmış anahtar sözcüklerin çoğunun tek alt çizgi sürümleri desteklenir. **`__cdecl`** Anahtar sözcüğü, önde gelen alt çizgi olmadan kullanılabilir.

**`__asm`** Anahtar sözcüğü C++ **`asm`** söz dizimini değiştirir. **`asm`** diğer C++ uygulamalarıyla uyumluluk için ayrılmıştır, ancak uygulanmaz. **`__asm`** adresini kullanın.

**`__based`** Anahtar sözcüğü 32-bit ve 64-bit hedef derlemeler için sınırlı kullanımları vardır.

:::row:::
    :::column:::
        [`__alignof`](alignof-operator.md)<sup>e</sup>\
        [`__asm`](../assembler/inline/asm.md)<sup>e</sup>\
        [`__assume`](../intrinsics/assume.md)<sup>e</sup>\
        [`__based`](based-pointers-cpp.md)<sup>e</sup>\
        [`__cdecl`](cdecl.md)<sup>e</sup>\
        [`__declspec`](declspec.md)<sup>e</sup>\
        [`__event`](event.md)\
        [`__except`](try-except-statement.md)<sup>e</sup>\
        [`__fastcall`](fastcall.md)<sup>e</sup>\
        [`__finally`](try-finally-statement.md)<sup>e</sup>\
        [`__forceinline`](inline-functions-cpp.md)<sup>e</sup>
    :::column-end:::
    :::column:::
        [`__hook`](hook.md)<sup>d</sup>\
        [`__if_exists`](if-exists-statement.md)\
        [`__if_not_exists`](if-not-exists-statement.md)\
        [`__inline`](inline-functions-cpp.md)<sup>e</sup>\
        [`__int16`](int8-int16-int32-int64.md)<sup>e</sup>\
        [`__int32`](int8-int16-int32-int64.md)<sup>e</sup>\
        [`__int64`](int8-int16-int32-int64.md)<sup>e</sup>\
        [`__int8`](int8-int16-int32-int64.md)<sup>e</sup>\
        [`__interface`](interface.md)\
        [`__leave`](try-finally-statement.md)<sup>e</sup>\
        [`__m128`](m128.md)
    :::column-end:::
    :::column:::
        [`__m128d`](m128d.md)\
        [`__m128i`](m128i.md)\
        [`__m64`](m64.md)\
        [`__multiple_inheritance`](inheritance-keywords.md)<sup>e</sup>\
        [`__ptr32`](ptr32-ptr64.md)<sup>e</sup>\
        [`__ptr64`](ptr32-ptr64.md)<sup>a</sup>\
        [`__raise`](raise.md)\
        [`__restrict`](extension-restrict.md)<sup>e</sup>\
        [`__single_inheritance`](inheritance-keywords.md)<sup>a</sup>\
        [`__sptr`](sptr-uptr.md)<sup>a</sup>\
        [`__stdcall`](stdcall.md)<sup>e</sup>
    :::column-end:::
    :::column:::
        [`__super`](super.md)\
        [`__thiscall`](thiscall.md)\
        [`__unaligned`](unaligned.md)<sup>e</sup>\
        [`__unhook`](unhook.md)<sup>d</sup>\
        [`__uptr`](sptr-uptr.md)<sup>e</sup>\
        [`__uuidof`](uuidof-operator.md)<sup>e</sup>\
        [`__vectorcall`](vectorcall.md)<sup>e</sup>\
        [`__virtual_inheritance`](inheritance-keywords.md)<sup>e</sup>\
        [`__w64`](w64.md)<sup>e</sup>\
        [`__wchar_t`](fundamental-types-cpp.md)
    :::column-end:::
:::row-end:::

olay işlemede kullanılan <sup>d</sup> iç işlevi.

<sup>e</sup> önceki sürümlerle geriye dönük uyumluluk için, bu anahtar sözcükler hem iki önde gelen alt çizgi ile hem de Microsoft uzantıları etkinleştirildiğinde (varsayılan) tek başına bir alt çizgi ile kullanılabilir.

## <a name="microsoft-keywords-in-__declspec-modifiers"></a>__Declspec değiştiricilerinde Microsoft anahtar sözcükleri

Bu tanımlayıcılar, değiştiricinin genişletilmiş öznitelikleridir **`__declspec`** . Bu bağlam içindeki anahtar sözcükler kabul edilir.

:::row:::
    :::column:::
        [`align`](align-cpp.md)\
        [`allocate`](allocate.md)\
        [`allocator`](allocator.md)\
        [`appdomain`](appdomain.md)\
        [`code_seg`](code-seg-declspec.md)\
        [`deprecated`](deprecated-cpp.md)
    :::column-end:::
    :::column:::
        [`dllexport`](dllexport-dllimport.md)\
        [`dllimport`](dllexport-dllimport.md)\
        [`jitintrinsic`](jitintrinsic.md)\
        [`naked`](naked-cpp.md)\
        [`noalias`](noalias.md)\
        [`noinline`](noinline.md)
    :::column-end:::
    :::column:::
        [`noreturn`](noreturn.md)\
        [`no_sanitize_address`](no-sanitize-address.md)\
        [`nothrow`](nothrow-cpp.md)\
        [`novtable`](novtable.md)\
        [`process`](process.md)\
        [`property`](property-cpp.md)
    :::column-end:::
    :::column:::
        [`restrict`](restrict.md)\
        [`safebuffers`](safebuffers.md)\
        [`selectany`](selectany.md)\
        [`spectre`](spectre.md)\
        [`thread`](thread.md)\
        [`uuid`](uuid-cpp.md)
    :::column-end:::
:::row-end:::

## <a name="ccli-and-ccx-keywords"></a>C++/CLı ve C++/CX anahtar sözcükleri

:::row:::
    :::column:::
        [`__abstract`](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<sup>f</sup>\
        [`__box`](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<sup>f</sup>\
        [`__delegate`](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<sup>f</sup>\
        [`__gc`](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<sup>f</sup>\
        [`__identifier`](../extensions/identifier-cpp-cli.md)\
        [`__nogc`](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<sup>f</sup>\
        [`__noop`](../intrinsics/noop.md)\
        **`__pin`**<sup>f</sup>\
        **`__property`**<sup>f</sup>\
        **`__sealed`**<sup>f</sup>
    :::column-end:::
    :::column:::
        [`__try_cast`](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<sup>f</sup>\
        [`__value`](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<sup>f</sup>\
        [`abstract`](../extensions/abstract-cpp-component-extensions.md)<sup>g</sup>\
        [`array`](../extensions/arrays-cpp-component-extensions.md)<sup>g</sup>\
        [`as_friend`](../preprocessor/hash-using-directive-cpp.md)\
        [`delegate`](../extensions/delegate-cpp-component-extensions.md)<sup>g</sup>\
        [`enum class`](../extensions/enum-class-cpp-component-extensions.md)\
        [`enum struct`](../extensions/enum-class-cpp-component-extensions.md)\
        [`event`](../extensions/event-cpp-component-extensions.md)<sup>g</sup>
    :::column-end:::
    :::column:::
        [`finally`](../dotnet/finally.md)\
        [`for each in`](../dotnet/for-each-in.md)\
        [`gcnew`](../extensions/ref-new-gcnew-cpp-component-extensions.md)<sup>g</sup>\
        [`generic`](../extensions/generics-cpp-component-extensions.md)<sup>g</sup>\
        [`initonly`](../dotnet/initonly-cpp-cli.md)\
        [`interface class`](../extensions/interface-class-cpp-component-extensions.md)<sup>g</sup>\
        [`interface struct`](../extensions/interface-class-cpp-component-extensions.md)<sup>g</sup>\
        [`interior_ptr`](../extensions/interior-ptr-cpp-cli.md)<sup>g</sup>\
        [`literal`](../extensions/literal-cpp-component-extensions.md)<sup>g</sup>
    :::column-end:::
    :::column:::
        [`new`](../extensions/new-new-slot-in-vtable-cpp-component-extensions.md)<sup>g</sup>\
        [`property`](../extensions/property-cpp-component-extensions.md)<sup>g</sup>\
        [`ref class`](../extensions/classes-and-structs-cpp-component-extensions.md)\
        [`ref struct`](../extensions/classes-and-structs-cpp-component-extensions.md)\
        [`safecast`](../extensions/safe-cast-cpp-component-extensions.md)\
        [`sealed`](../extensions/sealed-cpp-component-extensions.md)<sup>g</sup>\
        [`typeid`](../extensions/typeid-cpp-component-extensions.md)\
        [`value class`](../extensions/classes-and-structs-cpp-component-extensions.md)<sup>g</sup>\
        [`value struct`](../extensions/classes-and-structs-cpp-component-extensions.md)<sup>g</sup>
    :::column-end:::
:::row-end:::

<sup>f</sup> yalnızca C++ için yönetilen uzantılar için geçerlidir. Bu sözdizimi artık kullanım dışıdır. Daha fazla bilgi için bkz. [çalışma zamanı platformları Için bileşen uzantıları](../extensions/component-extensions-for-runtime-platforms.md).

C++/Clia <sup>uygulanabilir.</sup>

## <a name="see-also"></a>Ayrıca bkz.

[Sözcük kuralları](lexical-conventions.md)<br/>
[C++ yerleşik işleçleri, önceliği ve ilişkilendirilebilirlik](cpp-built-in-operators-precedence-and-associativity.md)
