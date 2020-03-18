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
ms.openlocfilehash: 92fd4f6ae4193e86edb114cc366e6d40e4208ca8
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439670"
---
# <a name="gd-gr-gv-gz-calling-convention"></a>/Gd, /Gr, /Gv, /Gz (Çağırma Kuralı)

Bu seçenekler, işlev bağımsız değişkenlerinin yığına gönderilme sırasını belirler. çağıran işlevi veya çağrılan işlev, çağrının sonundaki bağımsız değişkenleri yığından kaldırır ve derleyicinin tanımlamak için kullandığı ad dekorasyon kuralını belirtir. ayrı işlevler.

## <a name="syntax"></a>Sözdizimi

> **/GD**<br/>
> **/Gr**<br/>
> **/GV**<br/>
> **/Gz**

## <a name="remarks"></a>Açıklamalar

Varsayılan ayar olan **/GD**, [__fastcall](../../cpp/fastcall.md)veya [__vectorcall](../../cpp/vectorcall.md) [__stdcall](../../cpp/stdcall.md)işaretlenmiş üye işlevleri ve işlevler hariç C++ tüm işlevler için [__cdecl](../../cpp/cdecl.md) çağırma kuralını belirtir.

**/Gr** üye işlevleri, `main`adlı işlevler ve `__cdecl`, C++ `__stdcall`veya `__vectorcall`olarak işaretlenen işlevler hariç tüm işlevler için `__fastcall` çağırma kuralını belirtir. Tüm `__fastcall` işlevleri prototiptürlerine sahip olmalıdır. Bu çağırma kuralı yalnızca x86 'yi hedefleyen derleyicilerde kullanılabilir ve diğer mimarileri hedefleyen derleyiciler tarafından yok sayılır.

**/Gz** ; üye işlevleri, `main`adlı işlevler ve `__cdecl`C++ , `__fastcall`veya `__vectorcall`olarak işaretlenen işlevler hariç tüm işlevler için çağrı kuralı `__stdcall` belirtir. Tüm `__stdcall` işlevleri prototiptürlerine sahip olmalıdır. Bu çağırma kuralı yalnızca x86 'yi hedefleyen derleyicilerde kullanılabilir ve diğer mimarileri hedefleyen derleyiciler tarafından yok sayılır.

**/GV** ; üye işlevleri, `main`adlı işlevler, `vararg` C++ değişken bağımsız değişken listesi olan işlevler veya çakışan bir `__cdecl`, `__stdcall`veya `__fastcall` özniteliğiyle işaretlenmiş işlevler dışındaki tüm işlevler için `__vectorcall` çağırma kuralını belirtir. Bu çağırma kuralı yalnızca/Arch: SSE2 ve üstünü destekleyen x86 ve x64 mimarilerinde kullanılabilir ve ARM mimarisini hedefleyen derleyiciler tarafından yok sayılır.

Değişken sayıda bağımsız değişken alan işlevlerin `__cdecl`olarak işaretlenmesi gerekir.

**/GD**, **/gr**, **/GV** ve **/gz** [/clr: Safe](clr-common-language-runtime-compilation.md) veya **/clr: Pure**ile uyumlu değildir. **/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ve sonrasında desteklenmez.

> [!NOTE]
> Varsayılan olarak, C++ x86 işlemcileri için üye işlevleri [__thiscall](../../cpp/thiscall.md)kullanır.

Tüm işlemciler için, açıkça `__cdecl`, `__fastcall`, `__vectorcall`veya `__stdcall` olarak işaretlenen bir üye işlevi, Bu mimaride yok sayılmaması durumunda belirtilen çağırma kuralını kullanır. Değişken sayıda bağımsız değişken alan bir üye işlevi her zaman `__cdecl` çağırma kuralını kullanır.

Bu derleyici seçeneklerinin, C++ yöntemlerin ve işlevlerin ad dekorasyonu üzerinde hiçbir etkisi yoktur. `extern "C"`olarak bildirildiği sürece, C++ Yöntemler ve işlevler farklı bir ad dekorasyon şeması kullanır. Daha fazla bilgi için bkz. [düzenlenmiş adlar](decorated-names.md).

Çağırma kuralları hakkında daha fazla bilgi için bkz. [çağırma kuralları](../../cpp/calling-conventions.md).

## <a name="__cdecl-specifics"></a>__cdecl özellikleri

X86 işlemcilerde, tüm işlev bağımsız değişkenleri yığına sağdan sola geçirilir. ARM ve x64 mimarilerinde bazı bağımsız değişkenler kayıt tarafından geçirilir ve geri kalan, yığına sağdan sola geçirilir. Çağıran yordam, yığındaki bağımsız değişkenleri açılır.

C için `__cdecl` adlandırma kuralı, önce bir alt çizgi (`_`) tarafından işlev adını kullanır; durum çevirisi yapılmaz. `extern "C"`olarak bildirildiği sürece, C++ işlevler farklı bir ad dekorasyon şeması kullanır. Daha fazla bilgi için bkz. [düzenlenmiş adlar](decorated-names.md).

## <a name="__fastcall-specifics"></a>__fastcall özellikleri

Bir `__fastcall` işlevinin bağımsız değişkenlerinden bazıları yazmaçlara geçirilir (x86 işlemcileri, ECX ve EDX için) ve REST, yığının üzerine sağdan sola gönderilir. Çağrılan yordam, döndürülmeden önce bu bağımsız değişkenleri yığından çıkarır. Genellikle, **/gr** yürütme süresini azaltır.

> [!NOTE]
> Satır içi derleme dilinde yazılmış herhangi bir işlev için `__fastcall` çağırma kuralını kullanırken dikkatli olun. Kayıt kullanımı derleyicinin kullanımıyla çakışabilir.

C için `__fastcall` adlandırma kuralı, önce bir at işareti ( **\@** ) ve ardından işlev bağımsız değişkenlerinin bayt cinsinden boyutu ile işlev adını kullanır. Durum çevirisi yapılmaz. Derleyici bu şablonu adlandırma kuralı için kullanır:

`@function_name@number`

`__fastcall` adlandırma kuralını kullandığınızda, standart içerme dosyalarını kullanın. Aksi takdirde, çözümlenmemiş dış başvurular alırsınız.

## <a name="__stdcall-specifics"></a>__stdcall özellikleri

Bir `__stdcall` işlevin bağımsız değişkenleri, sağdan sola yığına gönderilir ve çağrılan işlev, döndürülmeden önce bu bağımsız değişkenleri yığından yükler.

C için `__stdcall` adlandırma kuralı, önce bir alt çizgi ( **\_** ) ve ardından bir at işareti ( **\@** ) ve işlev bağımsız değişkenlerinin bayt cinsinden boyutu ile işlev adını kullanır. Durum çevirisi yapılmaz. Derleyici bu şablonu adlandırma kuralı için kullanır:

`_functionname@number`

## <a name="__vectorcall-specifics"></a>__vectorcall özellikleri

`__vectorcall` işlevin tamsayı bağımsız değişkenleri değere göre geçirilir, en fazla iki (x86) veya dört (x64) tamsayı Yazmaçları, kayan nokta ve vektör değerleri için en fazla altı XMM kaydı ve REST, yığın üzerine sağdan sola geçirilir. Çağrılan işlev, döndürülmadan önce yığını temizler. Vektör ve kayan nokta dönüş değerleri XMM0 içinde döndürülür.

C için `__vectorcall` adlandırma kuralı, işlev adını izleyen iki işareti ( **\@\@** ) ve işlev bağımsız değişkenlerinin bayt cinsinden boyutunu kullanır. Durum çevirisi yapılmaz. Derleyici bu şablonu adlandırma kuralı için kullanır:

`functionname@@number`

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++**  > **Gelişmiş** özellik sayfasını seçin.

1. **Çağırma kuralı** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CallingConvention%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [MSVC Derleyicisi Seçenekleri](compiler-options.md)
- [MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
 