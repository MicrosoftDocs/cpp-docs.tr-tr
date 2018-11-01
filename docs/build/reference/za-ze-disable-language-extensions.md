---
title: /Za, /Ze (Dil Uzantılarını Devre Dışı Bırak)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.DisableLanguageExtensions
- /za
- /ze
- VC.Project.VCCLCompilerTool.DisableLanguageExtensions
helpviewer_keywords:
- -Za compiler option [C++]
- Za compiler option [C++]
- language extensions, disabling in compiler
- -Ze compiler option [C++]
- language extensions
- enable language extensions
- /Za compiler option [C++]
- /Ze compiler option [C++]
- Disable Language Extensions compiler option
- Ze compiler option [C++]
ms.assetid: 65e49258-7161-4289-a176-7c5c0656b1a2
ms.openlocfilehash: a3d25f71739f9948f2c0237efbaeaf8fa89f2114
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50549727"
---
# <a name="za-ze-disable-language-extensions"></a>/Za, /Ze (Dil Uzantılarını Devre Dışı Bırak)

**/Za** derleyici seçeneği, ANSI C89 veya ISO C ++ 11 ile uyumlu olmayan dil yapıları için bir hata gösterir. **/Ze** derleyici seçeneği, varsayılan olarak açıktır, Microsoft uzantıları sağlar.

## <a name="syntax"></a>Sözdizimi

```
/Za
/Ze
```

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  **/Ze** davranışını varsayılan olarak açık olduğundan seçeneği kullanım dışı. Kullanmanızı öneririz [/Zc (Uyumluluk)](../../build/reference/zc-conformance.md) belirli bir dil uzantısı özellikleri denetlemek için derleyici seçenekleri. Kullanım dışı derleyici seçeneklerinin bir listesi için bkz. **kullanım dışı ve derleyici seçenekleri kaldırıldı** konusundaki [kategoriye göre listelenmiş derleyici seçenekleri](../../build/reference/compiler-options-listed-by-category.md).

Visual C++ derleyicisi ANSI C89, ISO C99 veya ISO C++ standartlarına içinde belirtilen dışında özellikleri sunar. Bu özellikler, topluca C ve C++ için Microsoft uzantıları bilinir. Varsayılan olarak kullanılabilir ve kullanılabilir değil bu uzantılar ne zaman **/Za** seçeneği belirtildi. Belirli uzantılar hakkında daha fazla bilgi için bkz. [C ve C++ için Microsoft Extensions](../../build/reference/microsoft-extensions-to-c-and-cpp.md).

Belirterek dil uzantılarını devre dışı öneririz **/Za** programınızı diğer ortamlara bağlantı noktası planlıyorsanız seçeneği. Zaman **/Za** belirtilirse, derleyici Microsoft genişletilmiş anahtar sözcükleri basit tanımlayıcıları olarak değerlendirir, diğer Microsoft uzantılarını devre dışı bırakır ve otomatik olarak tanımlar `__STDC__` C programları için önceden tanımlanmış makro.

İle kullanılan diğer derleyici seçeneklerini **/Za** nasıl derleyici standartlara uyum sağlar etkileyebilir.

Belirli standartlarla uyumlu davranışı ayarları belirtmek daha fazla yolu için bkz [/Zc](../../build/reference/zc-conformance.md) derleyici seçeneği.

Visual C++ ile uyumluluk sorunları hakkında daha fazla bilgi için bkz. [standart dışı davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Gezinti bölmesinde **yapılandırma özellikleri**, **C/C++**, **dil**.

1. Değiştirme **dil uzantılarını devre dışı** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableLanguageExtensions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[/Zc (Uyumluluk)](../../build/reference/zc-conformance.md)
