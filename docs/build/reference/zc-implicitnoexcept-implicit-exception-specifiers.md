---
title: "-Zc: implicitNoexcept (örtük özel durum tanımlayıcıları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /Zc:implicitNoexcept
dev_langs:
- C++
helpviewer_keywords:
- /Zc:implicitNoexcept
- Zc:implicitNoexcept
- -Zc:implicitNoexcept
ms.assetid: 71807652-6f9d-436b-899e-f52daa6f500b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9af0a7a3a175699a4f4b738271fe0d4c5bbac4b2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="zcimplicitnoexcept-implicit-exception-specifiers"></a>/ZC:implicitNoexcept (Örtük Özel Durum Tanımlayıcıları)
Zaman **/ZC: implicitnoexcept** seçeneği belirtildiğinde, derleyici örtülü ekler [noexcept](../../cpp/noexcept-cpp.md) özel durum belirleyici derleyici tanımlı özel üye işlevleri ve kullanıcı tanımlı yok ediciler ve deallocators. Varsayılan olarak, **/ZC: implicitnoexcept** C ++ 11 standart ISO uyacak şekilde etkinleştirilir. Bu seçeneğini devre dışı bırakır örtük kapatma `noexcept` kullanıcı tanımlı yok ediciler ve dealloacators ve derleyici tanımlı özel üye işlevleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
/Zc:implicitNoexcept[-]  
```  
  
#### <a name="parameters"></a>Parametreler  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak ve **/ZC: implicitnoexcept** belirtilirse, derleyici C ++ 11 standart ISO 15.4 bölümünü izler ve örtük olarak ekler bir `noexcept` her özel durum belirleyici örtülü olarak bildirilen veya açıkça varsayılan Özel üye fonksiyonu — varsayılan oluşturucu, kopya Oluşturucu, taşıma oluşturucusu, yıkıcı, kopya atama işleci veya taşıma atama işleci — ve her kullanıcı tarafından tanımlanan yıkıcı veya deallocator işlevi. Kullanıcı tanımlı bir deallocator örtülü sahip `noexcept(true)` özel durum tanımlayıcısı. Kullanıcı tanımlı Yıkıcılar için örtük özel durum belirleyici olduğu `noexcept(true)` kapsanan üye sınıfı veya temel sınıf değil bir yıkıcı olmadıkça `noexcept(true)`. Derleyicinin ürettiği özel üye işlevleri, doğrudan bu işlev tarafından çağrılan işlev etkin ise için `noexcept(false)`, örtük özel durum belirleyici olduğu `noexcept(false)`. Aksi takdirde, örtük özel durum belirleyici değer `noexcept(true)`.  
  
 Derleyici kullanarak açık bildirilen işlevler için örtük özel durum belirleyici oluşturmaz `noexcept` veya `throw` tanımlayıcıları veya `__declspec(nothrow)` özniteliği.  
  
 Seçeneğini belirterek devre dışı bırakılırsa **/Zc:implicitNoexcept-**, hiçbir örtük özel durum tanımlayıcıları derleyici tarafından oluşturulur. Bu davranış Visual Studio 2013, yok ediciler ve özel durum tanımlayıcıları sahip değilse deallocators sahip olduğu ile aynıdır `throw` deyimleri. Varsayılan olarak, ne zaman ve **/ZC: implicitnoexcept** , belirtilmişse, bir `throw` deyimi karşılaştı çalışma zamanında bir örtük bir işlev içinde `noexcept(true)` belirticisi hemen çağrısından neden `std::terminate`, ve özel durum işleyicileri için normal unwinding davranışı garanti edilmez. Bu durum tanımlamaya yardımcı olmak üzere derleyici oluşturur [Derleyici Uyarısı (düzey 1) C4297](../../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md). Varsa `throw` olan bilerek, açık bir sağlamak için işlev bildirimi değiştirme öneririz `noexcept(false)` kullanmak yerine belirleyici **/Zc:implicitNoexcept-**.  
  
 Bu örnek, hiçbir açık özel durum belirticisinin kullanıcı tanımlı bir yıkıcı ne zaman nasıl davranacağını göstermektedir **/ZC: implicitnoexcept** seçeneğini ayarlayın ya da devre dışı. Davranış göstermek için ayarlandığında, derleme kullanarak `cl /EHsc /W4 implicitNoexcept.cpp`. Devre dışı davranış göstermek için derleme kullanarak `cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp`.  
  
```  
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
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **C/C++** klasör.  
  
3.  Seçin **komut satırı** özellik sayfası.  
  
4.  Değiştirme **ek seçenekler** eklenecek özellik **/ZC: implicitnoexcept** veya **/Zc:implicitNoexcept-** ve ardından **Tamam**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/ZC (Uyumluluk)](../../build/reference/zc-conformance.md)   
 [noexcept](../../cpp/noexcept-cpp.md)   
 [Özel durum belirtimleri (throw)](../../cpp/exception-specifications-throw-cpp.md)   
 [sonlandırma](../../standard-library/exception-functions.md#terminate)