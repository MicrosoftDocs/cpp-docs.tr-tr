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
ms.openlocfilehash: e1617b7c158e9705a6211310fa7873f667a62ba5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87234373"
---
# <a name="gd-gr-gv-gz-calling-convention"></a>/Gd, /Gr, /Gv, /Gz (Çağırma Kuralı)

Bu seçenekler, işlev bağımsız değişkenlerinin yığına gönderilme sırasını belirler. çağıran işlevi veya çağrılan işlev, çağrının sonundaki bağımsız değişkenleri yığından kaldırır ve derleyicinin bağımsız işlevleri tanımlamak için kullandığı ad dekorasyon kuralını belirtir.

## <a name="syntax"></a>Sözdizimi

> **`/Gd`**\
> **`/Gr`**\
> **`/Gv`**\
> **`/Gz`**

## <a name="remarks"></a>Açıklamalar

**`/Gd`** Varsayılan ayar, C++ üye işlevleri ve [__stdcall](../../cpp/stdcall.md), [__fastcall](../../cpp/fastcall.md)veya [__vectorcall](../../cpp/vectorcall.md)olarak işaretlenmiş işlevler dışındaki tüm işlevler için [__cdecl](../../cpp/cdecl.md) çağırma kuralını belirtir.

**`/Gr`****`__fastcall`** C++ üye işlevleri, adlandırılmış işlevler `main` ve, veya olarak işaretli işlevler hariç tüm işlevler için çağrı kuralını belirtir **`__cdecl`** **`__stdcall`** **`__vectorcall`** . Tüm **`__fastcall`** işlevlerin Prototiplerde olması gerekir. Bu çağırma kuralı yalnızca x86 'yi hedefleyen derleyicilerde kullanılabilir ve diğer mimarileri hedefleyen derleyiciler tarafından yok sayılır.

**`/Gz`****`__stdcall`** C++ üye işlevleri, adlandırılmış işlevler `main` ve, veya olarak işaretli işlevler hariç tüm işlevler için çağrı kuralını belirtir **`__cdecl`** **`__fastcall`** **`__vectorcall`** . Tüm **`__stdcall`** işlevlerin Prototiplerde olması gerekir. Bu çağırma kuralı yalnızca x86 'yi hedefleyen derleyicilerde kullanılabilir ve diğer mimarileri hedefleyen derleyiciler tarafından yok sayılır.

**`/Gv`****`__vectorcall`** C++ üye işlevleri, adlandırılmış işlevler `main` , `vararg` değişken bağımsız değişken listesi olan işlevler veya çakışan **`__cdecl`** , **`__stdcall`** veya özniteliğiyle işaretlenmiş işlevler **`__fastcall`** hariç tüm işlevler için çağrı kuralını belirtir. Bu çağırma kuralı yalnızca/Arch: SSE2 ve üstünü destekleyen x86 ve x64 mimarilerinde kullanılabilir ve ARM mimarisini hedefleyen derleyiciler tarafından yok sayılır.

Değişken sayıda bağımsız değişken alan işlevlerin işaretlenmesi gerekir **`__cdecl`** .

**`/Gd`**, **`/Gr`** **`/Gv`** ve, **`/Gz`** [`/clr:safe`](clr-common-language-runtime-compilation.md) veya **/clr: Pure**ile uyumlu değildir. **/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ve sonrasında desteklenmez.

> [!NOTE]
> Varsayılan olarak, x86 işlemcileri için C++ üye işlevleri kullanır [`__thiscall`](../../cpp/thiscall.md) .

Tüm işlemciler için, açıkça,, veya olarak işaretlenen bir üye işlevi, **`__cdecl`** **`__fastcall`** **`__vectorcall`** **`__stdcall`** Bu mimaride yok sayılırsa belirtilen çağırma kuralını kullanır. Değişken sayıda bağımsız değişken alan bir üye işlevi her zaman **`__cdecl`** çağrı kuralını kullanır.

Bu derleyici seçeneklerinin, C++ yöntemleri ve işlevlerinin ad dekorasyonu üzerinde hiçbir etkisi yoktur. Olarak açıklanmadığı sürece `extern "C"` , C++ yöntemleri ve işlevleri farklı bir ad dekorasyon şeması kullanır. Daha fazla bilgi için bkz. [düzenlenmiş adlar](decorated-names.md).

Çağırma kuralları hakkında daha fazla bilgi için bkz. [çağırma kuralları](../../cpp/calling-conventions.md).

## <a name="__cdecl-specifics"></a>__cdecl özellikleri

X86 işlemcilerde, tüm işlev bağımsız değişkenleri yığına sağdan sola geçirilir. ARM ve x64 mimarilerinde bazı bağımsız değişkenler kayıt tarafından geçirilir ve geri kalan, yığına sağdan sola geçirilir. Çağıran yordam, yığındaki bağımsız değişkenleri açılır.

C için, **`__cdecl`** adlandırma kuralı önce bir alt çizgi () tarafından işlev adını kullanır `_` ; durum çevirisi gerçekleştirilmez. Olarak açıklanmadığı sürece `extern "C"` , C++ işlevleri farklı bir ad dekorasyon şeması kullanır. Daha fazla bilgi için bkz. [düzenlenmiş adlar](decorated-names.md).

## <a name="__fastcall-specifics"></a>__fastcall özellikleri

Bir **`__fastcall`** işlevin bağımsız değişkenlerinden bazıları yazmaçlara geçirilir (x86 işlemcileri, ecx ve EDX için) ve REST, yığına sağdan sola gönderilir. Çağrılan yordam, döndürülmeden önce bu bağımsız değişkenleri yığından çıkarır. Genellikle, **/gr** yürütme süresini azaltır.

> [!NOTE]
> **`__fastcall`** Satır içi derleme dilinde yazılmış herhangi bir işlev için çağırma kuralını kullanırken dikkatli olun. Kayıt kullanımı derleyicinin kullanımıyla çakışabilir.

C için, **`__fastcall`** adlandırma kuralı önünde bir at işareti ( **\@** ) ve ardından işlev bağımsız değişkenlerinin bayt cinsinden boyutu ile işlev adını kullanır. Durum çevirisi yapılmaz. Derleyici bu şablonu adlandırma kuralı için kullanır:

`@function_name@number`

**`__fastcall`** Adlandırma kuralını kullandığınızda, standart içerme dosyalarını kullanın. Aksi takdirde, çözümlenmemiş dış başvurular alırsınız.

## <a name="__stdcall-specifics"></a>__stdcall özellikleri

Bir **`__stdcall`** işlevin bağımsız değişkenleri yığına sağdan sola gönderilir ve çağrılan işlev, döndürülmeden önce bu bağımsız değişkenleri yığından yükler.

C için, **`__stdcall`** adlandırma kuralı önce bir alt çizgi ( **\_** ) ve ardından bir at işareti ( **\@** ) ve işlevin bağımsız değişkenlerinin bayt cinsinden boyutu ile işlev adını kullanır. Durum çevirisi yapılmaz. Derleyici bu şablonu adlandırma kuralı için kullanır:

`_functionname@number`

## <a name="__vectorcall-specifics"></a>__vectorcall özellikleri

**`__vectorcall`** İşlevin tamsayı bağımsız değişkenleri değere göre geçirilir, en fazla iki (x86) veya dört (x64) tamsayı Yazmaçları, kayan nokta ve vektör değerleri için en fazla altı XMM kaydı ve REST, yığın üzerine sağdan sola geçirilir. Çağrılan işlev, döndürülmadan önce yığını temizler. Vektör ve kayan nokta dönüş değerleri XMM0 içinde döndürülür.

C için, **`__vectorcall`** adlandırma kuralı, işlev adını, ardından iki işareti ( **\@\@** ) ve işlevin bağımsız değişkenlerinin bayt cinsinden boyutunu kullanır. Durum çevirisi yapılmaz. Derleyici bu şablonu adlandırma kuralı için kullanır:

`functionname@@number`

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++**  >  **Gelişmiş** özellik sayfasını seçin.

1. **Çağırma kuralı** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CallingConvention%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [MSVC derleyici seçenekleri](compiler-options.md)
- [MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
