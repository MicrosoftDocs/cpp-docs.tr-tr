---
title: /Gd, /Gr, /Gv, /Gz (Çağırma Kuralı)
ms.date: 09/05/2018
f1_keywords:
- /gr
- /Gv
- /gz
- /Gd
- VC.Project.VCCLCompilerTool.CallingConvention
helpviewer_keywords:
- -Gd compiler option [C++]
- -Gv compiler option [C++]
- /Gv compiler option [C++]
- -Gr compiler option [C++]
- Gd compiler option [C++]
- Gr compiler option [C++]
- /Gz compiler option [C++]
- -Gz compiler option [C++]
- /Gd compiler option [C++]
- Gz compiler option [C++]
- Gv compiler option [C++]
- /Gr compiler option [C++]
ms.assetid: fd3110cb-2d77-49f2-99cf-a03f9ead00a3
ms.openlocfilehash: eabb4e11715e03745e27911ccd654568d70b8352
ms.sourcegitcommit: 8bb2bea1384b290b7570b01608a86c7488ae7a02
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2019
ms.locfileid: "67400506"
---
# <a name="gd-gr-gv-gz-calling-convention"></a>/Gd, /Gr, /Gv, /Gz (Çağırma Kuralı)

Bu seçenekler çağıran işlevin veya çağrılan işlevin çağrının sonunda yığından bağımsız değişkenler kaldırır olup olmadığını, işlev bağımsız değişkenleri yığın itilir sırasını ve tanımlamak için derleyicinin kullandığı ad dekorasyon kuralı belirler. tek tek işlevleri.

## <a name="syntax"></a>Sözdizimi

> **/Gd**<br/>
> **Gr**<br/>
> **/Gv**<br/>
> **/GZ**

## <a name="remarks"></a>Açıklamalar

**/Gd**, varsayılan ayar belirtir [__cdecl](../../cpp/cdecl.md) hariç tüm işlevler çağırma kuralını C++ üye işlevleri ve işaretli işlevler [__stdcall](../../cpp/stdcall.md), [__fastcall](../../cpp/fastcall.md), veya [__vectorcall](../../cpp/vectorcall.md).

**Gr** belirtir `__fastcall` C++ üye işlevleri hariç tüm işlevler için çağırma kuralı, İşlevler adlı `main`ve işaretli işlevler `__cdecl`, `__stdcall`, veya `__vectorcall`. Tüm `__fastcall` işlevleri prototiplere sahip olmalıdır. Bu çağırma kuralı yalnızca x86 hedefleyen derleyicilerde kullanılabilir ve diğer mimarileri hedefleyen derleyiciler tarafından göz ardı edilir.

**/GZ** belirtir `__stdcall` C++ üye işlevleri hariç tüm işlevler için çağırma kuralı, İşlevler adlı `main`ve işaretli işlevler `__cdecl`, `__fastcall`, veya `__vectorcall`. Tüm `__stdcall` işlevleri prototiplere sahip olmalıdır. Bu çağırma kuralı yalnızca x86 hedefleyen derleyicilerde kullanılabilir ve diğer mimarileri hedefleyen derleyiciler tarafından göz ardı edilir.

**/GV** belirtir `__vectorcall` hariç tüm işlevler çağırma kuralını C++ üye işlevleri, İşlevler adlı `main`, içeren işlevler bir `vararg` bağımsız değişken listesi veya çakışan ile işaretlenen İşlevler `__cdecl`, `__stdcall`, veya `__fastcall` özniteliği. Bu çağırma kuralı yalnızca/arch: SSE2 desteği x86 ve x64 mimarilerde ve üzerinde kullanılabilir ve ARM mimarisini hedefleyen derleyiciler tarafından göz ardı edilir.

Değişken sayıda bağımsız değişkenler almayan işlevleri işaretlenmelidir `__cdecl`.

**/Gd**, **GR**, **GV** ve **/Gz** ile uyumlu [/CLR: safe](clr-common-language-runtime-compilation.md) veya   **/CLR: pure**. **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 ve sonraki sürümlerde desteklenmiyor.

> [!NOTE]
> X86 için varsayılan olarak işlemciler C++ üye işlevleri kullanmak [__thiscall](../../cpp/thiscall.md).

Tüm işlemciler için açıkça olarak işaretlenen bir üye işlev `__cdecl`, `__fastcall`, `__vectorcall`, veya `__stdcall` o mimaride yok sayılmıyorsa belirli çağrı kuralını kullanır. Değişken sayıda bağımsız değişken kullanan her zaman alan bir üye işlev `__cdecl` çağırma kuralı.

Bu derleyici seçeneklerinin, C++ yöntemleri ve işlevlerinin ad düzenlemesi üzerine hiçbir etkisi. Olarak bildirilmedikleri sürece `extern "C"`, C++ yöntemleri ve işlevleri farklı bir ad dekorasyon düzeni kullanın. Daha fazla bilgi için [düzenlenmiş adlar](decorated-names.md).

Çağırma kuralları hakkında daha fazla bilgi için bkz. [çağırma kuralları](../../cpp/calling-conventions.md).

## <a name="cdecl-specifics"></a>__cdecl özellikleri

X86 işlemcilerde, tüm işlev bağımsız değişkenleri Kalanlar yığın üzerinde sağdan sola. ARM ve x64 mimarilerinde, bazı bağımsız değişkenler kayıt tarafından geçirilir ve geri Kalanlar yığın üzerinde sağdan sola. Çağıran yordam, yığından bağımsız değişkenleri yığından açar.

C'de, `__cdecl` kuralı kullanan bir işlev adı adlandırma öncesinde bir alt çizgi ( `_` ); durum çevirisi yapılmaz. Olarak bildirilmedikleri sürece `extern "C"`, C++ işlevleri farklı bir ad dekorasyon düzeni kullanır. Daha fazla bilgi için [düzenlenmiş adlar](decorated-names.md).

## <a name="fastcall-specifics"></a>__fastcall özellikleri

Bazı bir `__fastcall` işlev bağımsız yazmaçlara geçirilir (x86 için işlemciler, ECX ve EDX), ve geri kalan yığın üstüne sağdan sola itilir. Çağırılan rutin, döndürülmeden önce yığından bu bağımsız değişkenleri yığından açar. Genellikle, **GR** yürütme süresini azaltır.

> [!NOTE]
> Kullanırken dikkatli olun `__fastcall` satır içi derleme dilinde yazılmış bir işlev çağırma kuralını. Yazmaçların kullanımı derleyicinin kullanımıyla çakışabilir.

C'de, `__fastcall` kuralı kullanan bir işlev adı adlandırma öncesinde bir at işareti ( **\@** ) işlev bağımsız değişkenlerinin bayt cinsinden boyutu ardından. Durum çevirisi yok gerçekleştirilir. Derleyici, bu şablon yönelik adlandırma kuralını kullanır:

`@function_name@number`

Kullanırken `__fastcall` dosyalarını adlandırma kuralını kullanın. Aksi takdirde, çözülmemiş dış başvurular alırsınız.

## <a name="stdcall-specifics"></a>__stdcall özellikleri

A `__stdcall` işlevinin bağımsız değişkenleri sağdan sola yığın itilir ve çağrılan işlev döndürülmeden önce yığından bu bağımsız yığından açar.

C'de, `__stdcall` kuralı kullanan bir işlev adı adlandırma öncesinde bir alt çizgi ( **\_** ) ve ardından bir at işareti ( **\@** ) ve işlevin boyutu bayt cinsinden bağımsız değişkenler. Gerçekleşen durum çevirisi yok. Derleyici, bu şablon yönelik adlandırma kuralını kullanır:

`_functionname@number`

## <a name="vectorcall-specifics"></a>__vectorcall özellikleri

A `__vectorcall` işlevinin tamsayı değişkenleri (x x86) iki veya dört (x x64) kullanılarak değerle geçirilir tamsayı kaydeder ve en fazla altı XMM için kayan nokta ve vektör değerleri ve geri Kalanlar yığın üzerinde sağdan sola. Çağrılan işlev, döndürülmeden önce yığını temizler. XMM0'vektör ve kayan nokta dönüş değerleri döndürülür.

C'de, `__vectorcall` adlandırma kuralı iki et işareti işlevi adından kullanır ( **\@\@** ) ve işlev bağımsız değişkenlerinin bayt cinsinden boyutu. Gerçekleşen durum çevirisi yok. Derleyici, bu şablon yönelik adlandırma kuralını kullanır:

`functionname@@number`

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **C/C++**  > **Gelişmiş** özellik sayfası.

1. Değiştirme **çağırma kuralı** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CallingConvention%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [MSVC Derleyicisi Seçenekleri](compiler-options.md)
- [MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
