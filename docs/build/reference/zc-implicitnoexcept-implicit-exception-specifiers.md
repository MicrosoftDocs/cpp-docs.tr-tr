---
title: '/ ZC: implicitnoexcept (örtük özel durum tanımlayıcıları) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc:implicitNoexcept
dev_langs:
- C++
helpviewer_keywords:
- /Zc:implicitNoexcept
- Zc:implicitNoexcept
- -Zc:implicitNoexcept
ms.assetid: 71807652-6f9d-436b-899e-f52daa6f500b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e420017056d6857a2809ce6eb85fe99b6f3866f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="zcimplicitnoexcept-implicit-exception-specifiers"></a>/ZC:implicitNoexcept (Örtük Özel Durum Tanımlayıcıları)

Zaman **/ZC: implicitnoexcept** seçeneği belirtildiğinde, derleyici örtülü ekler [noexcept](../../cpp/noexcept-cpp.md) özel durum belirleyici derleyici tanımlı özel üye işlevleri ve kullanıcı tanımlı yok ediciler ve deallocators. Varsayılan olarak, **/ZC: implicitnoexcept** C ++ 11 standart ISO uyacak şekilde etkinleştirilir. Bu seçeneğini devre dışı bırakır örtük kapatma `noexcept` kullanıcı tanımlı yok ediciler ve dealloacators ve derleyici tanımlı özel üye işlevleri.

## <a name="syntax"></a>Sözdizimi

> **/Zc:implicitNoexcept**[**-**]

## <a name="remarks"></a>Açıklamalar

**/ ZC: implicitnoexcept** C ++ 11 standart ISO 15.4 bölümünü izleyin bildirir. Örtük olarak ekler bir `noexcept` özel durum belirleyici her örtülü olarak bildirilen veya açıkça varsayılan özel üye işlevine — varsayılan oluşturucu kopyalama oluşturucusu, taşıma oluşturucusu, yıkıcı, kopya atama işleci veya atama taşıma işleç — ve her kullanıcı tarafından tanımlanan yıkıcı veya deallocator işlevi. Kullanıcı tanımlı bir deallocator örtülü sahip `noexcept(true)` özel durum tanımlayıcısı. Kullanıcı tanımlı Yıkıcılar için örtük özel durum belirleyici olduğu `noexcept(true)` kapsanan üye sınıfı veya temel sınıf değil bir yıkıcı olmadıkça `noexcept(true)`. Derleyicinin ürettiği özel üye işlevleri, doğrudan bu işlev tarafından çağrılan işlev etkin ise için `noexcept(false)`, örtük özel durum belirleyici olduğu `noexcept(false)`. Aksi takdirde, örtük özel durum belirleyici değer `noexcept(true)`.

Derleyici kullanarak açık bildirilen işlevler için örtük özel durum belirleyici oluşturmaz `noexcept` veya `throw` tanımlayıcıları veya `__declspec(nothrow)` özniteliği.

Varsayılan olarak, **/ZC: implicitnoexcept** etkinleştirilir. [/ İzin veren-](permissive-standards-conformance.md) seçeneği etkilemez **/ZC: implicitnoexcept**.

Seçeneğini belirterek devre dışı bırakılırsa **/Zc:implicitNoexcept-**, hiçbir örtük özel durum tanımlayıcıları derleyici tarafından oluşturulur. Bu davranış Visual Studio 2013, yok ediciler ve özel durum tanımlayıcıları sahip değilse deallocators sahip olduğu ile aynıdır `throw` deyimleri. Varsayılan olarak, ne zaman ve **/ZC: implicitnoexcept** , belirtilmişse, bir `throw` deyimi karşılaştı çalışma zamanında bir örtük bir işlev içinde `noexcept(true)` belirticisi hemen çağrısından neden `std::terminate`, ve özel durum işleyicileri için normal unwinding davranışı garanti edilmez. Bu durum tanımlamaya yardımcı olmak üzere derleyici oluşturur [Derleyici Uyarısı (düzey 1) C4297](../../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md). Varsa `throw` olan bilerek, açık bir sağlamak için işlev bildirimi değiştirme öneririz `noexcept(false)` kullanmak yerine belirleyici **/Zc:implicitNoexcept-**.

Bu örnek, hiçbir açık özel durum belirticisinin kullanıcı tanımlı bir yıkıcı ne zaman nasıl davranacağını göstermektedir **/ZC: implicitnoexcept** seçeneğini ayarlayın ya da devre dışı. Davranış göstermek için ayarlandığında, derleme kullanarak `cl /EHsc /W4 implicitNoexcept.cpp`. Devre dışı davranış göstermek için derleme kullanarak `cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp`.

```cpp
// implicitNoexcept.cpp
// Compile by using: cl /EHsc /W4 implicitNoexcept.cpp
// Compile by using: cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp

#include <iostream>
#include <cstdlib>      // for std::exit, EXIT_FAILURE, EXIT_SUCCESS
#include <exception>    // for std::set_terminate

void my_terminate()
{
    std::cout << "Unexpected throw caused std::terminate" << std::endl;
    std::cout << "Exit returning EXIT_FAILURE" << std::endl;
    std::exit(EXIT_FAILURE);
}

struct A {
    // Explicit noexcept overrides implicit exception specification
    ~A() noexcept(false) {
        throw 1;
    }
};

struct B : public A {
    // Compiler-generated ~B() definition inherits noexcept(false)
    ~B() = default;
};

struct C {
    // By default, the compiler generates an implicit noexcept(true)
    // specifier for this user-defined destructor. To enable it to
    // throw an exception, use an explicit noexcept(false) specifier,
    // or compile by using /Zc:implicitNoexcept-
    ~C() {
        throw 1; // C4297, calls std::terminate() at run time
    }
};

struct D : public C {
    // This destructor gets the implicit specifier of its base.
    ~D() = default;
};

int main()
{
    std::set_terminate(my_terminate);

    try
    {
        {
            B b;
        }
    }
    catch (...)
    {
        // exception should reach here in all cases
        std::cout << "~B Exception caught" << std::endl;
    }
    try
    {
        {
            D d;
        }
    }
    catch (...)
    {
        // exception should not reach here if /Zc:implicitNoexcept
        std::cout << "~D Exception caught" << std::endl;
    }
    std::cout << "Exit returning EXIT_SUCCESS" << std::endl;
    return EXIT_SUCCESS;
}
```

Varsayılan ayar kullanarak derlendiğinde **/ZC: implicitnoexcept**, örnek bu bir çıktı üretir:

```Output
~B Exception caught
Unexpected throw caused std::terminate
Exit returning EXIT_FAILURE
```

Ayarını kullanarak derlendiğinde **/Zc:implicitNoexcept-**, örnek bu bir çıktı üretir:

```Output
~B Exception caught
~D Exception caught
Exit returning EXIT_SUCCESS
```

Visual c++ uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik **/ZC: implicitnoexcept** veya **/Zc:implicitNoexcept-** ve ardından **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](../../build/reference/zc-conformance.md)<br/>
[noexcept](../../cpp/noexcept-cpp.md)<br/>
[Özel Durum Belirtimleri (throw)](../../cpp/exception-specifications-throw-cpp.md)<br/>
[Sonlandırma](../../standard-library/exception-functions.md#terminate)<br/>
