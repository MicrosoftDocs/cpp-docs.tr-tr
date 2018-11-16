---
title: Önceden Tanımlı Makrolar
ms.custom: update_every_version
ms.date: 11/12/2018
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
ms.openlocfilehash: 9ebc23545817de0f249185700454237c66610c13
ms.sourcegitcommit: d441305fb19131afbd7fc259d8cda63ea26f2343
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51678360"
---
# <a name="predefined-macros"></a>Önceden Tanımlı Makrolar

Visual C++ derleyicisi dili (C veya C++), derleme hedefi ve seçilen derleyici seçeneklerine bağlı olarak belirli Önişlemci makroları önceden belirler.

Visual C++ ANSI/ISO C99 standardında ve ISO C ++ 14 standart tarafından belirtilen gerekli önceden tanımlanmış Önişlemci makroları destekler. Uygulama, birden çok daha fazla Microsoft'a özgü Önişlemci makroları da destekler. Bazı makrolar, yalnızca belirli bir yapı ortamları veya derleyici seçenekleri için tanımlanır. Sanki olarak belirtikleri belirtilmediği sürece, makroları çeviri biriminin tamamında tanımlanan **/D** derleyici seçeneği bağımsız değişkenler. Tanımlandığında, makrolar önişlemci önce derleme tarafından belirtilen değerleri için genişletilir. Önceden tanımlanmış makrolar bağımsız değişken almaz ve yeniden tanımlanamaz.

## <a name="standard-predefined-identifier"></a>Önceden tanımlanmış standart tanımlayıcı

Derleyici ISO C ++ 11 ISO C99 ile belirtilen önceden tanımlanmış bu tanımlayıcıyı destekler.

- **&#95;&#95;FUNC&#95; &#95;**  işlevi yerel olarak çevreleyen işlevin nitelenmemiş ve eksiz adını **statik const** dizisi **char**.

    ```cpp
    void example(){
        printf("%s\n", __func__);
    } // prints "example"
    ```

## <a name="standard-predefined-macros"></a>Standart önceden tanımlanmış makrolar

Derleyicinin, belirtilen ISO C99 ve ISO C ++ 17 standartlarına göre bu önceden tanımlanmış makrolar destekler.

- **&#95;&#95;cplusplus** çeviri birimi C++ derlendiğinde bir tamsayı sabit değeri tanımlanmış. Aksi takdirde, tanımlı değil.

- **&#95;&#95;Tarih&#95; &#95;**  geçerli kaynak dosyanın derleme tarihi. Tarihtir sabit uzunluğunda bir dize sabit değeri form *dd Mmm yyyy*. Ay adı *Mmm* kısaltılmış ay adı C çalışma zamanı kitaplığı tarafından oluşturulan tarihler aynıdır [asctime](../c-runtime-library/reference/asctime-wasctime.md) işlevi. Tarih ilk karakteri *GG* değer 10'dan az ise bir alandır. Bu makro, her zaman tanımlanır.

- **&#95;&#95;Dosya&#95; &#95;**  geçerli kaynak dosyanın adı. **&#95;&#95;Dosya&#95; &#95;**  bir karakter dize sabit değeri genişletir. Dosyanın tam yolunu görüntülendiğinden emin olmak için kullanın [/FC (tam yol, kaynak kodu dosyasında tanılama)](../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md). Bu makro, her zaman tanımlanır.

- **&#95;&#95;Satır&#95; &#95;**  geçerli kaynak dosyadaki satır tamsayı olarak tanımlanır. Değerini **&#95; &#95;satırı&#95; &#95;** makrosu kullanılarak değiştirilebilir bir `#line` yönergesi. Bu makro, her zaman tanımlanır.

- **&#95;&#95;STDC&#95; &#95;**  yalnızca C derlendiğinde ve 1 tanımlanan [/Za](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneği belirtildi. Aksi takdirde, tanımlı değil.

- **&#95;&#95;STDC&#95;BARINDIRILAN&#95; &#95;**  uygulaması ise 1 tanımlanan bir *uygulama barındırılan*, gerekli tüm standart kitaplığı destekleyen bir. Aksi durumda 0 tanımlanır.

- **&#95;&#95;STDCPP&#95;iş PARÇACIKLARI&#95; &#95;**  bir program yürütme birden fazla iş parçacığı sahip olabilir ve yalnızca, 1 tanımlanmış ve C++ derlenir. Aksi takdirde, tanımlı değil.

- **&#95;&#95;ZAMAN&#95; &#95;**  önceden işlenmiş çeviri birimi saati. Zaman bir karakter dizesidir değişmez değer formun *SS*, C çalışma zamanı kitaplığı tarafından döndürülen zaman aynı [asctime](../c-runtime-library/reference/asctime-wasctime.md) işlevi. Bu makro, her zaman tanımlanır.

## <a name="microsoft-specific-predefined-macros"></a>Microsoft'a özgü önceden tanımlı makrolar

Microsoft Visual C++ bu ek önceden tanımlı makrolar destekler.

- **&#95;&#95;ATOM&#95; &#95;**  1 olduğunda tanımlanan [/favor:ATOM](../build/reference/favor-optimize-for-architecture-specifics.md) derleyici seçeneği ayarlanır ve x86 veya x64 derleyici hedefidir. Aksi takdirde, tanımlı değil.

- **&#95;&#95;AVX&#95; &#95;**  1 olduğunda tanımlanan [/arch:](../build/reference/arch-x86.md) veya [/arch:AVX2](../build/reference/arch-x86.md) derleyici seçeneklerini ayarlayın ve x86 veya x64 derleyici hedefidir. Aksi takdirde, tanımlı değil.

- **&#95;&#95;AVX2&#95; &#95;**  1 olduğunda tanımlanan [/arch:AVX2](../build/reference/arch-x86.md) derleyici seçeneği ayarlanır ve x86 veya x64 derleyici hedefidir. Aksi takdirde, tanımlı değil.

- **&#95;CHAR&#95;İMZASIZ** varsayılan 1 ise tanımlı **char** türü imzalanmamış. Bu ne zaman ayarlanır [/J (varsayılan karakter türü imzasız)](../build/reference/j-default-char-type-is-unsigned.md) derleyici seçeneği ayarlanır. Aksi takdirde, tanımlı değil.

- **&#95;&#95;CLR&#95;VER** tanımlanan uygulama derlendiğinde kullanılan ortak dil çalışma zamanı sürümünü temsil eden bir tamsayı değişmez. Değer biçiminde kodlanır `Mmmbbbbb`burada `M` çalışma zamanının ana sürümüdür `mm` alt çalışma zamanı sürümü ve `bbbbb` yapı numarasıdır. **&#95;&#95;CLR&#95;VER** ise tanımlanabilir [/CLR](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği ayarlanır. Aksi takdirde, tanımlı değil.

    ```cpp
    // clr_ver.cpp
    // compile with: /clr
    using namespace System;
    int main() {
       Console::WriteLine(__CLR_VER);
    }
    ```

- **&#95;Denetim&#95;akış&#95;KORUYUCU** 1 olduğunda tanımlanan [/Guard: cf (etkinleştirme denetim akışı koruyucu)](../build/reference/guard-enable-control-flow-guard.md) derleyici seçeneği ayarlanır. Aksi takdirde, tanımlı değil.

- **&#95;&#95;Sayaç&#95; &#95;**  tamsayı sabit değeri 0'da başlar ve kaynak dosyada kullanılan her zaman 1 artırılır ya da kaynak dosyasının üstbilgileri dahil genişler. **&#95;&#95;Sayaç&#95; &#95;**  önceden derlenmiş üstbilgiler kullandığınızda durumunu hatırlar. Bu makro, her zaman tanımlanır.

  Bu örnekte `__COUNTER__` benzersiz tanımlayıcıları aynı türden üç farklı nesnelere atamak için. `exampleClass` Oluşturucusu bir parametre olarak bir tamsayı olarak alır. İçinde `main`, uygulama türünde üç nesne bildirir `exampleClass`kullanarak `__COUNTER__` benzersiz tanımlayıcı parametresi olarak:

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

- **&#95;&#95;cplusplus&#95;CLI** tamsayı değişmez değer C++ derlendiğinde 200406 olarak tanımlanır ve [/CLR](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği ayarlanır. Aksi takdirde, tanımlı değil. Tanımlandığında  **&#95; &#95;cplusplus&#95;CLI** çeviri biriminin tamamında etkili olduğu.

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

- **&#95;&#95;cplusplus&#95;winrt** tamsayı değişmez değer C++ derlendiğinde 201009 olarak tanımlanır ve [/ZW (Windows çalışma zamanı derlemesi)](../build/reference/zw-windows-runtime-compilation.md) derleyici seçeneği ayarlanır. Aksi takdirde, tanımlı değil.

- **&#95;CPPRTTI** 1 ise tanımlanan [/GR (çalışma zamanı türü bilgileri etkinleştir)](../build/reference/gr-enable-run-time-type-information.md) derleyici seçeneği ayarlanır. Aksi takdirde, tanımlı değil.

- **&#95;CPPUNWIND** bir veya daha fazla ise 1 tanımlanan [/GX (özel durum işlemeyi etkinleştir)](../build/reference/gx-enable-exception-handling.md), [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md), veya [/EH (özel durum işleme modeli)](../build/reference/eh-exception-handling-model.md) derleyici seçeneklerini ayarlayın. Aksi takdirde, tanımlı değil.

- **&#95;Hata ayıklama** 1 olduğunda tanımlanan [/LDd](../build/reference/md-mt-ld-use-run-time-library.md), [/MDd](../build/reference/md-mt-ld-use-run-time-library.md), veya [/mtd](../build/reference/md-mt-ld-use-run-time-library.md) derleyici seçeneği ayarlanır. Aksi takdirde, tanımlı değil.

- **&#95;DLL** 1 olduğunda tanımlanan [/MD](../build/reference/md-mt-ld-use-run-time-library.md) veya [/MDd](../build/reference/md-mt-ld-use-run-time-library.md) (çok iş parçacıklı DLL) derleyici seçeneği ayarlanır. Aksi takdirde, tanımlı değil.

- **&#95;&#95;FUNCDNAME&#95; &#95;**  içeren bir dize tanımlanan [ile düzenlenmiş adın](../build/reference/decorated-names.md) kapsayan işlevin. Makro bir işlev yalnızca içinde tanımlanır. **&#95; &#95;FUNCDNAME&#95; &#95;** makro kullanırsanız değil Genişletilmiş [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) veya [/P](../build/reference/p-preprocess-to-a-file.md) derleyici seçeneği.

   Bu örnekte `__FUNCDNAME__`, `__FUNCSIG__`, ve `__FUNCTION__` işlev bilgisini görüntülemek için makroları.

   [!code-cpp[NVC_Predefined_Macros_Examples#1](../preprocessor/codesnippet/CPP/predefined-macros_1.cpp)]

- **&#95;&#95;FUNCSIG&#95; &#95;**  kapsayan işlevin imzasını içeren bir dize tanımlanır. Makro bir işlev yalnızca içinde tanımlanır. **&#95; &#95;FUNCSIG&#95; &#95;** makro kullanırsanız değil Genişletilmiş [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) veya [/P](../build/reference/p-preprocess-to-a-file.md) derleyici seçeneği. Çağırma kuralı için bir 64 bit hedef derlendiğinde olan `__cdecl` varsayılan olarak. Kullanım örneği için bkz: `__FUNCDNAME__` makrosu.

- **&#95;&#95;İŞLEV&#95; &#95;**  kapsayan işlevin düzenlenmemiş adını içeren bir dize tanımlanır. Makro bir işlev yalnızca içinde tanımlanır. **&#95; &#95;İşlevi&#95; &#95;** makro kullanırsanız değil Genişletilmiş [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) veya [/P](../build/reference/p-preprocess-to-a-file.md) derleyici seçeneği. Kullanım örneği için bkz: `__FUNCDNAME__` makrosu.

- **&#95;INTEGRAL&#95;MAX&#95;BITS** tamsayı değişmez değer 64 olarak tanımlanan, bir vektör olmayan tamsayı türü için en büyük boyutu (bit cinsinden). Bu makro, her zaman tanımlanır.

   ```cpp
   // integral_max_bits.cpp
   #include <stdio.h>
   int main() {
      printf("%d\n", _INTEGRAL_MAX_BITS);
   }
   ```

- **&#95;&#95;INTELLİSENSE&#95; &#95;**  Visual Studio IDE içinde geçiş sırasında IntelliSense derleyici 1 olarak tanımlanmış. Aksi takdirde, tanımlı değil. Bu makro, IntelliSense derleyici değil anlamak veya derleme ve IntelliSense derleyici arasında geçiş yapmak için kullanmak kod koruma sağlamak için kullanabilirsiniz. Daha fazla bilgi için [sorun giderme ipuçları için IntelliSense yavaşlık](https://blogs.msdn.microsoft.com/vcblog/2011/03/29/troubleshooting-tips-for-intellisense-slowness/).

- **&#95;ISO&#95;geçici** 1 ise tanımlanan [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) derleyici seçeneği ayarlanır. Aksi takdirde, tanımlı değil.

- **&#95;Çekirdek&#95;modu** 1 ise tanımlanan [/Kernel (çekirdek modu ikilisi Oluştur)](../build/reference/kernel-create-kernel-mode-binary.md) derleyici seçeneği ayarlanır. Aksi takdirde, tanımlı değil.

- **&#95;M&#95;AMD64** bu hedef x64 işlemci 100 derlemeleri için tamsayı değişmez değer olarak tanımlanmış. Aksi takdirde, tanımlı değil.

- **&#95;M&#95;ARM** ARM işlemcileri hedefleyen bir derleme için tamsayı değişmez değer 7 olarak tanımlanır. Aksi takdirde, tanımlı değil.

- **&#95;M&#95;ARM&#95;ARMV7VE** 1 olduğunda tanımlanan [/arch:ARMv7VE](../build/reference/arch-arm.md) derleyici seçeneği, ARM işlemcileri hedefleyen derlemeleri için ayarlanır. Aksi takdirde, tanımlı değil.

- **&#95;M&#95;ARM&#95;FP** belirten bir tamsayı sabit değeri tanımlanan [/arch](../build/reference/arch-arm.md) derleyici seçeneği ayarlandıysa, derleme hedef ARM işlemci ise. Aksi takdirde, tanımlı değil.

  - 30-39 aralığında `/arch` ARM seçeneği belirtilmemişse, ARM için varsayılan mimariyi belirten ayarlandığı (`VFPv3`).

  - Aralıktaki 40-49 if `/arch:VFPv4` ayarlandı.

  - Bkz: [/arch (ARM)](../build/reference/arch-arm.md) daha fazla bilgi için.

- **&#95;M&#95;ARM64** 64-bit ARM işlemcileri hedefleyen bir derleme için 1 olarak tanımlanır. Aksi takdirde, tanımlı değil.

- **&#95;M&#95;CEE** 001 Eğer öyleyse herhangi tanımlanan [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği ayarlanır. Aksi takdirde, tanımlı değil.

- **&#95;M&#95;CEE&#95;saf** başına Visual Studio 2015'te kullanım dışı. 001 if tanımlanan [/CLR: pure](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği ayarlanır. Aksi takdirde, tanımlı değil.

- **&#95;M&#95;CEE&#95;güvenli** başına Visual Studio 2015'te kullanım dışı. 001 if tanımlanan [/CLR: safe](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği ayarlanır. Aksi takdirde, tanımlı değil.

- **&#95;M&#95;FP&#95;EXCEPT** 1 ise tanımlanan [/FP: dışında](../build/reference/fp-specify-floating-point-behavior.md) veya [/FP: strict](../build/reference/fp-specify-floating-point-behavior.md) derleyici seçeneği ayarlanır. Aksi takdirde, tanımlı değil.

- **&#95;M&#95;FP&#95;hızlı** 1 ise tanımlanan [Fast](../build/reference/fp-specify-floating-point-behavior.md) derleyici seçeneği ayarlanır. Aksi takdirde, tanımlı değil.

- **&#95;M&#95;FP&#95;PRECISE** 1 ise tanımlanan [/FP: precise](../build/reference/fp-specify-floating-point-behavior.md) derleyici seçeneği ayarlanır. Aksi takdirde, tanımlı değil.

- **&#95;M&#95;FP&#95;KATI** 1 ise tanımlanan [/FP: strict](../build/reference/fp-specify-floating-point-behavior.md) derleyici seçeneği ayarlanır. Aksi takdirde, tanımlı değil.

- **&#95;M&#95;IX86** bu hedef x86 işlemci derlemeleri için 600 tamsayı değişmez değer olarak tanımlanmış. Bu makro x64 veya ARM derleme hedefleri için tanımlı değil.

- **&#95;M&#95;IX86&#95;FP** belirten bir tamsayı sabit değeri tanımlanan [/arch](../build/reference/arch-arm.md) kümesi ya da varsayılan derleyici seçeneği. Bu makroyu derleme hedefi x x86 olduğunda her zaman tanımlanır işlemci. Aksi takdirde, tanımlı değil. Tanımlanan değeri olur:

  - 0 ise `/arch:IA32` derleyici seçeneği ayarlı.

  - 1 ise `/arch:SSE` derleyici seçeneği ayarlı.

  - 2 ise `/arch:SSE2`, `/arch:AVX` veya `/arch:AVX2` derleyici seçeneği ayarlı. Bu değer varsayılan ise bir `/arch` derleyici seçeneği belirtilmedi. Zaman `/arch:AVX` belirtilirse, makro **&#95; &#95;AVX&#95; &#95;** da tanımlanır. Zaman `/arch:AVX2` belirtilirse, her ikisi de **&#95; &#95;AVX&#95; &#95;** ve **&#95; &#95;AVX2&#95; &#95;** de tanımlanabilir.

  - Bkz: [/arch (x86)](../build/reference/arch-x86.md) daha fazla bilgi için.

- **&#95;M&#95;X64** bu hedef x64 işlemci 100 derlemeleri için tamsayı değişmez değer olarak tanımlanmış. Aksi takdirde, tanımlı değil.

- **&#95;YÖNETİLEN** 1 olduğunda tanımlanan [/CLR](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği ayarlanır. Aksi takdirde, tanımlı değil.

- **&#95;MSC&#95;derleme** tanımlanan derleyicinin sürüm numarasının düzeltme numarası öğeyi içeren bir tamsayı değişmez. Düzeltme numarası noktayla ayrılmış sürüm numarasının dördüncü öğedir. Örneğin, Visual C++ derleyicinin sürüm numarası 15.00.20706.01 ise  **&#95;MSC&#95;derleme** makrosu 1 olarak değerlendirir. Bu makro, her zaman tanımlanır.

- **&#95;MSC&#95;UZANTILARI** 1 ise tanımlanan [/Ze (dil uzantılarını etkinleştir)](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneği ayarlandığında, varsayılan. Aksi takdirde, tanımlı değil.

- **&#95;MSC&#95;tam&#95;VER** kodlar büyük bir tamsayı değişmez değer tanımlı, küçük ve derleyicinin sürüm numarasının sayı öğeleri oluşturun. Birincil numara noktayla ayrılmış sürüm numarasının ilk öğedir, ikincil numara ikinci öğe ise ve yapı numarası üçüncü öğedir. Örneğin, Visual C++ derleyicinin sürüm numarası 15.00.20706.01 ise  **&#95;MSC&#95;tam&#95;VER** makrosu 150020706 için değerlendirir. Girin `cl /?` derleyicinin sürüm numarası görüntülemek için komut satırına. Bu makro, her zaman tanımlanır.

- **&#95;MSC&#95;VER** tanımlanan derleyicinin sürüm numarasının büyük ve küçük sayı öğelerini kodlayan bir tamsayı değişmez. Birincil numara noktayla ayrılmış sürüm numarasının ilk öğedir ve ikincil numara ikinci öğedir. Örneğin, Visual C++ derleyicinin sürüm numarası 17.00.51106.1 ise  **&#95;MSC&#95;VER** makrosu 1700 olarak. Girin `cl /?` derleyicinin sürüm numarası görüntülemek için komut satırına. Bu makro, her zaman tanımlanır.

   |Visual Studio sürümü|&AMP;#95;MSC&AMP;#95;VER|
   |-|-|
   |Visual Studio 6.0|1200|
   |Visual Studio .NET 2002 (7.0)|1300|
   |Visual Studio .NET 2003 (7.1)|1310|
   |Visual Studio 2005 (8.0)|1400|
   |Visual Studio 2008 (9.0)|1500|
   |Visual Studio 2010 (10.0)|1600|
   |Visual Studio 2012 (11.0)|1700|
   |Visual Studio 2013 (12.0)|1800|
   |Visual Studio 2015 (14.0)|1900|
   |Visual Studio 2017 RTW (15.0)|1910|
   |Visual Studio 2017 sürüm 15.3|1911|
   |Visual Studio 2017 sürüm 15.5|1912|
   |Visual Studio 2017 sürüm 15.6|1913|
   |Visual Studio 2017 sürüm 15.7|1914|
   |Visual Studio 2017 sürüm 15,8|1915|
   |Visual Studio 2017 sürüm 15.9|1916|

   Derleyici yayınları veya belirli bir sürümü Visual Studio'nun veya sonra güncelleştirmeleri, kullanım için test etmek için **>=** karşılaştırmak için (büyük-veya-eşittir) işleci  **&#95;MSC&#95;VER** bilinen karşı Sürüm. Birbirini dışlayan bir şekilde karşılaştırmak için birden fazla sürümü yüklüyse, azalan sırada sürüm numarasının listeleyin, karşılaştırmaları sipariş öneririz. Örneğin, ardından derleyicilerini veya Visual Studio 2013 sonra yayımlanan alır sonra Visual Studio 2013'ten önce yayımlanan tüm derleyicileri için bir eylem bu kod için Visual Studio 2015 ve sonraki sürümlerinde, yayımlanan derleyiciler denetler:

   ```cpp
   #if _MSC_VER >= 1900
   // . . .
   #elif _MSC_VER >= 1800
   // . . .
   #else
   // . . .
   #endif
   ```

   Daha fazla bilgi için [Visual C++ Derleyici sürümü](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/visual-c-compiler-version/) Visual C++ Team blogunda.

- **&#95;MSVC&#95;LANG** derleyici tarafından hedeflenen C++ dil standardı belirten bir tamsayı sabit değeri olarak tanımlanır. C++ derlendiğinde, makro tamsayı değişmez değer 201402 L ise [/Std: c ++ 14](../build/reference/std-specify-language-standard-version.md) derleyici seçeneği ayarlanır veya varsayılan olarak; 201703 M'ye varsa ayarlanır [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md) ayarlanır ve derleyici seçeneği ayarlanır; bir Yüksek, belirtilmeyen değeri [/Std: c ++ Son](../build/reference/std-specify-language-standard-version.md). Aksi takdirde, makro tanımsız olur. **&#95;MSVC&#95;LANG** makrosu ve [/Std (dil standart sürümünü belirtin)](../build/reference/std-specify-language-standard-version.md) derleyici seçenekleri olan Visual Studio 2015 güncelleştirme 3'te sonraki sürümlerinde kullanılabilir.

- **&#95;&#95;MSVC&#95;çalışma zamanı&#95;DENETLER** biri 1 tanımlanmış, [/RTC](../build/reference/rtc-run-time-error-checks.md) derleyici seçeneklerini ayarlayın. Aksi takdirde, tanımlı değil.

- **&#95;MT** 1 olduğunda tanımlanan [/MD veya/MDd](../build/reference/md-mt-ld-use-run-time-library.md) (çok iş parçacıklı DLL) veya [/MT veya/mtd](../build/reference/md-mt-ld-use-run-time-library.md) (çok iş parçacıklı) belirtildiğinde. Aksi takdirde, tanımlı değil.

- **&#95;YEREL&#95;WCHAR&#95;T&#95;TANIMLANAN** 1 olduğunda tanımlanan [/ZC: wchar_t](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) derleyici seçeneği ayarlanır. Aksi takdirde, tanımlı değil.

- **&#95;OPENMP** , Visual C++ tarafından uygulanan OpenMP belirtiminin tarihini temsil eden tamsayı sabit değeri 200203 olarak tanımlanan [/OpenMP (OpenMP 2.0 desteğini etkinleştir)](../build/reference/openmp-enable-openmp-2-0-support.md) derleyici seçeneği ayarlanır. Aksi takdirde, tanımlı değil.

   ```cpp
   // _OPENMP_dir.cpp
   // compile with: /openmp
   #include <stdio.h>
   int main() {
      printf("%d\n", _OPENMP);
   }
   ```

- **&#95;PREFAST&#95;**  1 olduğunda tanımlanan [/ analyze](../build/reference/analyze-code-analysis.md) derleyici seçeneği ayarlanır. Aksi takdirde, tanımlı değil.

- **&#95;&#95;Zaman damgası&#95; &#95;**  C çalışma zamanı kitaplığı tarafından döndürülen kısaltılmış, sabit uzunluk biçiminde geçerli kaynak dosyanın son değiştirilme saati ve tarihi içeren bir dize sabit değeri olarak tanımlanan [asctime](../c-runtime-library/reference/asctime-wasctime.md) , örneğin, işlev `Fri 19 Aug 13:32:58 2016`. Bu makro, her zaman tanımlanır.

- **&#95;VC&#95;NODEFAULTLIB** 1 olduğunda tanımlanan [/Zl (varsayılan kitaplık adını atla)](../build/reference/zl-omit-default-library-name.md) derleyici seçeneği ayarlanır. Aksi takdirde, tanımlı değil.

- **&#95;WCHAR&#95;T&#95;TANIMLANAN** 1 olduğunda tanımlanan varsayılan [/ZC: wchar_t](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) derleyici seçeneği ayarlanır. **&#95;WCHAR&#95;T&#95;TANIMLANAN** makrosu tanımlandı, ancak hiçbir değer sahipse `/Zc:wchar_t-` derleyici seçeneği ayarlanır, ve **wchar_t** dahil olan sistem üstbilgi dosyasında tanımlanan, Proje. Aksi takdirde, tanımlı değil.

- **&#95;WIN32** tanımlanan 32 bit ARM, 64-bit ARM x86, derleme hedef olduğunda 1 olarak veya x 64. Aksi takdirde, tanımlı değil.

- **&#95;WIN64** derleme hedef 64-bit ARM veya x64 olduğunda 1 tanımlanır. Aksi takdirde, tanımlı değil.

- **&#95;WINRT&#95;DLL** 1 olduğunda, C++ ve her ikisi de derlenmiş tanımlanan [/ZW (Windows çalışma zamanı derlemesi)](../build/reference/zw-windows-runtime-compilation.md) ve [/LD veya /LDd](../build/reference/md-mt-ld-use-run-time-library.md) derleyici seçeneklerini ayarlayın. Aksi takdirde, tanımlı değil.

ATL veya MFC kitaplık sürümünü belirlemek için kullanılan Önişlemci makroları derleyici tarafından önceden tanımlanmamıştır. Gereken üst bilgi eklenir önce ön işlemci yönergelerinde tanımlanmadı şekilde bu makrolar kitaplığı üstbilgisinde tanımlanır.

- **&#95;ATL&#95;VER** tanımlanan \<atldef.h > ATL sürüm numarasını kodlayan bir tamsayı sabit değeri olarak.

- **&#95;MFC&#95;VER** tanımlanan \<afxver_.h > MFC sürüm numarasını kodlayan bir tamsayı sabit değeri olarak.

## <a name="see-also"></a>Ayrıca Bkz.

[Makrolar (C/C++)](../preprocessor/macros-c-cpp.md)<br/>
[Ön İşlemci İşleçleri](../preprocessor/preprocessor-operators.md)<br/>
[Ön işlemci Yönergeleri](../preprocessor/preprocessor-directives.md)