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
ms.openlocfilehash: 90fcad40b3322f8a8ae7ffc58875c2850f143138
ms.sourcegitcommit: 0867d648e0955ebad7260b5fbebfd6cd4d58f3c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/19/2019
ms.locfileid: "68341003"
---
# <a name="jmc-just-my-code-debugging"></a>/JMC (Yalnızca Kendi Kodum’da hata ayıklama)

Visual Studio hata ayıklayıcısında yerel *yalnızca kendi kodum* hata ayıklama için derleyici desteğini belirtir. Bu seçenek, Visual Studio 'Nun sistem, çerçeve, kitaplık ve diğer kullanıcı olmayan çağrılar üzerinde ilermasına ve çağrı yığını penceresinde bu çağrıları daraltmaya izin veren kullanıcı ayarlarını destekler. **/JMC** derleyici seçeneği, Visual Studio 2017 sürüm 15,8 ' den itibaren kullanılabilir.

## <a name="syntax"></a>Sözdizimi

> **/JMC**\[] **-**

## <a name="remarks"></a>Açıklamalar

Visual Studio [yalnızca kendi kodum](/visualstudio/debugger/just-my-code) ayarları, Visual Studio hata ayıklayıcı 'nın sistem, çerçeve, kitaplık ve diğer kullanıcı olmayan çağrılar üzerinde adımların yapılıp yapılmayacağını belirtir. **/JMC** derleyici seçeneği, yerel C++ kodunuzda yalnızca kendi kodum hata ayıklama desteğini sağlar. **/JMC** etkinleştirildiğinde, derleyici, işlev giriş bölümündeki bir yardımcı işleve `__CheckForDebuggerJustMyCode`çağrılar ekler. Yardımcı işlevi, Visual Studio hata ayıklayıcısı Yalnızca kendi kodum adım işlemlerini destekleyen kancalar sağlar. Visual Studio hata ayıklayıcıda yalnızca kendi kodum etkinleştirmek için, menü çubuğunda **Araçlar** > **Seçenekler**' i seçin ve ardından**genel** > **etkinleştirme yalnızca kendi kodum** **hata ayıklama** > seçeneğini belirleyin.

**/JMC** seçeneği, kodunuzun `__CheckForDebuggerJustMyCode` yardımcı işlevini sağlayan C çalışma zamanı kitaplığı (CRT) ile bağlantı kurulmasını gerektirir. Projeniz CRT 'a bağlantı içermiyorsa, bağlayıcı hatası **LNK2019: çözülmemiş dış sembol __Checkfordebuggeryatmycode**' u görebilirsiniz. Bu hatayı çözmek için, CRT 'ya bağlantı ya da **/JMC** seçeneğini devre dışı bırakın.

Varsayılan olarak, **/JMC** derleyici seçeneği kapalıdır. Ancak, Visual Studio 2017 sürüm 15,8 ' den itibaren bu seçenek çoğu Visual Studio proje şablonlarında etkinleştirilmiştir. Bu seçeneği açıkça devre dışı bırakmak için komut satırındaki **/JMC-** seçeneğini kullanın. Visual Studio 'da proje özellik sayfaları iletişim kutusunu açın ve **yapılandırma özellikleri** >  > **C/C++** **genel** özellik sayfasındaki **support yalnızca kendi kodum hata ayıklama** özelliğini **Hayır**.

Daha fazla bilgi için bkz [ C++ . yalnızca kendi kodum](/visualstudio/debugger/just-my-code#BKMK_C___Just_My_Code) Visual Studio 'da [yalnızca kendi kodum kullanarak yalnızca kullanıcı kodunda hata ayıklama yapılıp yapılmayacağını belirtme](/visualstudio/debugger/just-my-code)ve Visual C++ Team blog gönderisi Visual [Studio C++ 'da yalnızca kendi kodum adımlanıyor](https://blogs.msdn.microsoft.com/vcblog/2018/06/29/announcing-jmc-stepping-in-visual-studio/).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **C/C++** genel > Özellik sayfası ' nı seçin.

1. **Destek yalnızca kendi kodum hata ayıklama** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
