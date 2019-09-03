---
title: Önceden tanımlanmış makrolar
ms.custom: update_every_version
ms.date: 04/05/2019
f1_keywords:
- _ATL_VER
- __ATOM__
- __AVX__
- __AVX2__
- _CHAR_UNSIGNED
- __CLR_VER
- _CONTROL_FLOW_GUARD
- __COUNTER__
- __cplusplus
- __cplusplus_cli
- __cplusplus_winrt
- _CPPRTTI
- _CPPUNWIND
- __DATE__
- _DEBUG
- _DLL
- __FILE__
- __FUNCDNAME__
- __FUNCSIG__
- __FUNCTION__
- _INTEGRAL_MAX_BITS
- _ISO_VOLATILE
- _KERNEL_MODE
- __LINE__
- _M_AMD64
- _M_ARM
- _M_ARM_ARMV7VE
- _M_ARM_FP
- _M_ARM64
- _M_CEE
- _M_CEE_PURE
- _M_CEE_SAFE
- _M_FP_EXCEPT
- _M_FP_FAST
- _M_FP_PRECISE
- _M_FP_STRICT
- _M_IX86
- _M_IX86_FP
- _M_X64
- _MANAGED
- _MFC_VER
- _MSC_BUILD
- _MSC_EXTENSIONS
- _MSC_FULL_VER
- _MSC_VER
- _MSVC_LANG
- __MSVC_RUNTIME_CHECKS
- _MT
- _NATIVE_WCHAR_T_DEFINED
- _NO_SIZED_DEALLOCATION
- _OPENMP
- _PREFAST_
- _RESUMABLE_FUNCTIONS_SUPPORTED
- _RTC_CONVERSION_CHECKS_ENABLED
- __STDC__
- __STDC_HOSTED__
- __STDCPP_THREADS__
- __TIME__
- __TIMESTAMP__
- __VA_ARGS__
- _VC_NODEFAULTLIB
- _WCHAR_T_DEFINED
- _WIN32
- _WIN64
- _WINRT_DLL
- __func__
helpviewer_keywords:
- timestamps, preprocessor macro
- cl.exe compiler, version number
- version numbers, C/C++ compiler (cl.exe)
- macros, predefined C++
- preprocessor, macros
- predefined macros
- _ATL_VER macro
- __ATOM__ macro
- __AVX__ macro
- __AVX2__ macro
- _CHAR_UNSIGNED macro
- __CLR_VER macro
- _CONTROL_FLOW_GUARD macro
- __COUNTER__ macro
- __cplusplus macro
- __cplusplus_cli macro
- __cplusplus_winrt macro
- _CPPRTTI macro
- _CPPUNWIND macro
- __DATE__ macro
- _DEBUG macro
- _DLL macro
- __FILE__ macro
- __FUNCDNAME__ macro
- __FUNCSIG__ macro
- __FUNCTION__ macro
- _INTEGRAL_MAX_BITS macro
- _ISO_VOLATILE macro
- _KERNEL_MODE macro
- __LINE__ macro
- _M_AMD64 macro
- _M_ARM macro
- _M_ARM_ARMV7VE macro
- _M_ARM_FP macro
- _M_ARM64 macro
- _M_CEE macro
- _M_CEE_PURE macro
- _M_CEE_SAFE macro
- _M_FP_EXCEPT macro
- _M_FP_FAST macro
- _M_FP_PRECISE macro
- _M_FP_STRICT macro
- _M_IX86 macro
- _M_IX86_FP macro
- _M_X64 macro
- _MANAGED macro
- _MFC_VER macro
- _MSC_BUILD macro
- _MSC_EXTENSIONS macro
- _MSC_FULL_VER macro
- _MSC_VER macro
- _MSVC_LANG macro
- __MSVC_RUNTIME_CHECKS macro
- _MT macro
- _NATIVE_WCHAR_T_DEFINED macro
- _NO_SIZED_DEALLOCATION macro
- _OPENMP macro
- _PREFAST_ macro
- _RESUMABLE_FUNCTIONS_SUPPORTED macro
- _RTC_CONVERSION_CHECKS_ENABLED macro
- __STDC__ macro
- __STDC_HOSTED__ macro
- __STDCPP_THREADS__ macro
- __TIME__ macro
- __TIMESTAMP__ macro
- __VA_ARGS__ macro
- _VC_NODEFAULTLIB macro
- _WCHAR_T_DEFINED macro
- _WIN32 macro
- _WIN64 macro
- _WINRT_DLL macro
- __func__ identifier
ms.assetid: 1cc5f70a-a225-469c-aed0-fe766238e23f
ms.openlocfilehash: ab478cd8ac51b5cb88cec38f80541df8a7be2789
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222288"
---
# <a name="predefined-macros"></a>Önceden tanımlanmış makrolar

Microsoft C/C++ DERLEYICISI (MSVC), dile (C veya C++), derleme hedefine ve seçilen derleyici seçeneklerine bağlı olarak belirli Önişlemci makrolarını önceden tanımlar.

MSVC, ANSI/ISO C99 Standard ve ISO C++ 14 ve C++ 17 standartları için gereken önceden tanımlanmış Önişlemci makrolarını destekler. Uygulama, Microsoft 'a özgü birkaç önişlemci makrosunu da destekler. Bazı makrolar yalnızca belirli derleme ortamları veya derleyici seçenekleri için tanımlanır. Aksi belirtilmedikçe, makrolar, **/d** derleyici seçeneği bağımsız değişkenleri olarak belirtimiş gibi bir çeviri birimi boyunca tanımlanır. Tanımlandığında, makrolar derlemeden önce Önişlemci tarafından belirtilen değerlere genişletilir. Önceden tanımlanmış makrolar bağımsız değişken almaz ve yeniden tanımlanamaz.

## <a name="standard-predefined-identifier"></a>Standart önceden tanımlanmış tanımlayıcı

Derleyici ISO C99 ve ISO C++ 11 tarafından belirtilen önceden tanımlanmış tanımlayıcıyı destekler.

- **&#95; Func &#95; &#95;** İşlevin yerel **statik sabit** dizisi olarak, kapsayan işlevin nitelenmemiş ve donatımış adı.

    ```cpp
    void example(){
        printf("%s\n", __func__);
    } // prints "example"
    ```

## <a name="standard-predefined-macros"></a>Standart önceden tanımlanmış makrolar

Derleyici ISO C99 ve ISO C++ 17 standartları tarafından belirtilen önceden tanımlanmış makroları destekler.

- **&#95; &#95;** Çeviri birimi olarak C++derlendiğinde tamsayı sabit değeri olarak tanımlanır. Aksi takdirde, tanımsız.

- **&#95; Tarih &#95; &#95;** Geçerli kaynak dosyanın derleme tarihi. Tarih, *aaa gg yyyy*biçiminde sabit uzunluklu bir dize sabit değeri olur. Ay adı *aaa* , C çalışma zamanı KITAPLıĞı (CRT) [asctime](../c-runtime-library/reference/asctime-wasctime.md) işlevi tarafından oluşturulan kısaltılmış ay adı ile aynıdır. Değer 10 ' dan küçükse, *gg* 'nin ilk karakteri bir alandır. Bu makro her zaman tanımlanmıştır.

- **&#95; Dosya &#95; &#95;** Geçerli kaynak dosyanın adı. Dosya, bir karakter dizesi değişmez değerine genişletilir. **&#95; &#95;&#95;** Dosyanın tam yolunun görüntülendiğinden emin olmak için [/FC (kaynak kodu dosyasının Tanılamadaki Tam yolu)](../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md)kullanın. Bu makro her zaman tanımlanmıştır.

- **&#95; Satır &#95; &#95;** Geçerli kaynak dosyasında tamsayı satır numarası olarak tanımlanır. Çizgi makrosunun değeri bir **&#95; &#95;yönerge kullanılarak değiştirilebilir.&#95;** `#line` Bu makro her zaman tanımlanmıştır.

- **&#95;&#95; Stdc &#95;** Yalnızca C olarak derlendiğinde ve [/za](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneği belirtilmişse 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- **&#95;&#95;&#95;&#95;**  Uygulama *barındırılan bir uygulama*ise ve tüm gerekli standart kitaplığı destekleyen, 1 olarak barındırılan stdc. Aksi takdirde, 0 olarak tanımlanır.

- **&#95;&#95;&#95;&#95;**  Yalnızca bir programın birden fazla yürütme iş parçacığı ve olarak C++derlenmesi halinde olması halinde, ve yalnızca bir program tarafından 1 olarak tanımlanan stdcpp iş parçacıkları. Aksi takdirde, tanımsız.

- **&#95; Zaman &#95; &#95;** Önceden işlenmiş çeviri biriminin çevirisi süresi. Bu zaman, *HH: mm: ss*biçimindeki bir karakter dizesi değişmez DEĞERI, CRT [asctime](../c-runtime-library/reference/asctime-wasctime.md) işlevi tarafından döndürülen zaman ile aynıdır. Bu makro her zaman tanımlanmıştır.

## <a name="microsoft-specific-predefined-macros"></a>Microsoft 'a özgü önceden tanımlanmış makrolar

MSVC bu önceden tanımlanmış ek makroları destekler.

- **&#95; Atom &#95; &#95;** [/İyileştir: Atom](../build/reference/favor-optimize-for-architecture-specifics.md) derleyicisi seçeneği ayarlandığında ve derleyici hedefi x86 veya x64 olduğunda 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- **&#95;&#95; AVX &#95;** [/Arch: AVX](../build/reference/arch-x86.md) veya [/Arch: AVX2](../build/reference/arch-x86.md) derleyici seçenekleri ayarlandığında ve derleyici hedefi x86 veya x64 olduğunda, 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- **&#95; AVX2 &#95; &#95;** [/Arch: AVX2](../build/reference/arch-x86.md) derleyici seçeneği ayarlandığında ve derleyici hedefi x86 veya x64 olduğunda, 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- **&#95;Varsayılan&#95;** **char** türü işaretsiz ise, Char işaretsiz olarak 1 olarak tanımlanır. [/J (varsayılan karakter türü işaretsiz)](../build/reference/j-default-char-type-is-unsigned.md) derleyici seçeneği ayarlandığında bu değer tanımlanmıştır. Aksi takdirde, tanımsız.

- **&#95;clr ver &#95;&#95;** Uygulamayı derlemek için kullanılan ortak dil çalışma zamanının (CLR) sürümünü temsil eden bir tamsayı sabiti olarak tanımlanır. `Mmmbbbbb`Değer, çalışma zamanının `M` `mm` ana sürümü olan, çalışma zamanının ikincil sürümüdür ve `bbbbb` yapı numarası olduğunda, biçiminde kodlanır. **&#95;&#95;&#95;** [/Clr](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği ayarlandıysa clr ver tanımlanmıştır. Aksi takdirde, tanımsız.

    ```cpp
    // clr_ver.cpp
    // compile with: /clr
    using namespace System;
    int main() {
       Console::WriteLine(__CLR_VER);
    }
    ```

- **&#95;&#95;&#95;** [/Guard: CF (denetim akışı korumasını ETKINLEŞTIR)](../build/reference/guard-enable-control-flow-guard.md) derleyici seçeneği ayarlandığında, denetim akışı koruyucusu 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- **&#95; Sayaç &#95; &#95;** 0 ' dan başlayan bir tamsayı değişmez değerine genişletilir. Değer, kaynak dosyada her kullanıldığında veya kaynak dosyanın eklenen üst bilgilerinde 1 ile artırılır. Önceden derlenmiş üst bilgiler kullandığınızda **&#95; sayaç, durumunu anımsar. &#95; &#95;** Bu makro her zaman tanımlanmıştır.

  Bu örnek, `__COUNTER__` aynı türdeki üç farklı nesneye benzersiz tanımlayıcılar atamak için kullanır. `exampleClass` Oluşturucu bir parametre olarak bir tamsayı alır. ' `main`De, uygulama benzersiz tanımlayıcı parametresi olarak kullanarak `exampleClass` `__COUNTER__` türünde üç nesne bildirir:

    ```cpp
    // macro__COUNTER__.cpp
    // Demonstration of __COUNTER__, assigns unique identifiers to
    // different objects of the same type.
    // Compile by using: cl /EHsc /W4 macro__COUNTER__.cpp
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
        // __COUNTER__ is initially defined as 0
        exampleClass e1(__COUNTER__);

        // On the second reference, __COUNTER__ is now defined as 1
        exampleClass e2(__COUNTER__);

        // __COUNTER__ is now defined as 2
        exampleClass e3(__COUNTER__);

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

- **&#95;&#95;&#95;** bir/clr derleyici seçeneği ayarlandığında, bir tamsayı sabit değeri olarak tanımlanan CPlusPlus CLI 200406. [](../build/reference/clr-common-language-runtime-compilation.md) C++ Aksi takdirde, tanımsız. Tanımlandığında,  **&#95; &#95;CPlusPlus&#95;CLI** , çeviri birimi boyunca geçerli olur.

    ```cpp
    // cplusplus_cli.cpp
    // compile by using /clr
    #include "stdio.h"
    int main() {
       #ifdef __cplusplus_cli
          printf("%d\n", __cplusplus_cli);
       #else
          printf("not defined\n");
       #endif
    }
    ```

- **&#95;&#95;&#95;** olarak C++ derlendiğinde ve [/ZW (Windows çalışma zamanı derlemesi)](../build/reference/zw-windows-runtime-compilation.md) derleyici seçeneği ayarlandığında, CPlusPlus WinRT, tamsayı sabit değeri 201009 olarak tanımlandı. Aksi takdirde, tanımsız.

- **&#95;Cpprttı** [/Gr (çalışma zamanı türü bilgilerini etkinleştir)](../build/reference/gr-enable-run-time-type-information.md) derleyici seçeneği ayarlandıysa 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- **&#95;Cppaçılım** Bir veya daha fazla [/GX (özel durum Işlemeyi etkinleştir)](../build/reference/gx-enable-exception-handling.md), [/clr (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md)veya [/Eh (özel durum işleme modeli](../build/reference/eh-exception-handling-model.md) ) derleyici seçenekleri ayarlanmışsa 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- **&#95;Hata ayıkla** [/LDD](../build/reference/md-mt-ld-use-run-time-library.md), [/MDD](../build/reference/md-mt-ld-use-run-time-library.md)veya [/MTD](../build/reference/md-mt-ld-use-run-time-library.md) derleyici seçeneği ayarlandığında 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- [/Md](../build/reference/md-mt-ld-use-run-time-library.md) veya [/MDD](../build/reference/md-mt-ld-use-run-time-library.md) (çok iş parçacıklı DLL) derleyici seçeneği ayarlandığında 1 olarak tanımlanan dll.  **&#95;** Aksi takdirde, tanımsız.

- **&#95;Funcdname &#95;&#95;** Kapsayan işlevin [düzenlenmiş adını](../build/reference/decorated-names.md) içeren bir dize sabit değeri olarak tanımlanır. Makro yalnızca bir işlev içinde tanımlanır. /EP veya [/p](../build/reference/p-preprocess-to-a-file.md) derleyici seçeneğini kullanırsanız [](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)  **&#95;funcdname&#95; makrosu genişletilmez &#95;** .

   Bu örnek, işlev `__FUNCDNAME__`bilgilerini `__FUNCSIG__`göstermek için `__FUNCTION__` , ve makrolarını kullanır.

   [!code-cpp[NVC_Predefined_Macros_Examples#1](../preprocessor/codesnippet/CPP/predefined-macros_1.cpp)]

- **&#95;&#95; Funcsig &#95;** Kapsayan işlevin imzasını içeren bir dize sabit değeri olarak tanımlanır. Makro yalnızca bir işlev içinde tanımlanır. [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) veya [/p](../build/reference/p-preprocess-to-a-file.md) derleyici seçeneğini kullanırsanız,  **&#95; &#95;&#95; funcsig** makrosu genişletilmez. 64 bitlik bir hedef için derlendiğinde, çağırma kuralı varsayılan olarak olur `__cdecl` . Kullanım örneği için, `__FUNCDNAME__` makroya bakın.

- **&#95; İşlev &#95; &#95;** Kapsayan işlevin açıklanmıyor adını içeren bir dize sabit değeri olarak tanımlanır. Makro yalnızca bir işlev içinde tanımlanır. /EP veya [/p](../build/reference/p-preprocess-to-a-file.md) derleyici seçeneğini kullanırsanız [](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)  **&#95;işlev&#95; makrosu genişletilmez &#95;** . Kullanım örneği için, `__FUNCDNAME__` makroya bakın.

- **Integral&#95;en&#95;büyük bit &#95;** Vektör olmayan tamsayı türü için en büyük boyut olan 64 (bit cinsinden) olarak tanımlanır. Bu makro her zaman tanımlanmıştır.

   ```cpp
   // integral_max_bits.cpp
   #include <stdio.h>
   int main() {
      printf("%d\n", _INTEGRAL_MAX_BITS);
   }
   ```

- **&#95; IntelliSense &#95; &#95;** Visual Studio IDE 'de bir IntelliSense derleyicisi geçişi sırasında 1 olarak tanımlanır. Aksi takdirde, tanımsız. IntelliSense derleyicisinin tanımadığı kodu korumak için bu makroyu kullanabilir veya yapı ile IntelliSense derleyicisi arasında geçiş yapmak için kullanabilirsiniz. Daha fazla bilgi için bkz. [IntelliSense Yavaşlılığını Için sorun giderme ipuçları](https://devblogs.microsoft.com/cppblog/troubleshooting-tips-for-intellisense-slowness/).

- **&#95;,&#95;** [/Volatile: iso](../build/reference/volatile-volatile-keyword-interpretation.md) derleyici seçeneği ayarlandıysa, ISO geçici olarak 1 olarak tanımlanmıştır. Aksi takdirde, tanımsız.

- **&#95;&#95;** [/Kernel (çekirdek modu ikilisi oluştur)](../build/reference/kernel-create-kernel-mode-binary.md) derleyici seçeneği ayarlandıysa, çekirdek modu 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- **&#95;A&#95;AMD64** X64 işlemcileri hedefleyen derlemeler için 100 tamsayı sabit değeri olarak tanımlanır. Aksi takdirde, tanımsız.

- **&#95;d&#95;ARM** ARM işlemcilerini hedefleyen derlemeler için 7 tamsayı sabit değeri olarak tanımlanır. Aksi takdirde, tanımsız.

- **&#95;P&#95;ARM&#95;ARMV7VE** , ARM İşlemcileri hedef derlemeler için [/Arch: ARMV7VE](../build/reference/arch-arm.md) derleyici seçeneği ayarlandığında 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- **&#95;ARM&#95;işlemci&#95;** hedefleri için hangi [/Arch](../build/reference/arch-arm.md) derleyici seçeneğinin ayarlandığını gösteren bir tamsayı sabit değeri olarak tanımlanan, a ARM FP. Aksi takdirde, tanımsız.

  - ARM seçeneği belirtilmemişse, ARM için varsayılan mimariyi `/arch` belirten 30-39 aralığında bir değer (`VFPv3`) ayarlanır.

  - Ayarlanmışsa 40-49 `/arch:VFPv4` aralığındaki bir değer.

  - Daha fazla bilgi için bkz. [/Arch (ARM)](../build/reference/arch-arm.md).

- **&#95;A&#95;ARM64** 64-bit ARM İşlemcileri hedefleyen derlemeler için 1 olarak tanımlanmıştır. Aksi takdirde, tanımsız.

- **&#95;Herhangi&#95;** bir [/clr (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği ayarlandıysa, M Cee, 001 olarak tanımlanır. Aksi takdirde, tanımsız.

- **M&#95;Cee&#95;saf &#95;** Visual Studio 2015 ' de kullanım dışı bırakıldı. [/Clr: Pure](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği ayarlandıysa 001 olarak tanımlanır. Aksi takdirde, tanımsız.

- **M&#95;Cee&#95;güvenli &#95;** Visual Studio 2015 ' de kullanım dışı bırakıldı. [/Clr: Safe](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği ayarlandıysa, 001 olarak tanımlanır. Aksi takdirde, tanımsız.

- **&#95;&#95;/FP: except veya/FP: Strict derleyici seçeneği ayarlandıysa, 1 olarak&#95;** tanımlanır. [](../build/reference/fp-specify-floating-point-behavior.md) [](../build/reference/fp-specify-floating-point-behavior.md) Aksi takdirde, tanımsız.

- **&#95;/FP&#95;: Fast derleyici seçeneği ayarlandıysa, 1 olarak hızlı bir şekilde tanımlanır.&#95;** [](../build/reference/fp-specify-floating-point-behavior.md) Aksi takdirde, tanımsız.

- **&#95;&#95;&#95;** [/FP: kesin](../build/reference/fp-specify-floating-point-behavior.md) derleyici seçeneği ayarlandıysa, 5 FP kesin olarak 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- **&#95;5&#95;FP: Strict derleyici seçeneği ayarlandıysa, 1 olarak&#95;** tanımlanır. [](../build/reference/fp-specify-floating-point-behavior.md) Aksi takdirde, tanımsız.

- **&#95;A&#95;IX86** X86 işlemcileri hedefleyen derlemeler için 600 tamsayı sabit değeri olarak tanımlanır. Bu makro x64 veya ARM derleme hedefleri için tanımlı değil.

- **&#95;A&#95;IX86&#95;FP** , ayarlanan [/Arch](../build/reference/arch-arm.md) derleyici seçeneğini veya varsayılan değeri belirten bir tamsayı sabit değeri olarak tanımlanır. Bu makro, derleme hedefi bir x86 işlemcisi olduğunda her zaman tanımlanır. Aksi takdirde, tanımsız. Tanımlandığında değer şu şekilde olur:

  - `/arch:IA32` derleyici seçeneği ayarlandıysa 0.

  - `/arch:SSE` derleyici seçeneği ayarlandıysa 1.

  - `/arch:SSE2`, ,`/arch:AVX` veya`/arch:AVX2` derleyici seçeneği ayarlandıysa 2. Bu değer, bir `/arch` derleyici seçeneği belirtilmemişse varsayılan değerdir. Belirtildiğinde, **&#95; &#95;AVX&#95;** makrosu da tanımlanmıştır. `/arch:AVX` Belirtildiğinde, **&#95;hem &#95;AVX&#95;** hem **&#95; de AVX2 de tanımlanmıştır. &#95; &#95;** `/arch:AVX2`

  - Daha fazla bilgi için bkz. [/Arch (x86)](../build/reference/arch-x86.md).

- **&#95;D&#95;x64** X64 işlemcileri hedefleyen derlemeler için 100 tamsayı sabit değeri olarak tanımlanır. Aksi takdirde, tanımsız.

- **&#95;Yönetilen** [/Clr](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği ayarlandığında 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- **&#95;msc&#95;derlemesi** Derleyicinin sürüm numarasının düzeltme numarası öğesini içeren bir tamsayı sabit değeri olarak tanımlanır. Düzeltme numarası, dönem ile ayrılmış sürüm numarasının dördüncü öğesidir. Örneğin, Microsoft C/C++ derleyicisinin sürüm numarası 15.00.20706.01 ise,  **&#95;msc&#95;derleme** makrosu 1 olarak değerlendirilir. Bu makro her zaman tanımlanmıştır.

- **&#95;Varsayılan&#95;** [/Ze (dil uzantılarını etkinleştir)](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneği AYARLANDıYSA, 1 olarak tanımlanan msc uzantıları. Aksi takdirde, tanımsız.

- **msc&#95;tam&#95;ver &#95;** Derleyicinin sürüm numarasının büyük, küçük ve derleme numarası öğelerini kodlayan bir tamsayı sabit değeri olarak tanımlanır. Ana sayı, dönem ile ayrılmış sürüm numarasının ilk öğesidir, küçük sayı ikinci öğedir ve yapı numarası üçüncü öğedir. Örneğin, MicrosoftC++ C/derleyicisinin sürüm numarası 15.00.20706.01 ise,  **&#95;msc&#95;tam&#95;ver** makrosu 150020706 olarak değerlendirilir. Derleyicinin `cl /?` sürüm numarasını görüntülemek için komut satırına yazın. Bu makro her zaman tanımlanmıştır.

- **&#95;msc&#95;ver** Derleyicinin sürüm numarasının büyük ve küçük sayı öğelerini kodlayan bir tamsayı sabit değeri olarak tanımlanır. Ana sayı, dönem ile ayrılmış sürüm numarasının ilk öğesidir ve ikincil sayı ikinci öğedir. Örneğin, Microsoft C/C++ derleyicisinin sürüm numarası 17.00.51106.1 ise,  **&#95;msc&#95;ver** makrosu 1700 olarak değerlendirilir. Derleyicinin `cl /?` sürüm numarasını görüntülemek için komut satırına yazın. Bu makro her zaman tanımlanmıştır.

   |Visual Studio sürüm|**&#95;MSC&#95;VER**|
   |-|-|
   |Visual Studio 6.0|1200|
   |Visual Studio .NET 2002 (7,0)|1300|
   |Visual Studio .NET 2003 (7,1)|1310|
   |Visual Studio 2005 (8,0)|1400|
   |Visual Studio 2008 (9,0)|1500|
   |Visual Studio 2010 (10,0)|1600|
   |Visual Studio 2012 (11,0)|1700|
   |Visual Studio 2013 (12,0)|1800|
   |Visual Studio 2015 (14,0)|1900|
   |Visual Studio 2017 RTW (15,0)|1910|
   |Visual Studio 2017 sürüm 15,3|1911|
   |Visual Studio 2017 sürüm 15.5|1912|
   |Visual Studio 2017 sürüm 15.6|1913|
   |Visual Studio 2017 sürüm 15,7|1914|
   |Visual Studio 2017 sürüm 15,8|1915|
   |Visual Studio 2017 sürüm 15,9|1916|
   |Visual Studio 2019 RTW (16,0)|1920|
   |Visual Studio 2019 sürüm 16,1|1921|
   |Visual Studio 2019 sürüm 16,2|1922|
   |Visual Studio 2019 sürüm 16,3|1923|

   Visual Studio 'nun belirli bir sürümünde veya sonrasında derleyici sürümlerini veya güncelleştirmelerini test etmek için **>=** işlecini kullanın. Bu sürümü, bu bilinen sürüme karşı  **&#95;msc&#95;** sürümünü karşılaştırmak için koşullu bir yönerge içinde kullanabilirsiniz. Karşılaştırmak için birbirini dışlayan birkaç sürümleriniz varsa, karşılaştırmaları sürüm numarası azalan sırada sıralayın. Örneğin, bu kod Visual Studio 2017 ve üzeri sürümlerde yayınlanan derleyicileri denetler. Ardından, Visual Studio 2015 ' de veya sonrasında yayınlanan derleyicileri denetler. Ardından, Visual Studio 2015 'den önce yayınlanan tüm derleyicileri denetler:

   ```cpp
   #if _MSC_VER >= 1910
   // . . .
   #elif _MSC_VER >= 1900
   // . . .
   #else
   // . . .
   #endif
   ```

   Daha fazla bilgi için bkz. Microsoft C++ ekibi blogu 'ndaki [Visual C++ derleyicisi sürümü](https://devblogs.microsoft.com/cppblog/visual-c-compiler-version/) .

- **&#95;Derleyicinin&#95;** hedeflediği C++ dil standardını belirten BIR tamsayı sabiti olarak tanımlanan MSVC lang. Yalnızca olarak C++derlenen kodda ayarlanır. Makro varsayılan olarak 201402L tamsayı sabit değeridir veya [/std: c++ 14](../build/reference/std-specify-language-standard-version.md) derleyici seçeneği belirtildiğinde. [/Std: c++ 17](../build/reference/std-specify-language-standard-version.md) derleyici seçeneği belirtilmişse, makro 201703L olarak ayarlanır. [/Std: c + + latest](../build/reference/std-specify-language-standard-version.md) seçeneği belirtildiğinde, daha yüksek, belirtilmeyen bir değere ayarlanır. Aksi takdirde, makro tanımsız olur. **&#95;MSVC&#95;lang** makrosu ve [/std (dil standardı sürümü belirt)](../build/reference/std-specify-language-standard-version.md) derleyici seçenekleri Visual Studio 2015 güncelleştirme 3 ' ten başlayarak kullanılabilir.

- **&#95;&#95;MSVC&#95;çalışma&#95;zamanı denetimleri** , [/RTC](../build/reference/rtc-run-time-error-checks.md) derleyici seçeneklerinden biri ayarlandığında 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- **&#95;MT** [/Md veya/MDd](../build/reference/md-mt-ld-use-run-time-library.md) (çok Iş parçacıklı DLL) veya [/MT ya da/MTD](../build/reference/md-mt-ld-use-run-time-library.md) (çok iş parçacıklı) belirtildiğinde 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- **&#95;Yerel&#95;wchar&#95;T&#95;** , [/Zc: wchar_t](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) derleyici seçeneği ayarlandığında 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- **&#95;OPENMP** [/OpenMP (openmp 2,0 desteğini etkinleştir)](../build/reference/openmp-enable-openmp-2-0-support.md) derleyici seçeneği ayarlandıysa tamsayı sabit değeri 200203 olarak tanımlanır. Bu değer, MSVC tarafından uygulanan OpenMP belirtiminin tarihini temsil eder. Aksi takdirde, tanımsız.

   ```cpp
   // _OPENMP_dir.cpp
   // compile with: /openmp
   #include <stdio.h>
   int main() {
      printf("%d\n", _OPENMP);
   }
   ```

- **&#95;PREfast&#95;** [/Analyze](../build/reference/analyze-code-analysis.md) derleyici seçeneği ayarlandığında 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- **&#95;&#95; Zaman &#95;damgası** Geçerli kaynak dosyanın son değiştirilme tarihini ve saatini içeren bir dize sabit değeri olarak tanımlanır; Örneğin, `Fri 19 Aug 13:32:58 2016`CRT [asctime](../c-runtime-library/reference/asctime-wasctime.md) işlevi tarafından döndürülen kısaltılmış, sabit uzunlukta form. Bu makro her zaman tanımlanmıştır.

- **&#95;Bir&#95;** [/zl (varsayılan kitaplık adını atla)](../build/reference/zl-omit-default-library-name.md) derleyici seçeneği ayarlandığında, VC nodefaultlib 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- **&#95;WCHAR&#95;T&#95;** varsayılan [/Zc: wchar_t](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) derleyici seçeneği ayarlandığında 1 olarak tanımlanır. `/Zc:wchar_t-` **Wchar&#95;&#95;T tanımlı makro tanımlanmış, ancak derleyici seçeneği ayarlandıysa ve wchar_t, projenize dahil olan bir sistem üst bilgisi dosyasında tanımlıysa bir değere sahip &#95;** değildir. Aksi takdirde, tanımsız.

- **&#95;WIN32** Derleme hedefi 32-bit ARM, 64-bit ARM, x86 veya x64 olduğunda 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- **&#95;WIN64** Derleme hedefi 64-bit ARM veya x64 olduğunda 1 olarak tanımlanır. Aksi takdirde, tanımsız.

- **&#95;Olarak&#95;** C++ derlendiğinde ve her ikisi de [/ZW (Windows çalışma zamanı derlemesi)](../build/reference/zw-windows-runtime-compilation.md) ve [/ld ya da/LDD](../build/reference/md-mt-ld-use-run-time-library.md) derleyici seçenekleri ayarlandığında, WINRT dll 'si 1 olarak tanımlanır. Aksi takdirde, tanımsız.

Derleyici tarafından önceden tanımlanmış ATL veya MFC kitaplık sürümünü tanımlayan bir ön işlemci makrosu yoktur. ATL ve MFC kitaplık üstbilgileri bu sürüm makrolarını dahili olarak tanımlar. Bunlar, gerekli üst bilgi eklenmeden önce yapılan ön işlemci yönergelerinde tanımsızdır.

- **&#95;&#95;** Atldef. \<h içinde tanımlanan ATL ver, ATL sürüm numarasını kodlayan bir tamsayı sabit değeri olarak >.

- **&#95;MFC&#95;** sürüm numarasını kodlayan bir tamsayı sabit değeri olarak afxver_. h içinde \<tanımlanan MFC ver >.

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar (C/C++)](../preprocessor/macros-c-cpp.md)<br/>
[Önişlemci işleçleri](../preprocessor/preprocessor-operators.md)<br/>
[Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md)