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
ms.openlocfilehash: bb1a632ffe684ac0777d0089a2edfd514bf66d0b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223804"
---
# <a name="zcimplicitnoexcept-implicit-exception-specifiers"></a>/ZC:implicitNoexcept (Örtük Özel Durum Tanımlayıcıları)

**/Zc: implicitNoexcept** seçeneği belirtildiğinde, derleyici derleyici tanımlı özel üye işlevlerine ve Kullanıcı tanımlı Yıkıcılar ve anlaşanların yer aldığı bir örtük [noexcept](../../cpp/noexcept-cpp.md) özel durum tanımlayıcısı ekler. Varsayılan olarak, **/Zc: IMPLICITNOEXCEPT** ISO c++ 11 standardına uyacak şekilde etkindir. Bu seçeneği kapatmak, **`noexcept`** Kullanıcı tanımlı Yıkıcılar ve satıcılarla ilgili özel üye işlevleri üzerinde örtülü olarak devre dışı bırakır.

## <a name="syntax"></a>Sözdizimi

> **/Zc: implicitNoexcept**[ **-** ]

## <a name="remarks"></a>Açıklamalar

**/Zc: implicitNoexcept** , derleyiciye ISO c++ 11 standardının 15,4 bölümünü izlemesini söyler. Örtülü olarak **`noexcept`** belirtilen her bir özel üye işlevine (Varsayılan Oluşturucu, kopya Oluşturucu, taşıma Oluşturucu, yıkıcı, kopya atama işleci veya taşıma atama işleci) ve her kullanıcı tanımlı yıkıcı veya ayırıcı işlevi için bir özel durum tanımlayıcısı ekler. Kullanıcı tanımlı bir ayırıcı örtük bir `noexcept(true)` özel durum tanımlayıcısına sahiptir. Kullanıcı tanımlı Yıkıcılar için örtük özel durum Belirleyicisi, `noexcept(true)` Kapsanan bir üye sınıfı veya taban sınıfının olmayan bir yıkıcıya sahip olmaması durumunda olur `noexcept(true)` . Derleyicinin ürettiği özel üye işlevleri için, bu işlev tarafından doğrudan çağrılan herhangi bir işlev etkin bir şekilde `noexcept(false)` , örtük özel durum belirleyicisi olur `noexcept(false)` . Aksi takdirde, örtük özel durum belirleyicisi olur `noexcept(true)` .

Derleyici açık **`noexcept`** veya **`throw`** belirticiler veya bir öznitelik kullanılarak belirtilen işlevler için örtük bir özel durum tanımlayıcısı oluşturmaz `__declspec(nothrow)` .

Varsayılan olarak, **/Zc: implicitNoexcept** etkindir. [/Permissive-](permissive-standards-conformance.md) seçeneği **/Zc: implicitNoexcept**öğesini etkilemez.

Seçenek **/Zc: implicitNoexcept-** belirtilerek devre dışı bırakılmışsa, derleyici tarafından örtük özel durum belirticileri oluşturulmaz. Bu davranış, özel durum belirticileri olmayan yok ediciler ve anlaşıcıları deyimleri olabilecek Visual Studio 2013 aynıdır **`throw`** . Varsayılan olarak, ve **/Zc: implicitNoexcept** belirtildiğinde, bir **`throw`** ifadede örtük tanımlayıcı içeren bir işlevde çalışma zamanında karşılaşılırsa, `noexcept(true)` Bu `std::terminate` durum, özel durum işleyicilerinin anında çağrılmasını ve normal geri sarma davranışının garanti edilmesine neden olur. Bu durumun tanımlanmasına yardımcı olmak için derleyici [Derleyici Uyarısı (düzey 1) C4297](../../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md)oluşturur. **`throw`** Bilerek yapılıyorsa, işlev bildiriinizi `noexcept(false)` **/Zc: implicitNoexcept-** yerine açık bir belirticiye sahip olacak şekilde değiştirmenizi öneririz.

Bu örnek, **/Zc: implicitNoexcept** seçeneği ayarlandığında veya devre dışı bırakıldığında açık özel durum belirleyicisi olmayan kullanıcı tanımlı bir yıkıcının nasıl davranacağını gösterir. Ayarlandığında, kullanarak derleyen davranışı göstermek için `cl /EHsc /W4 implicitNoexcept.cpp` . Devre dışı bırakıldığında davranışı göstermek için kullanarak derleyin `cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp` .

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

**/Zc: implicitNoexcept**varsayılan ayarı kullanılarak derlendiğinde, örnek bu çıktıyı oluşturur:

```Output
~B Exception caught
Unexpected throw caused std::terminate
Exit returning EXIT_FAILURE
```

**/Zc: implicitNoexcept-** ayarı kullanılarak derlendiğinde, örnek bu çıktıyı oluşturur:

```Output
~B Exception caught
~D Exception caught
Exit returning EXIT_SUCCESS
```

Visual C++ uyumluluk sorunları hakkında daha fazla bilgi için bkz. [Standart olmayan davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** özelliğini **/Zc: implicitNoexcept** veya **/Zc: implicitNoexcept** içerecek şekilde değiştirin ve ardından **Tamam**' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[/Zc (Uyumluluk)](zc-conformance.md)<br/>
[noexcept](../../cpp/noexcept-cpp.md)<br/>
[Özel durum belirtimleri (throw)](../../cpp/exception-specifications-throw-cpp.md)<br/>
[sonlandırmayı](../../standard-library/exception-functions.md#terminate)<br/>
