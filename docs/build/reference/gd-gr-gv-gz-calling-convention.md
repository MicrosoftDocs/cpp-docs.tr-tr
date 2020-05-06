---
title: /Gd, /Gr, /Gv, /Gz (Çağırma Kuralı)
ms.date: 09/05/2018
f1_keywords:
- /Gr
- /Gv
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
ms.openlocfilehash: 73fce079a98a3f4afaa35f8b8c6630fc8a9b4ca4
ms.sourcegitcommit: 6b749db14b4cf3a2b8d581fda6fdd8cb98bc3207
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82825532"
---
# <a name="gd-gr-gv-gz-calling-convention"></a>/Gd, /Gr, /Gv, /Gz (Çağırma Kuralı)

Bu seçenekler, işlev bağımsız değişkenlerinin yığına gönderilme sırasını belirler. çağıran işlevi veya çağrılan işlev, çağrının sonundaki bağımsız değişkenleri yığından kaldırır ve derleyicinin bağımsız işlevleri tanımlamak için kullandığı ad dekorasyon kuralını belirtir.

## <a name="syntax"></a>Sözdizimi

> **/GD**\
> **/Gr**\
> **/GV**\
> **/Gz**

## <a name="remarks"></a>Açıklamalar

Varsayılan ayar olan **/GD**, C++ üye işlevleri ve [__stdcall](../../cpp/stdcall.md), [__fastcall](../../cpp/fastcall.md)veya [__vectorcall](../../cpp/vectorcall.md)olarak işaretlenmiş işlevler dışındaki tüm işlevler için [__cdecl](../../cpp/cdecl.md) çağırma kuralını belirtir.

**/Gr** C++ üye `__fastcall` işlevleri, adlandırılmış `main`işlevler ve, `__cdecl` `__stdcall`veya `__vectorcall`olarak işaretli işlevler hariç tüm işlevler için çağırma kuralını belirtir. Tüm `__fastcall` işlevlerin Prototiplerde olması gerekir. Bu çağırma kuralı yalnızca x86 'yi hedefleyen derleyicilerde kullanılabilir ve diğer mimarileri hedefleyen derleyiciler tarafından yok sayılır.

**/Gz** , C++ `__stdcall` üye işlevleri, adlandırılmış `main`işlevler ve, `__cdecl` `__fastcall`veya `__vectorcall`olarak işaretli işlevler hariç tüm işlevler için çağırma kuralını belirtir. Tüm `__stdcall` işlevlerin Prototiplerde olması gerekir. Bu çağırma kuralı yalnızca x86 'yi hedefleyen derleyicilerde kullanılabilir ve diğer mimarileri hedefleyen derleyiciler tarafından yok sayılır.

**/GV** C++ üye `__vectorcall` `main`işlevleri, adlandırılmış işlevler, `vararg` değişken bağımsız değişken listesi olan işlevler veya çakışan `__cdecl`, `__stdcall`veya `__fastcall` özniteliğiyle işaretlenmiş işlevler hariç tüm işlevler için çağrı kuralını belirtir. Bu çağırma kuralı yalnızca/Arch: SSE2 ve üstünü destekleyen x86 ve x64 mimarilerinde kullanılabilir ve ARM mimarisini hedefleyen derleyiciler tarafından yok sayılır.

Değişken sayıda bağımsız değişken alan işlevlerin işaretlenmesi `__cdecl`gerekir.

**/GD**, **/gr**, **/GV** ve **/gz** [/clr: Safe](clr-common-language-runtime-compilation.md) veya **/clr: Pure**ile uyumlu değildir. **/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ve sonrasında desteklenmez.

> [!NOTE]
> Varsayılan olarak, x86 işlemciler için, C++ üye işlevleri [__thiscall](../../cpp/thiscall.md)kullanır.

Tüm işlemciler için `__cdecl`, açıkça, `__fastcall` `__vectorcall`, veya `__stdcall` olarak işaretlenen bir üye işlevi, Bu mimaride yok sayılırsa belirtilen çağırma kuralını kullanır. Değişken sayıda bağımsız değişken alan bir üye işlevi her zaman `__cdecl` çağrı kuralını kullanır.

Bu derleyici seçeneklerinin, C++ yöntemleri ve işlevlerinin ad dekorasyonu üzerinde hiçbir etkisi yoktur. Olarak `extern "C"`açıklanmadığı sürece, C++ yöntemleri ve işlevleri farklı bir ad dekorasyon şeması kullanır. Daha fazla bilgi için bkz. [düzenlenmiş adlar](decorated-names.md).

Çağırma kuralları hakkında daha fazla bilgi için bkz. [çağırma kuralları](../../cpp/calling-conventions.md).

## <a name="__cdecl-specifics"></a>__cdecl özellikleri

X86 işlemcilerde, tüm işlev bağımsız değişkenleri yığına sağdan sola geçirilir. ARM ve x64 mimarilerinde bazı bağımsız değişkenler kayıt tarafından geçirilir ve geri kalan, yığına sağdan sola geçirilir. Çağıran yordam, yığındaki bağımsız değişkenleri açılır.

C için, `__cdecl` adlandırma kuralı önce bir alt çizgi ( `_` ) ile işlev adını kullanır. durum çevirisi yapılmaz. Olarak `extern "C"`açıklanmadığı sürece, C++ işlevleri farklı bir ad dekorasyon şeması kullanır. Daha fazla bilgi için bkz. [düzenlenmiş adlar](decorated-names.md).

## <a name="__fastcall-specifics"></a>__fastcall özellikleri

Bir `__fastcall` işlevin bağımsız değişkenlerinden bazıları yazmaçlara geçirilir (x86 işlemcileri, ecx ve EDX için) ve REST, yığına sağdan sola gönderilir. Çağrılan yordam, döndürülmeden önce bu bağımsız değişkenleri yığından çıkarır. Genellikle, **/gr** yürütme süresini azaltır.

> [!NOTE]
> Satır içi derleme dilinde yazılmış herhangi `__fastcall` bir işlev için çağırma kuralını kullanırken dikkatli olun. Kayıt kullanımı derleyicinin kullanımıyla çakışabilir.

C için, `__fastcall` adlandırma kuralı önünde bir at işareti (**\@**) ve ardından işlev bağımsız değişkenlerinin bayt cinsinden boyutu ile işlev adını kullanır. Durum çevirisi yapılmaz. Derleyici bu şablonu adlandırma kuralı için kullanır:

`@function_name@number`

`__fastcall` Adlandırma kuralını kullandığınızda, standart içerme dosyalarını kullanın. Aksi takdirde, çözümlenmemiş dış başvurular alırsınız.

## <a name="__stdcall-specifics"></a>__stdcall özellikleri

Bir `__stdcall` işlevin bağımsız değişkenleri yığına sağdan sola gönderilir ve çağrılan işlev, döndürülmeden önce bu bağımsız değişkenleri yığından yükler.

C için, `__stdcall` adlandırma kuralı önce bir alt çizgi (**\_**) ve ardından bir at işareti (**\@**) ve işlevin bağımsız değişkenlerinin bayt cinsinden boyutu ile işlev adını kullanır. Durum çevirisi yapılmaz. Derleyici bu şablonu adlandırma kuralı için kullanır:

`_functionname@number`

## <a name="__vectorcall-specifics"></a>__vectorcall özellikleri

`__vectorcall` İşlevin tamsayı bağımsız değişkenleri değere göre geçirilir, en fazla iki (x86) veya dört (x64) tamsayı Yazmaçları, kayan nokta ve vektör değerleri için en fazla altı XMM kaydı ve REST, yığın üzerine sağdan sola geçirilir. Çağrılan işlev, döndürülmadan önce yığını temizler. Vektör ve kayan nokta dönüş değerleri XMM0 içinde döndürülür.

C için, `__vectorcall` adlandırma kuralı, işlev adını, ardından iki işareti (**\@**) ve işlevin bağımsız değişkenlerinin bayt cinsinden boyutunu kullanır. Durum çevirisi yapılmaz. Derleyici bu şablonu adlandırma kuralı için kullanır:

`functionname@@number`

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** > **Gelişmiş** özellik sayfasını seçin.

1. **Çağırma kuralı** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CallingConvention%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [MSVC Derleyicisi Seçenekleri](compiler-options.md)
- [MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
