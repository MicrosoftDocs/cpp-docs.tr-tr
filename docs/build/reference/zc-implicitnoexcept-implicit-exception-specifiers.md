---
title: /ZC:implicitNoexcept (Örtük Özel Durum Tanımlayıcıları)
ms.date: 03/06/2018
f1_keywords:
- /Zc:implicitNoexcept
helpviewer_keywords:
- /Zc:implicitNoexcept
- Zc:implicitNoexcept
- -Zc:implicitNoexcept
ms.assetid: 71807652-6f9d-436b-899e-f52daa6f500b
ms.openlocfilehash: ec2b8c8fb4c7730a78c4403606d6fa61c0ddc374
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810022"
---
# <a name="zcimplicitnoexcept-implicit-exception-specifiers"></a>/ZC:implicitNoexcept (Örtük Özel Durum Tanımlayıcıları)

Zaman **/ZC: implicitnoexcept** seçeneği belirtildiğinde, derleyici örtük ekler [noexcept](../../cpp/noexcept-cpp.md) derleyici tarafından tanımlanan özel üye işlevleri ve kullanıcı tanımlı yok ediciler için özel durum tanımlayıcısı ve deallocators. Varsayılan olarak, **/ZC: implicitnoexcept** ISO C ++ 11 standart uyacak şekilde etkinleştirilir. Bu seçeneğini devre dışı bırakır örtük kapatma `noexcept` kullanıcı tanımlı yok ediciler ve dealloacators ve derleyici tarafından tanımlanan özel üye işlevleri.

## <a name="syntax"></a>Sözdizimi

> **/Zc:implicitNoexcept**[**-**]

## <a name="remarks"></a>Açıklamalar

**/ ZC: implicitnoexcept** derleyiciye ISO C ++ 11 standart 15.4 bölümünü izleyin. Örtük olarak ekler bir `noexcept` her örtük olarak bildirilen veya açıkça varsayılan haline getirilen özel üye işlev özel durum tanımlayıcısı: varsayılan oluşturucu Oluşturucu, taşıma Oluşturucu, yıkıcı, kopya atama işleci kopyalama veya taşıma atama işleç — ve her kullanıcı tanımlı yıkıcı ve birleştiricinin işlevi. Kullanıcı tanımlı bir birleştiricinin örtük sahip `noexcept(true)` özel durum tanımlayıcısı. Kullanıcı tanımlı yok ediciler için örtük özel durum tanımlayıcısıdır `noexcept(true)` içindeki üye sınıfı veya temel sınıf olmayan bir yıkıcı olmadıkça `noexcept(true)`. Etkili bir şekilde doğrudan bu işlev tarafından çağrılan bir işlev ise, derleyicinin ürettiği özel üye işlevleri için `noexcept(false)`, örtük özel durum tanımlayıcısı `noexcept(false)`. Aksi takdirde, örtük özel durum tanımlayıcısı olan `noexcept(true)`.

Derleyici bir örtük özel durum tanımlayıcısı kullanılarak açık bildirilen işlevler için oluşturmaz `noexcept` veya `throw` tanımlayıcıları veya `__declspec(nothrow)` özniteliği.

Varsayılan olarak, **/ZC: implicitnoexcept** etkinleştirilir. [/ Permissive-](permissive-standards-conformance.md) seçeneği etkilemez **/ZC: implicitnoexcept**.

Seçeneğini belirterek devre dışı bırakılırsa **/Zc:implicitNoexcept-**, hiçbir örtük özel durum tanımlayıcıları, derleyici tarafından oluşturulur. Bu yok ediciler ve özel durum tanımlayıcıları yoktu deallocators sahip olduğu Visual Studio 2013 ile aynı, davranıştır `throw` deyimleri. Varsayılan olarak, ne zaman **/ZC: implicitnoexcept** , belirtilmişse bir `throw` deyimi, çalışma zamanında bir işlev örtük ile karşılaşıldığında `noexcept(true)` belirticisi hemen çağrısından neden `std::terminate`, ve özel durum işleyicileri için geriye doğru izleme normal davranış garanti edilmez. Bu durum belirlemenize yardımcı olması için derleyici oluşturur [Derleyici Uyarısı (düzey 1) C4297](../../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md). Varsa `throw` olduğunu bilerek, açık bir sağlamak için işlev bildirimi değiştirmeniz önerilir `noexcept(false)` kullanmak yerine belirticisi **/Zc:implicitNoexcept-**.

Bu örnek, hiçbir açık özel durum tanımlayıcısına sahip kullanıcı tanımlı bir yıkıcı olduğunda nasıl davranacağını gösterir **/ZC: implicitnoexcept** seçeneği ayarlanır veya devre dışı. Davranış gösterecek şekilde ayarlandığında, kullanarak derleme `cl /EHsc /W4 implicitNoexcept.cpp`. Kullanarak devre dışı bırakıldığında davranışını göstermek için derleme `cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp`.

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

Varsayılan ayar kullanılarak derlendiğinde **/ZC: implicitnoexcept**, örnek aşağıdaki çıkışı üretir:

```Output
~B Exception caught
Unexpected throw caused std::terminate
Exit returning EXIT_FAILURE
```

Ayar kullanılarak derlendiğinde **/Zc:implicitNoexcept-**, örnek aşağıdaki çıkışı üretir:

```Output
~B Exception caught
~D Exception caught
Exit returning EXIT_SUCCESS
```

Visual C++'ta uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik **/ZC: implicitnoexcept** veya **/Zc:implicitNoexcept-** seçip **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](zc-conformance.md)<br/>
[noexcept](../../cpp/noexcept-cpp.md)<br/>
[Özel Durum Belirtimleri (throw)](../../cpp/exception-specifications-throw-cpp.md)<br/>
[sonlandırma](../../standard-library/exception-functions.md#terminate)<br/>
