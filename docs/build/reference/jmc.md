---
title: /JMC (Yalnızca Kendi Kodum’da hata ayıklama)
ms.date: 08/20/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.SupportJustMyCode
helpviewer_keywords:
- /JMC compiler option [C++]
- Just my code [C++]
- -JMC compiler option [C++]
- User code, debugging
- JMC compiler option [C++]
ms.openlocfilehash: 7b22a754f9f49564cd7f76c7d1989cd562f70874
ms.sourcegitcommit: 31a443c9998cf5cfbaff00fcf815b133f55b2426
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/14/2020
ms.locfileid: "86373885"
---
# <a name="jmc-just-my-code-debugging"></a>/JMC (Yalnızca Kendi Kodum’da hata ayıklama)

Visual Studio hata ayıklayıcısında yerel *yalnızca kendi kodum* hata ayıklama için derleyici desteğini belirtir. Bu seçenek, Visual Studio 'Nun sistem, çerçeve, kitaplık ve diğer kullanıcı olmayan çağrılar üzerinde ilermasına ve çağrı yığını penceresinde bu çağrıları daraltmaya izin veren kullanıcı ayarlarını destekler. **/JMC** derleyici seçeneği, Visual Studio 2017 sürüm 15,8 ' den itibaren kullanılabilir.

## <a name="syntax"></a>Syntax

> **/JMC** \[ **-** ]

## <a name="remarks"></a>Açıklamalar

Visual Studio [yalnızca kendi kodum](/visualstudio/debugger/just-my-code) ayarları, Visual Studio hata ayıklayıcı 'nın sistem, çerçeve, kitaplık ve diğer kullanıcı olmayan çağrılar üzerinde adımların yapılıp yapılmayacağını belirtir. **/JMC** derleyici seçeneği, yerel C++ kodunuzda yalnızca kendi kodum hata ayıklama desteğini sağlar. **/JMC** etkinleştirildiğinde, derleyici, işlev giriş bölümündeki bir yardımcı işleve çağrılar ekler `__CheckForDebuggerJustMyCode` . Yardımcı işlevi, Visual Studio hata ayıklayıcısı Yalnızca kendi kodum adım işlemlerini destekleyen kancalar sağlar. Visual Studio hata ayıklayıcıda yalnızca kendi kodum etkinleştirmek için, menü çubuğunda **Araçlar**  >  **Seçenekler**' i seçin ve ardından **Debugging**  >  **genel**  >  **etkinleştirme yalnızca kendi kodum**hata ayıklama seçeneğini belirleyin.

**/JMC** seçeneği, kodunuzun yardımcı Işlevini sağlayan C çalışma zamanı KITAPLıĞı (CRT) ile bağlantı kurulmasını gerektirir `__CheckForDebuggerJustMyCode` . Projeniz CRT 'a bağlantı içermiyorsa, bağlayıcı hatası **LNK2019: çözülmemiş dış sembol __CheckForDebuggerJustMyCode**görebilirsiniz. Bu hatayı çözmek için, CRT 'ya bağlantı ya da **/JMC** seçeneğini devre dışı bırakın.

Varsayılan olarak, **/JMC** derleyici seçeneği kapalıdır. Ancak, Visual Studio 2017 sürüm 15,8 ' den itibaren bu seçenek çoğu Visual Studio proje şablonlarında etkinleştirilmiştir. Bu seçeneği açıkça devre dışı bırakmak için komut satırındaki **/JMC-** seçeneğini kullanın. Visual Studio 'da proje özellik sayfaları iletişim kutusunu açın ve **yapılandırma özellikleri**C/C++ genel özellik sayfasındaki **support yalnızca kendi kodum hata ayıklama** özelliğini  >  **C/C++**  >  **General** **Hayır**olarak değiştirin.

Daha fazla bilgi için bkz. [c++ yalnızca kendi kodum](/visualstudio/debugger/just-my-code#BKMK_C___Just_My_Code) [visual Studio 'da yalnızca kendi kodum kullanarak yalnızca kullanıcı kodunda hata ayıklama yapılıp yapılmayacağını belirtin](/visualstudio/debugger/just-my-code)ve [Visual Studio 'Da C++ Yalnızca kendi kodum adımlamayı duyuruyor](https://devblogs.microsoft.com/cppblog/announcing-jmc-stepping-in-visual-studio/)Visual C++ ekip blog gönderisi.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **genel** özellik sayfasını seçin.

1. **Destek yalnızca kendi kodum hata ayıklama** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)<br/>
