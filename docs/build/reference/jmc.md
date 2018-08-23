---
title: / JMC (yalnızca kendi kodum'hata ayıklama) | Microsoft Docs
ms.custom: 08/20/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /JMC
dev_langs:
- C++
helpviewer_keywords:
- /JMC compiler option [C++]
- Just my code [C++]
- -JMC compiler option [C++]
- User code, debugging
- JMC compiler option [C++]
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1da60b43bd151a776278b51a5ee8a22de7ef3b4c
ms.sourcegitcommit: 7f3df9ff0310a4716b8136ca20deba699ca86c6c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/21/2018
ms.locfileid: "40242847"
---
# <a name="jmc-just-my-code-debugging"></a>/ JMC (yalnızca kendi kodum'hata ayıklama)

Yerel için derleyici desteği belirtir *yalnızca kendi kodum* Visual Studio hata ayıklayıcıda hata ayıklama. Bu seçenek izin sistemi, çerçeve, kitaplık ve diğer kullanıcı olmayan çağrılardan üzerinden adımla ve bu çağrıları çağrı yığını penceresinde daraltmak için Visual Studio kullanıcı ayarlarını destekler. **/JMC** Visual Studio 2017 sürüm 15,8 başlangıç derleyici seçeneği kullanılabilir.

## <a name="syntax"></a>Sözdizimi

> **/ JMC**\[**-**]

## <a name="remarks"></a>Açıklamalar

Visual Studio [yalnızca kendi kodum](/visualstudio/debugger/just-my-code) ayarları, Visual Studio hata ayıklayıcısını sistem, çerçeve, kitaplık ve diğer kullanıcı olmayan çağrılardan adımları belirtin. **/JMC** derleyici seçeneği, yalnızca kendi kodum yerel C++ kodunda hata ayıklama desteği sağlar. Zaman **/JMC** olan etkin, derleyici bir yardımcı işlev çağrıları ekler `__CheckForDebuggerJustMyCode`, işlev giriş. Visual Studio hata ayıklayıcısı yalnızca kendi kodum adım işlemleri destekleyen kancaları yardımcı işlevini sağlar. Visual Studio hata ayıklayıcısı, menü çubuğunda, yalnızca kendi kodum etkinleştirmeyi tercih **Araçları** > **seçenekleri**ve ardından bir seçenek kümesinde **hata ayıklama**  >  **Genel** > **yalnızca kendi kodumu etkinleştir**.

**/JMC** seçeneği gerektirir kodunuzu C çalışma zamanı kitaplığı (sağlayan CRT için), bağlantıları `__CheckForDebuggerJustMyCode` yardımcı işlevi. Projeniz için CRT bağlanmazsa, bağlayıcı hatası görebilirsiniz **LNK2019: çözümlenmemiş dış sembol __CheckForDebuggerJustMyCode**. Bu hatayı gidermek için bağlantı için CRT veya devre dışı **/JMC** seçeneği.

Varsayılan olarak, **/JMC** derleyici seçeneği kapalıdır. Ancak, bu seçenek Visual Studio 2017 sürüm 15,8 başlangıç çoğu Visual Studio Proje şablonları etkinleştirilir. Açıkça bu seçeneği devre dışı bırakma, **/JMC-** komut satırı seçeneği. Visual Studio'da proje özellik sayfaları iletişim kutusunu açmak ve değiştirmek **yalnızca My Code hata ayıklama desteği** özelliğinde **yapılandırma özellikleri** > **C/C++**  >  **Genel** özellik sayfasında **Hayır**.

Daha fazla bilgi için bkz. [C++ Yalnızca benim kodum](/visualstudio/debugger/just-my-code#BKMK_C___Just_My_Code) içinde [yalnızca kendi kodum, Visual Studio kullanarak kullanıcı kodunda hata ayıklama belirtin](/visualstudio/debugger/just-my-code)ve Visual C++ Team Blog gönderisinde [Duyurusu C++ yalnızca kendi kodum Visual Studio'da Adımlama](https://blogs.msdn.microsoft.com/vcblog/2018/06/29/announcing-jmc-stepping-in-visual-studio/).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **genel** özellik sayfası.

1. Değiştirme **yalnızca My Code hata ayıklama desteği** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
