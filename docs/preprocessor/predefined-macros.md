---
title: Önceden tanımlanmış makrolar
description: Microsoft C++ derleyicisi önceden tanımlanmış Önişlemci makrolarını listeler ve açıklar.
ms.custom: update_every_version
ms.date: 06/08/2020
f1_keywords:
- ':::no-loc(_ATL_VER):::'
- ':::no-loc(__ATOM__):::'
- ':::no-loc(__AVX__):::'
- ':::no-loc(__AVX2__):::'
- ':::no-loc(__AVX512BW__):::'
- ':::no-loc(__AVX512CD__):::'
- ':::no-loc(__AVX512DQ__):::'
- ':::no-loc(__AVX512F__):::'
- ':::no-loc(__AVX512VL__):::'
- ':::no-loc(_CHAR_UNSIGNED):::'
- ':::no-loc(__CLR_VER):::'
- ':::no-loc(_CONTROL_FLOW_GUARD):::'
- ':::no-loc(__COUNTER__):::'
- ':::no-loc(__cplusplus):::'
- ':::no-loc(__cplusplus_cli):::'
- ':::no-loc(__cplusplus_winrt):::'
- ':::no-loc(_CPPRTTI):::'
- ':::no-loc(_CPPUNWIND):::'
- ':::no-loc(__DATE__):::'
- ':::no-loc(_DEBUG):::'
- ':::no-loc(_DLL):::'
- ':::no-loc(__FILE__):::'
- ':::no-loc(__FUNCDNAME__):::'
- ':::no-loc(__FUNCSIG__):::'
- ':::no-loc(__FUNCTION__):::'
- ':::no-loc(_INTEGRAL_MAX_BITS):::'
- ':::no-loc(_ISO_VOLATILE):::'
- ':::no-loc(_KERNEL_MODE):::'
- ':::no-loc(__LINE__):::'
- ':::no-loc(_M_AMD64):::'
- ':::no-loc(_M_ARM):::'
- ':::no-loc(_M_ARM_ARMV7VE):::'
- ':::no-loc(_M_ARM_FP):::'
- ':::no-loc(_M_ARM64):::'
- ':::no-loc(_M_CEE):::'
- ':::no-loc(_M_CEE_PURE):::'
- ':::no-loc(_M_CEE_SAFE):::'
- ':::no-loc(_M_FP_EXCEPT):::'
- ':::no-loc(_M_FP_FAST):::'
- ':::no-loc(_M_FP_PRECISE):::'
- ':::no-loc(_M_FP_STRICT):::'
- ':::no-loc(_M_IX86):::'
- ':::no-loc(_M_IX86_FP):::'
- ':::no-loc(_M_X64):::'
- ':::no-loc(_MANAGED):::'
- ':::no-loc(_MFC_VER):::'
- ':::no-loc(_MSC_BUILD):::'
- ':::no-loc(_MSC_EXTENSIONS):::'
- ':::no-loc(_MSC_FULL_VER):::'
- ':::no-loc(_MSC_VER):::'
- ':::no-loc(_MSVC_LANG):::'
- ':::no-loc(__MSVC_RUNTIME_CHECKS):::'
- ':::no-loc(_MT):::'
- ':::no-loc(_NATIVE_WCHAR_T_DEFINED):::'
- ':::no-loc(_NO_SIZED_DEALLOCATION):::'
- ':::no-loc(_OPENMP):::'
- ':::no-loc(_PREFAST_):::'
- ':::no-loc(_RESUMABLE_FUNCTIONS_SUPPORTED):::'
- ':::no-loc(_RTC_CONVERSION_CHECKS_ENABLED):::'
- ':::no-loc(__STDC__):::'
- ':::no-loc(__STDC_HOSTED__):::'
- ':::no-loc(__STDCPP_THREADS__):::'
- ':::no-loc(__TIME__):::'
- ':::no-loc(__TIMESTAMP__):::'
- ':::no-loc(__VA_ARGS__):::'
- ':::no-loc(_VC_NODEFAULTLIB):::'
- ':::no-loc(_WCHAR_T_DEFINED):::'
- ':::no-loc(_WIN32):::'
- ':::no-loc(_WIN64):::'
- ':::no-loc(_WINRT_DLL):::'
helpviewer_keywords:
- timestamps, preprocessor macro
- cl.exe compiler, version number
- version numbers, C/C++ compiler (cl.exe)
- macros, predefined C++
- preprocessor, macros
- predefined macros
- ':::no-loc(_ATL_VER)::: macro'
- ':::no-loc(__ATOM__)::: macro'
- ':::no-loc(__AVX__)::: macro'
- ':::no-loc(__AVX2__)::: macro'
- ':::no-loc(__AVX512BW__)::: macro'
- ':::no-loc(__AVX512CD__)::: macro'
- ':::no-loc(__AVX512DQ__)::: macro'
- ':::no-loc(__AVX512F__)::: macro'
- ':::no-loc(__AVX512VL__)::: macro'
- ':::no-loc(_CHAR_UNSIGNED)::: macro'
- ':::no-loc(__CLR_VER)::: macro'
- ':::no-loc(_CONTROL_FLOW_GUARD)::: macro'
- ':::no-loc(__COUNTER__)::: macro'
- ':::no-loc(__cplusplus)::: macro'
- ':::no-loc(__cplusplus_cli)::: macro'
- ':::no-loc(__cplusplus_winrt)::: macro'
- ':::no-loc(_CPPRTTI)::: macro'
- ':::no-loc(_CPPUNWIND)::: macro'
- ':::no-loc(__DATE__)::: macro'
- ':::no-loc(_DEBUG)::: macro'
- ':::no-loc(_DLL)::: macro'
- ':::no-loc(__FILE__)::: macro'
- ':::no-loc(__FUNCDNAME__)::: macro'
- ':::no-loc(__FUNCSIG__)::: macro'
- ':::no-loc(__FUNCTION__)::: macro'
- ':::no-loc(_INTEGRAL_MAX_BITS)::: macro'
- ':::no-loc(_ISO_VOLATILE)::: macro'
- ':::no-loc(_KERNEL_MODE)::: macro'
- ':::no-loc(__LINE__)::: macro'
- ':::no-loc(_M_AMD64)::: macro'
- ':::no-loc(_M_ARM)::: macro'
- ':::no-loc(_M_ARM_ARMV7VE)::: macro'
- ':::no-loc(_M_ARM_FP)::: macro'
- ':::no-loc(_M_ARM64)::: macro'
- ':::no-loc(_M_CEE)::: macro'
- ':::no-loc(_M_CEE_PURE)::: macro'
- ':::no-loc(_M_CEE_SAFE)::: macro'
- ':::no-loc(_M_FP_EXCEPT)::: macro'
- ':::no-loc(_M_FP_FAST)::: macro'
- ':::no-loc(_M_FP_PRECISE)::: macro'
- ':::no-loc(_M_FP_STRICT)::: macro'
- ':::no-loc(_M_IX86)::: macro'
- ':::no-loc(_M_IX86_FP)::: macro'
- ':::no-loc(_M_X64)::: macro'
- ':::no-loc(_MANAGED)::: macro'
- ':::no-loc(_MFC_VER)::: macro'
- ':::no-loc(_MSC_BUILD)::: macro'
- ':::no-loc(_MSC_EXTENSIONS)::: macro'
- ':::no-loc(_MSC_FULL_VER)::: macro'
- ':::no-loc(_MSC_VER)::: macro'
- ':::no-loc(_MSVC_LANG)::: macro'
- ':::no-loc(__MSVC_RUNTIME_CHECKS)::: macro'
- ':::no-loc(_MT)::: macro'
- ':::no-loc(_NATIVE_WCHAR_T_DEFINED)::: macro'
- ':::no-loc(_NO_SIZED_DEALLOCATION)::: macro'
- ':::no-loc(_OPENMP)::: macro'
- ':::no-loc(_PREFAST_)::: macro'
- ':::no-loc(_RESUMABLE_FUNCTIONS_SUPPORTED)::: macro'
- ':::no-loc(_RTC_CONVERSION_CHECKS_ENABLED)::: macro'
- ':::no-loc(__STDC__)::: macro'
- ':::no-loc(__STDC_HOSTED__)::: macro'
- ':::no-loc(__STDCPP_THREADS__)::: macro'
- ':::no-loc(__TIME__)::: macro'
- ':::no-loc(__TIMESTAMP__)::: macro'
- ':::no-loc(__VA_ARGS__)::: macro'
- ':::no-loc(_VC_NODEFAULTLIB)::: macro'
- ':::no-loc(_WCHAR_T_DEFINED)::: macro'
- ':::no-loc(_WIN32)::: macro'
- ':::no-loc(_WIN64)::: macro'
- ':::no-loc(_WINRT_DLL)::: macro'
- ':::no-loc(__func__)::: identifier'
ms.assetid: 1cc5f70a-a225-469c-aed0-fe766238e23f
no-loc:
- ':::no-loc(_ATL_VER):::'
- ':::no-loc(__ATOM__):::'
- ':::no-loc(__AVX__):::'
- ':::no-loc(__AVX2__):::'
- ':::no-loc(__AVX512BW__):::'
- ':::no-loc(__AVX512CD__):::'
- ':::no-loc(__AVX512DQ__):::'
- ':::no-loc(__AVX512F__):::'
- ':::no-loc(__AVX512VL__):::'
- ':::no-loc(_CHAR_UNSIGNED):::'
- ':::no-loc(__CLR_VER):::'
- ':::no-loc(_CONTROL_FLOW_GUARD):::'
- ':::no-loc(__COUNTER__):::'
- ':::no-loc(__cplusplus):::'
- ':::no-loc(__cplusplus_cli):::'
- ':::no-loc(__cplusplus_winrt):::'
- ':::no-loc(_CPPRTTI):::'
- ':::no-loc(_CPPUNWIND):::'
- ':::no-loc(__DATE__):::'
- ':::no-loc(_DEBUG):::'
- ':::no-loc(_DLL):::'
- ':::no-loc(__FILE__):::'
- ':::no-loc(__FUNCDNAME__):::'
- ':::no-loc(__FUNCSIG__):::'
- ':::no-loc(__FUNCTION__):::'
- ':::no-loc(_INTEGRAL_MAX_BITS):::'
- ':::no-loc(_ISO_VOLATILE):::'
- ':::no-loc(_KERNEL_MODE):::'
- ':::no-loc(__LINE__):::'
- ':::no-loc(_M_AMD64):::'
- ':::no-loc(_M_ARM):::'
- ':::no-loc(_M_ARM_ARMV7VE):::'
- ':::no-loc(_M_ARM_FP):::'
- ':::no-loc(_M_ARM64):::'
- ':::no-loc(_M_CEE):::'
- ':::no-loc(_M_CEE_PURE):::'
- ':::no-loc(_M_CEE_SAFE):::'
- ':::no-loc(_M_FP_EXCEPT):::'
- ':::no-loc(_M_FP_FAST):::'
- ':::no-loc(_M_FP_PRECISE):::'
- ':::no-loc(_M_FP_STRICT):::'
- ':::no-loc(_M_IX86):::'
- ':::no-loc(_M_IX86_FP):::'
- ':::no-loc(_M_X64):::'
- ':::no-loc(_MANAGED):::'
- ':::no-loc(_MFC_VER):::'
- ':::no-loc(_MSC_BUILD):::'
- ':::no-loc(_MSC_EXTENSIONS):::'
- ':::no-loc(_MSC_FULL_VER):::'
- ':::no-loc(_MSC_VER):::'
- ':::no-loc(_MSVC_LANG):::'
- ':::no-loc(__MSVC_RUNTIME_CHECKS):::'
- ':::no-loc(_MT):::'
- ':::no-loc(_NATIVE_WCHAR_T_DEFINED):::'
- ':::no-loc(_NO_SIZED_DEALLOCATION):::'
- ':::no-loc(_OPENMP):::'
- ':::no-loc(_PREFAST_):::'
- ':::no-loc(_RESUMABLE_FUNCTIONS_SUPPORTED):::'
- ':::no-loc(_RTC_CONVERSION_CHECKS_ENABLED):::'
- ':::no-loc(__STDC__):::'
- ':::no-loc(__STDC_HOSTED__):::'
- ':::no-loc(__STDCPP_THREADS__):::'
- ':::no-loc(__TIME__):::'
- ':::no-loc(__TIMESTAMP__):::'
- ':::no-loc(__VA_ARGS__):::'
- ':::no-loc(_VC_NODEFAULTLIB):::'
- ':::no-loc(_WCHAR_T_DEFINED):::'
- ':::no-loc(_WIN32):::'
- ':::no-loc(_WIN64):::'
- ':::no-loc(_WINRT_DLL):::'
- ':::no-loc(__func__):::'
ms.openlocfilehash: 1c7b2f18aede84d8067c36537f33261554c16c17
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222647"
---
# <a name="predefined-macros"></a>Önceden tanımlanmış makrolar

Microsoft C/C++ derleyicisi (MSVC), dile (C veya C++), derleme hedefine ve seçilen derleyici seçeneklerine bağlı olarak belirli Önişlemci makrolarını önceden tanımlar.

MSVC, ANSI/ISO C99 Standard ve ISO C++ 14 ve C++ 17 standartları için gereken önceden tanımlanmış Önişlemci makrolarını destekler. Uygulama, Microsoft 'a özgü birkaç önişlemci makrosunu da destekler. Bazı makrolar yalnızca belirli derleme ortamları veya derleyici seçenekleri için tanımlanır. Aksi belirtilmedikçe, makrolar, **`/D`** derleyici seçeneği bağımsız değişkenleri olarak belirtimiş gibi bir çeviri birimi boyunca tanımlanır. Tanımlandığında, makrolar derlemeden önce Önişlemci tarafından belirtilen değerlere genişletilir. Önceden tanımlanmış makrolar bağımsız değişken almaz ve yeniden tanımlanamaz.

## <a name="standard-predefined-identifier"></a>Standart önceden tanımlanmış tanımlayıcı

Derleyici ISO C99 ve ISO C++ 11 tarafından belirtilen önceden tanımlanmış tanımlayıcıyı destekler.

- `:::no-loc(__func__):::`İşlev yerel **statik const** dizisi olarak kapsayan işlevin nitelenmemiş ve donatımış adı **`char`** .

    ```cpp
    void example(){
        printf("%s\n", :::no-loc(__func__):::);
    } // prints "example"
    ```

## <a name="standard-predefined-macros"></a>Standart önceden tanımlanmış makrolar

Derleyici ISO C99 ve ISO C++ 17 standartları tarafından belirtilen önceden tanımlanmış makroları destekler.

- `:::no-loc(__cplusplus):::`Çeviri birimi C++ olarak derlendiğinde tamsayı sabit değeri olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(__DATE__):::`Geçerli kaynak dosyanın derleme tarihi. Tarih, *aaa gg yyyy*biçiminde sabit uzunluklu bir dize sabit değeri olur. Ay adı *aaa* , C çalışma zamanı KITAPLıĞı (CRT) [asctime](../c-runtime-library/reference/asctime-wasctime.md) işlevi tarafından oluşturulan kısaltılmış ay adı ile aynıdır. Değer 10 ' dan küçükse, *gg* 'nin ilk karakteri bir alandır. Bu makro her zaman tanımlanmıştır.

- `:::no-loc(__FILE__):::`Geçerli kaynak dosyanın adı. `:::no-loc(__FILE__):::`bir karakter dizesi değişmez değerine genişletilir. Dosyanın tam yolunun görüntülendiğinden emin olmak için, kullanın [ **`/FC`** (kaynak kodu dosyasının Tanılamadaki Tam yolu)](../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md). Bu makro her zaman tanımlanmıştır.

- `:::no-loc(__LINE__):::`Geçerli kaynak dosyasında tamsayı satır numarası olarak tanımlanır. `:::no-loc(__LINE__):::`Makronun değeri bir yönerge kullanılarak değiştirilebilir `#line` . Bu makro her zaman tanımlanmıştır.

- `:::no-loc(__STDC__):::`Yalnızca C olarak derlendiğinde ve derleyici seçeneği belirtilmişse 1 olarak tanımlanır [**`/Za`**](../build/reference/za-ze-disable-language-extensions.md) . Aksi takdirde, tanımsız.

- `:::no-loc(__STDC_HOSTED__):::`Uygulama, tüm gerekli standart kitaplığı destekleyen bir *barındırılan uygulama*ise, 1 olarak tanımlanır. Aksi takdirde, 0 olarak tanımlanır.

- `:::no-loc(__STDCPP_THREADS__):::`Yalnızca bir programda birden fazla yürütme iş parçacığı ve C++ olarak derlenmiş ise 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(__TIME__):::`Önceden işlenmiş çeviri biriminin çevirisi süresi. Bu zaman, *HH: mm: ss*biçimindeki bir karakter dizesi değişmez DEĞERI, CRT [asctime](../c-runtime-library/reference/asctime-wasctime.md) işlevi tarafından döndürülen zaman ile aynıdır. Bu makro her zaman tanımlanmıştır.

## <a name="microsoft-specific-predefined-macros"></a>Microsoft 'a özgü önceden tanımlanmış makrolar

MSVC bu önceden tanımlanmış ek makroları destekler.

- `:::no-loc(__ATOM__):::`[**`/favor:ATOM`**](../build/reference/favor-optimize-for-architecture-specifics.md)Derleyici seçeneği ayarlandığında ve derleyici hedefi x86 veya x64 olduğunda, 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(__AVX__):::`[**`/arch:AVX`**](../build/reference/arch-x86.md),, [**`/arch:AVX2`**](../build/reference/arch-x86.md) Veya [**`/arch:AVX512`**](../build/reference/arch-x86.md) derleyici seçenekleri ayarlandığında ve derleyici hedefi x86 veya x64 olduğunda, 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(__AVX2__):::`[**`/arch:AVX2`**](../build/reference/arch-x86.md)Or [**`/arch:AVX512`**](../build/reference/arch-x86.md) derleyici seçeneği ayarlandığında ve derleyici hedefi x86 veya x64 olduğunda, 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(__AVX512BW__):::`[**`/arch:AVX512`**](../build/reference/arch-x86.md)Derleyici seçeneği ayarlandığında ve derleyici hedefi x86 veya x64 olduğunda, 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(__AVX512CD__):::`[**`/arch:AVX512`**](../build/reference/arch-x86.md)Derleyici seçeneği ayarlandığında ve derleyici hedefi x86 veya x64 olduğunda, 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(__AVX512DQ__):::`[**`/arch:AVX512`**](../build/reference/arch-x86.md)Derleyici seçeneği ayarlandığında ve derleyici hedefi x86 veya x64 olduğunda, 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(__AVX512F__):::`[**`/arch:AVX512`**](../build/reference/arch-x86.md)Derleyici seçeneği ayarlandığında ve derleyici hedefi x86 veya x64 olduğunda, 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(__AVX512VL__):::`[**`/arch:AVX512`**](../build/reference/arch-x86.md)Derleyici seçeneği ayarlandığında ve derleyici hedefi x86 veya x64 olduğunda, 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(_CHAR_UNSIGNED):::`Varsayılan tür işaretsiz ise 1 olarak tanımlanır **`char`** . Bu değer, [ **`/J`** (varsayılan karakter türü imzasız)](../build/reference/j-default-char-type-is-unsigned.md) derleyici seçeneği ayarlandığında tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(__CLR_VER):::`Uygulamayı derlemek için kullanılan ortak dil çalışma zamanının (CLR) sürümünü temsil eden bir tamsayı sabiti olarak tanımlanır. Değer, `Mmmbbbbb` `M` çalışma zamanının ana sürümü olan, `mm` çalışma zamanının ikincil sürümüdür ve yapı numarası olduğunda, biçiminde kodlanır `bbbbb` . `:::no-loc(__CLR_VER):::`, [**`/clr`**](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği ayarlandıysa tanımlanmıştır. Aksi takdirde, tanımsız.

    ```cpp
    // clr_ver.cpp
    // compile with: /clr
    using namespace System;
    int main() {
       Console::WriteLine(:::no-loc(__CLR_VER):::);
    }
    ```

- `:::no-loc(_CONTROL_FLOW_GUARD):::`[ **`/guard:cf`** (Control Flow Guard 'ı etkinleştir)](../build/reference/guard-enable-control-flow-guard.md) derleyici seçeneği ayarlandığında 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(__COUNTER__):::`0 ' dan başlayan bir tamsayı değişmez değerine genişletilir. Değer, kaynak dosyada her kullanıldığında veya kaynak dosyanın eklenen üst bilgilerinde 1 ile artırılır. `:::no-loc(__COUNTER__):::`önceden derlenmiş üst bilgiler kullandığınızda durumunu anımsar. Bu makro her zaman tanımlanmıştır.

  Bu örnek `:::no-loc(__COUNTER__):::` , aynı türdeki üç farklı nesneye benzersiz tanımlayıcılar atamak için kullanır. `exampleClass`Oluşturucu bir parametre olarak bir tamsayı alır. ' De `main` , uygulama `exampleClass` `:::no-loc(__COUNTER__):::` benzersiz tanımlayıcı parametresi olarak kullanarak türünde üç nesne bildirir:

    ```cpp
    // macro:::no-loc(__COUNTER__):::.cpp
    // Demonstration of :::no-loc(__COUNTER__):::, assigns unique identifiers to
    // different objects of the same type.
    // Compile by using: cl /EHsc /W4 macro:::no-loc(__COUNTER__):::.cpp
    #include <stdio.h>

    class exampleClass {
        int m_nID;
    public:
        // initialize object with a read-only unique ID
        exampleClass(int nID) : m_nID(nID) {}
        int GetID(void) { return m_nID; }
    };

    int main()
    {
        // :::no-loc(__COUNTER__)::: is initially defined as 0
        exampleClass e1(:::no-loc(__COUNTER__):::);

        // On the second reference, :::no-loc(__COUNTER__)::: is now defined as 1
        exampleClass e2(:::no-loc(__COUNTER__):::);

        // :::no-loc(__COUNTER__)::: is now defined as 2
        exampleClass e3(:::no-loc(__COUNTER__):::);

        printf("e1 ID: %i\n", e1.GetID());
        printf("e2 ID: %i\n", e2.GetID());
        printf("e3 ID: %i\n", e3.GetID());

        // Output
        // ------------------------------
        // e1 ID: 0
        // e2 ID: 1
        // e3 ID: 2

        return 0;
    }
    ```

- `:::no-loc(__cplusplus_cli):::`C++ olarak derlendiğinde ve bir derleyici seçeneği ayarlandığında, tamsayı sabit değeri 200406 olarak tanımlanır [**`/clr`**](../build/reference/clr-common-language-runtime-compilation.md) . Aksi takdirde, tanımsız. Tanımlandığında, `:::no-loc(__cplusplus_cli):::` çeviri birimi boyunca geçerli olur.

    ```cpp
    // cplusplus_cli.cpp
    // compile by using /clr
    #include "stdio.h"
    int main() {
       #ifdef :::no-loc(__cplusplus_cli):::
          printf("%d\n", :::no-loc(__cplusplus_cli):::);
       #else
          printf("not defined\n");
       #endif
    }
    ```

- `:::no-loc(__cplusplus_winrt):::`C++ olarak derlendiğinde ve [ **`/ZW`** (Windows çalışma zamanı derlemesi)](../build/reference/zw-windows-runtime-compilation.md) derleyici seçeneği ayarlandığında, tamsayı sabit değeri 201009 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(_CPPRTTI):::`[ **`/GR`** (Çalışma zamanı türü bilgilerini etkinleştir)](../build/reference/gr-enable-run-time-type-information.md) derleyici seçeneği ayarlandıysa 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(_CPPUNWIND):::`Bir veya daha fazla [ **`/GX`** (özel durum işlemeyi etkinleştir)](../build/reference/gx-enable-exception-handling.md), [ **`/clr`** (ortak dil çalışma zamanı derlemesi](../build/reference/clr-common-language-runtime-compilation.md)) veya [ **`/EH`** (özel durum işleme modeli)](../build/reference/eh-exception-handling-model.md) derleyici seçenekleri ayarlandıysa 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(_DEBUG):::`[**`/LDd`**](../build/reference/md-mt-ld-use-run-time-library.md), [**`/MDd`**](../build/reference/md-mt-ld-use-run-time-library.md) Veya derleyici seçeneği ayarlandığında 1 olarak tanımlanır [**`/MTd`**](../build/reference/md-mt-ld-use-run-time-library.md) . Aksi takdirde, tanımsız.

- `:::no-loc(_DLL):::`[**`/MD`**](../build/reference/md-mt-ld-use-run-time-library.md)Or [**`/MDd`**](../build/reference/md-mt-ld-use-run-time-library.md) (çok Iş parçacıklı DLL) derleyici seçeneği ayarlandığında 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(__FUNCDNAME__):::`Kapsayan işlevin [düzenlenmiş adını](../build/reference/decorated-names.md) içeren bir dize sabit değeri olarak tanımlanır. Makro yalnızca bir işlev içinde tanımlanır. `:::no-loc(__FUNCDNAME__):::` [**`/EP`**](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) Or derleyici seçeneğini kullanırsanız makro genişletilmez [**`/P`**](../build/reference/p-preprocess-to-a-file.md) .

   Bu örnek, `:::no-loc(__FUNCDNAME__):::` `:::no-loc(__FUNCSIG__):::` `:::no-loc(__FUNCTION__):::` işlev bilgilerini göstermek için, ve makrolarını kullanır.

   [!code-cpp[NVC_Predefined_Macros_Examples#1](../preprocessor/codesnippet/CPP/predefined-macros_1.cpp)]

- `:::no-loc(__FUNCSIG__):::`Kapsayan işlevin imzasını içeren bir dize sabit değeri olarak tanımlanır. Makro yalnızca bir işlev içinde tanımlanır. `:::no-loc(__FUNCSIG__):::` [**`/EP`**](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) Or derleyici seçeneğini kullanırsanız makro genişletilmez [**`/P`**](../build/reference/p-preprocess-to-a-file.md) . 64 bitlik bir hedef için derlendiğinde, çağırma kuralı **`__cdecl`** Varsayılan olarak olur. Kullanım örneği için, `:::no-loc(__FUNCDNAME__):::` makroya bakın.

- `:::no-loc(__FUNCTION__):::`Kapsayan işlevin açıklanmıyor adını içeren bir dize sabit değeri olarak tanımlanır. Makro yalnızca bir işlev içinde tanımlanır. `:::no-loc(__FUNCTION__):::` [**`/EP`**](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) Or derleyici seçeneğini kullanırsanız makro genişletilmez [**`/P`**](../build/reference/p-preprocess-to-a-file.md) . Kullanım örneği için, `:::no-loc(__FUNCDNAME__):::` makroya bakın.

- `:::no-loc(_INTEGRAL_MAX_BITS):::`Vektör olmayan tamsayı türü için en büyük boyut olan 64 (bit cinsinden) olarak tanımlanır. Bu makro her zaman tanımlanmıştır.

   ```cpp
   // integral_max_bits.cpp
   #include <stdio.h>
   int main() {
      printf("%d\n", :::no-loc(_INTEGRAL_MAX_BITS):::);
   }
   ```

- `__INTELLISENSE__`Visual Studio IDE 'de bir IntelliSense derleyicisi geçişi sırasında 1 olarak tanımlanır. Aksi takdirde, tanımsız. IntelliSense derleyicisinin tanımadığı kodu korumak için bu makroyu kullanabilir veya yapı ile IntelliSense derleyicisi arasında geçiş yapmak için kullanabilirsiniz. Daha fazla bilgi için bkz. [IntelliSense Yavaşlılığını Için sorun giderme ipuçları](https://devblogs.microsoft.com/cppblog/troubleshooting-tips-for-intellisense-slowness/).

- `:::no-loc(_ISO_VOLATILE):::`[**`/volatile:iso`**](../build/reference/volatile-volatile-keyword-interpretation.md)Derleyici seçeneği ayarlandıysa 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(_KERNEL_MODE):::`[ **`/kernel`** (Çekirdek modu ikilisi oluştur)](../build/reference/kernel-create-kernel-mode-binary.md) derleyici seçeneği ayarlandıysa 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(_M_AMD64):::`X64 işlemcileri hedefleyen derlemeler için 100 tamsayı sabit değeri olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(_M_ARM):::`ARM işlemcilerini hedefleyen derlemeler için 7 tamsayı sabit değeri olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(_M_ARM_ARMV7VE):::`[**`/arch:ARMv7VE`**](../build/reference/arch-arm.md)Derleyici SEÇENEĞI ARM İşlemcileri hedefleyen derlemeler için ayarlandığında 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(_M_ARM_FP):::`[**`/arch`**](../build/reference/arch-arm.md)ARM işlemci hedefleri için hangi derleyici seçeneğinin ayarlandığını belirten tamsayı sabit değeri olarak tanımlanır. Aksi takdirde, tanımsız.

  - ARM **`/arch`** seçeneği belirtilmemişse, ARM için varsayılan mimariyi belirten 30-39 aralığında bir değer ( `VFPv3` ) ayarlanır.

  - Ayarlanmışsa 40-49 aralığındaki bir değer **`/arch:VFPv4`** .

  - Daha fazla bilgi için bkz. [ **`/arch`** (ARM)](../build/reference/arch-arm.md).

- `:::no-loc(_M_ARM64):::`64-bit ARM İşlemcileri hedefleyen derlemeler için 1 olarak tanımlanmıştır. Aksi takdirde, tanımsız.

- `:::no-loc(_M_CEE):::`Varsa, 001 olarak tanımlanır [ **`/clr`** (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği ayarlanır. Aksi takdirde, tanımsız.

- `:::no-loc(_M_CEE_PURE):::`Visual Studio 2015 ' de kullanım dışı bırakıldı. [**`/clr:pure`**](../build/reference/clr-common-language-runtime-compilation.md)Derleyici seçeneği ayarlandıysa 001 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(_M_CEE_SAFE):::`Visual Studio 2015 ' de kullanım dışı bırakıldı. [**`/clr:safe`**](../build/reference/clr-common-language-runtime-compilation.md)Derleyici seçeneği ayarlandıysa 001 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(_M_FP_EXCEPT):::`[**`/fp:except`**](../build/reference/fp-specify-floating-point-behavior.md)Or [**`/fp:strict`**](../build/reference/fp-specify-floating-point-behavior.md) derleyici seçeneği ayarlandıysa 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(_M_FP_FAST):::`[**`/fp:fast`**](../build/reference/fp-specify-floating-point-behavior.md)Derleyici seçeneği ayarlandıysa 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(_M_FP_PRECISE):::`[**`/fp:precise`**](../build/reference/fp-specify-floating-point-behavior.md)Derleyici seçeneği ayarlandıysa 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(_M_FP_STRICT):::`[**`/fp:strict`**](../build/reference/fp-specify-floating-point-behavior.md)Derleyici seçeneği ayarlandıysa 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(_M_IX86):::`X86 işlemcileri hedefleyen derlemeler için 600 tamsayı sabit değeri olarak tanımlanır. Bu makro x64 veya ARM derleme hedefleri için tanımlı değil.

- `:::no-loc(_M_IX86_FP):::`Ayarlanan derleyici seçeneğini veya varsayılan değeri belirten bir tamsayı sabit değeri olarak tanımlanır [**`/arch`**](../build/reference/arch-arm.md) . Bu makro, derleme hedefi bir x86 işlemcisi olduğunda her zaman tanımlanır. Aksi takdirde, tanımsız. Tanımlandığında değer şu şekilde olur:

  - `/arch:IA32`derleyici seçeneği ayarlandıysa 0.

  - `/arch:SSE`derleyici seçeneği ayarlandıysa 1.

  - `/arch:SSE2`,, `/arch:AVX` `/arch:AVX2` veya `/arch:AVX512` derleyici seçeneği ayarlandıysa 2. Bu değer, bir `/arch` derleyici seçeneği belirtilmemişse varsayılan değerdir. Belirtildiğinde `/arch:AVX` , makro `:::no-loc(__AVX__):::` da tanımlanır. Belirtildiğinde `/arch:AVX2` , her ikisi `:::no-loc(__AVX__):::` `:::no-loc(__AVX2__):::` de tanımlanır. Belirtildiğinde,,,,,, `/arch:AVX512` `:::no-loc(__AVX__):::` `:::no-loc(__AVX2__):::` `:::no-loc(__AVX512BW__):::` `:::no-loc(__AVX512CD__):::` `:::no-loc(__AVX512DQ__):::` `:::no-loc(__AVX512F__):::` ve `:::no-loc(__AVX512VL__):::` de tanımlanır.

  - Daha fazla bilgi için bkz. [ **`/arch`** (x86)](../build/reference/arch-x86.md).

- `:::no-loc(_M_X64):::`X64 işlemcileri hedefleyen derlemeler için 100 tamsayı sabit değeri olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(_MANAGED):::`[**`/clr`**](../build/reference/clr-common-language-runtime-compilation.md)Derleyici seçeneği ayarlandığında 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(_MSC_BUILD):::`Derleyicinin sürüm numarasının düzeltme numarası öğesini içeren bir tamsayı sabit değeri olarak tanımlanır. Düzeltme numarası, dönem ile ayrılmış sürüm numarasının dördüncü öğesidir. Örneğin, Microsoft C/C++ derleyicisinin sürüm numarası 15.00.20706.01 ise, `:::no-loc(_MSC_BUILD):::` makro 1 olarak değerlendirilir. Bu makro her zaman tanımlanmıştır.

- `:::no-loc(_MSC_EXTENSIONS):::`Varsayılan [ **`/Ze`** (dil uzantılarını etkinleştir)](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneği ayarlandıysa 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(_MSC_FULL_VER):::`Derleyicinin sürüm numarasının büyük, küçük ve derleme numarası öğelerini kodlayan bir tamsayı sabit değeri olarak tanımlanır. Ana sayı, dönem ile ayrılmış sürüm numarasının ilk öğesidir, küçük sayı ikinci öğedir ve yapı numarası üçüncü öğedir. Örneğin, Microsoft C/C++ derleyicisinin sürüm numarası 15.00.20706.01 ise, `:::no-loc(_MSC_FULL_VER):::` makro 150020706 olarak değerlendirilir. `cl /?`Derleyicinin sürüm numarasını görüntülemek için komut satırına yazın. Bu makro her zaman tanımlanmıştır.

- `:::no-loc(_MSC_VER):::`Derleyicinin sürüm numarasının büyük ve küçük sayı öğelerini kodlayan bir tamsayı sabit değeri olarak tanımlanır. Ana sayı, dönem ile ayrılmış sürüm numarasının ilk öğesidir ve ikincil sayı ikinci öğedir. Örneğin, Microsoft C/C++ derleyicisinin sürüm numarası 17.00.51106.1 ise, `:::no-loc(_MSC_VER):::` makro 1700 olarak değerlendirilir. `cl /?`Derleyicinin sürüm numarasını görüntülemek için komut satırına yazın. Bu makro her zaman tanımlanmıştır.

   | Visual Studio sürüm | `:::no-loc(_MSC_VER):::` |
   |--|--|
   | Visual Studio 6.0 | 1200 |
   | Visual Studio .NET 2002 (7,0) | 1300 |
   | Visual Studio .NET 2003 (7,1) | 1310 |
   | Visual Studio 2005 (8,0) | 1400 |
   | Visual Studio 2008 (9,0) | 1500 |
   | Visual Studio 2010 (10,0) | 1600 |
   | Visual Studio 2012 (11,0) | 1700 |
   | Visual Studio 2013 (12,0) | 1800 |
   | Visual Studio 2015 (14,0) | 1900 |
   | Visual Studio 2017 RTW (15,0) | 1910 |
   | Visual Studio 2017 sürüm 15.3 | 1911 |
   | Visual Studio 2017 sürüm 15.5 | 1912 |
   | Visual Studio 2017 sürüm 15.6 | 1913 |
   | Visual Studio 2017 sürüm 15.7 Sürüm Notları | 1914 |
   | Visual Studio 2017 sürüm 15,8 | 1915 |
   | Visual Studio 2017 sürüm 15,9 | 1916 |
   | Visual Studio 2019 RTW (16,0) | 1920 |
   |  Visual Studio 2019 sürüm 16.1 | 1921 |
   |  Visual Studio 2019 sürüm 16.2  | 1922 |
   | Visual Studio 2019 sürüm 16,3 | 1923 |
   |  Visual Studio 2019 sürüm 16.4 | 1924 |
   | Visual Studio 2019 sürüm 16,5 | 1925 |
   | Visual Studio 2019 sürüm 16,6 | 1926 |
   | Visual Studio 2019 sürüm 16,7 | 1927 |

   Visual Studio 'nun belirli bir sürümünde veya sonrasında derleyici sürümlerini veya güncelleştirmelerini test etmek için `>=` işlecini kullanın. Bunu, bilinen bir sürümle karşılaştırmak için koşullu bir yönergede kullanabilirsiniz `:::no-loc(_MSC_VER):::` . Karşılaştırmak için birbirini dışlayan birkaç sürümleriniz varsa, karşılaştırmaları sürüm numarası azalan sırada sıralayın. Örneğin, bu kod Visual Studio 2017 ve üzeri sürümlerde yayınlanan derleyicileri denetler. Ardından, Visual Studio 2015 ' de veya sonrasında yayınlanan derleyicileri denetler. Ardından, Visual Studio 2015 'den önce yayınlanan tüm derleyicileri denetler:

   ```cpp
   #if :::no-loc(_MSC_VER)::: >= 1910
   // . . .
   #elif :::no-loc(_MSC_VER)::: >= 1900
   // . . .
   #else
   // . . .
   #endif
   ```

   Daha fazla bilgi için bkz. Microsoft C++ ekip blogu 'nda [Visual C++ derleyici sürümü](https://devblogs.microsoft.com/cppblog/visual-c-compiler-version/) .

- `:::no-loc(_MSVC_LANG):::`Derleyicinin hedeflediği C++ dili standardını belirten bir tamsayı sabit değeri olarak tanımlanır. Yalnızca C++ olarak derlenen kodda ayarlanır. Makro varsayılan olarak 201402L tamsayı sabit değeridir veya [**`/std:c++14`**](../build/reference/std-specify-language-standard-version.md) derleyici seçeneği belirtildiğinde. Derleyici seçeneği belirtilmişse, makro 201703L olarak ayarlanır [**`/std:c++17`**](../build/reference/std-specify-language-standard-version.md) . Seçenek belirtildiğinde, daha yüksek, belirtilmemiş bir değere ayarlanır [**`/std:c++latest`**](../build/reference/std-specify-language-standard-version.md) . Aksi takdirde, makro tanımsız olur. `:::no-loc(_MSVC_LANG):::`Makro ve [ **`/std`** (dil standardı sürümü belirt)](../build/reference/std-specify-language-standard-version.md) derleyici seçenekleri Visual Studio 2015 güncelleştirme 3 ' ten başlayarak kullanılabilir.

- `:::no-loc(__MSVC_RUNTIME_CHECKS):::`Derleyici seçeneklerinden biri ayarlandığında 1 olarak tanımlanır [**`/RTC`**](../build/reference/rtc-run-time-error-checks.md) . Aksi takdirde, tanımsız.

- `_MSVC_TRADITIONAL`Önişlemci uyumluluk modu [**`/experimental:preprocessor`**](../build/reference/experimental-preprocessor.md) derleyici seçeneği ayarlandığında 0 olarak tanımlanır. [**`/experimental:preprocessor-`**](../build/reference/experimental-preprocessor.md)Geleneksel Önişlemci 'nin kullanımda olduğunu göstermek için varsayılan olarak veya derleyici seçeneği ayarlandığında 1 olarak tanımlanır. `_MSVC_TRADITIONAL`Visual Studio 2017 sürüm 15,8 ' den itibaren makro ve [ **`/experimental:preprocessor`** (Önişlemci uyumluluk modunu etkinleştir)](../build/reference/experimental-preprocessor.md) derleyici seçeneği kullanılabilir.

   ```cpp
   #if defined(_MSVC_TRADITIONAL) && _MSVC_TRADITIONAL
   // Logic using the traditional preprocessor
   #else
   // Logic using cross-platform compatible preprocessor
   #endif
   ```

- `:::no-loc(_MT):::`[ **`/MD`** Veya **`/MDd`** (çok iş parçacıklı DLL)](../build/reference/md-mt-ld-use-run-time-library.md) veya (çok [ **`/MT`** **`/MTd`** iş parçacıklı)](../build/reference/md-mt-ld-use-run-time-library.md) belirtildiğinde 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(_NATIVE_WCHAR_T_DEFINED):::`[**`/Zc:wchar_t`**](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)Derleyici seçeneği ayarlandığında 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(_OPENMP):::`[ **`/openmp`** (OpenMP 2,0 desteğini etkinleştir)](../build/reference/openmp-enable-openmp-2-0-support.md) derleyici seçeneği ayarlandıysa tamsayı sabit değeri 200203 olarak tanımlanır. Bu değer, MSVC tarafından uygulanan OpenMP belirtiminin tarihini temsil eder. Aksi takdirde, tanımsız.

   ```cpp
   // :::no-loc(_OPENMP):::_dir.cpp
   // compile with: /openmp
   #include <stdio.h>
   int main() {
      printf("%d\n", :::no-loc(_OPENMP):::);
   }
   ```

- `:::no-loc(_PREFAST_):::`[**`/analyze`**](../build/reference/analyze-code-analysis.md)Derleyici seçeneği ayarlandığında 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(__TIMESTAMP__):::`Geçerli kaynak dosyanın son değiştirilme tarihini ve saatini içeren bir dize sabit değeri olarak tanımlanır; Örneğin, CRT işlevinin döndürdüğü kısaltılmış, sabit uzunlukta form [`asctime`](../c-runtime-library/reference/asctime-wasctime.md) `Fri 19 Aug 13:32:58 2016` . Bu makro her zaman tanımlanmıştır.

- `:::no-loc(_VC_NODEFAULTLIB):::`[ **`/Zl`** (Varsayılan kitaplık adını atla)](../build/reference/zl-omit-default-library-name.md) derleyici seçeneği ayarlandığında 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(_WCHAR_T_DEFINED):::`Varsayılan [**`/Zc:wchar_t`**](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) derleyici seçeneği ayarlandığında 1 olarak tanımlanır. `:::no-loc(_WCHAR_T_DEFINED):::`Makro tanımlanmıştır, ancak **`/Zc:wchar_t-`** derleyici seçeneği ayarlandıysa bir değere sahip değildir ve **`wchar_t`** projenize dahil olan bir sistem üst bilgisi dosyasında tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(_WIN32):::`Derleme hedefi 32-bit ARM, 64-bit ARM, x86 veya x64 olduğunda 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(_WIN64):::`Derleme hedefi 64-bit ARM veya x64 olduğunda 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- `:::no-loc(_WINRT_DLL):::`C++ olarak derlendiğinde ve hem [ **`/ZW`** (Windows çalışma zamanı derlemesi)](../build/reference/zw-windows-runtime-compilation.md) hem de [ **`/LD`** ya **`/LDd`** ](../build/reference/md-mt-ld-use-run-time-library.md) da derleyici seçenekleri ayarlandığında 1 olarak tanımlanır. Aksi takdirde, tanımsız.

Derleyici tarafından önceden tanımlanmış ATL veya MFC kitaplık sürümünü tanımlayan bir ön işlemci makrosu yoktur. ATL ve MFC kitaplık üstbilgileri bu sürüm makrolarını dahili olarak tanımlar. Bunlar, gerekli üst bilgi eklenmeden önce yapılan ön işlemci yönergelerinde tanımsızdır.

- `:::no-loc(_ATL_VER):::`' De \<atldef.h> ATL sürüm numarasını kodlayan bir tamsayı sabit değeri olarak tanımlanmıştır.

- `:::no-loc(_MFC_VER):::`\<afxver_.h>MFC sürüm numarasını kodlayan bir tamsayı sabit değeri olarak tanımlanmıştır.

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar (C/C++)](../preprocessor/macros-c-cpp.md)<br/>
[Ön işlemci işleçleri](../preprocessor/preprocessor-operators.md)<br/>
[Ön işlemci yönergeleri](../preprocessor/preprocessor-directives.md)
