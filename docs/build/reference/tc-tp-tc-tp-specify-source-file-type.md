---
description: Şu konuda daha fazla bilgi edinin:/TC,/TP,/TC,/TP (kaynak dosya türünü belirtin)
title: /Tc, /Tp, /TC, /TP (Kaynak Dosya Türünü Belirtin)
ms.date: 01/11/2018
f1_keywords:
- VC.Project.VCCLWCECompilerTool.CompileAs
- VC.Project.VCCLCompilerTool.CompileAs
- /Tp
- /tc
helpviewer_keywords:
- Tp compiler option [C++]
- /Tc compiler option [C++]
- -Tc compiler option [C++]
- source files, specifying to compiler
- Tc compiler option [C++]
- /Tp compiler option [C++]
- -Tp compiler option [C++]
ms.openlocfilehash: 23aed145c8dd9ac36f26bcebe2ea2aab1c39e586
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230035"
---
# <a name="tc-tp-tc-tp-specify-source-file-type"></a>/Tc, /Tp, /TC, /TP (Kaynak Dosya Türünü Belirtin)

**/TC** seçeneği,. c uzantısı olmasa bile, filename bağımsız değişkeninin bir C kaynak dosyası olduğunu belirtir. **/TP** seçeneği,. cpp veya. CXX uzantısı olmasa bile, filename bağımsız değişkeninin bir C++ kaynak dosyası olduğunu belirtir. Seçenek ve dosya adı arasındaki bir boşluk isteğe bağlıdır. Her seçenek bir dosya belirtir; ek dosyalar belirtmek için seçeneğini tekrarlayın.

**/TC** ve **/TP** , **/TC** ve **/TP**'ın küresel varyantlardır. Bu, komut satırındaki tüm dosyaları C kaynak dosyaları (**/TC**) veya C++ kaynak dosyaları (**/TP**) olarak, seçeneğe bağlı olarak komut satırındaki konuma göre işlemek üzere derleyiciye belirler. Bu genel seçenekler, **/TC** veya **/TP** aracılığıyla tek bir dosyada geçersiz kılınabilir.

## <a name="syntax"></a>Syntax

> **/TC** _dosya adı_\
> **/TP** _dosya adı_\
> **/TC**\
> **/TP**

### <a name="arguments"></a>Arguments

*filename*<br/>
C veya C++ kaynak dosyası.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, **CL** . c uzantılı dosyaların c kaynak dosya olduğunu ve. cpp veya. cxx uzantılı dosyaları C++ kaynak dosyaları olduğunu varsayar.

**TC** veya **TC** seçeneği belirtildiğinde, [/zc: wchar_t (wchar_t yerel tür)](zc-wchar-t-wchar-t-is-native-type.md) seçeneğinin herhangi bir belirtimi yok sayılır.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **Gelişmiş** özellik sayfasını seçin.

1. **Derle** özelliğini değiştirin. Değişikliklerinizi uygulamak için **Tamam ' ı** veya **Uygula** ' yı seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAs%2A>.

## <a name="examples"></a>Örnekler

Bu CL komut satırı MAIN. c, TEST. prg ve Harmanla. prg 'nin tüm C kaynak dosyaları olduğunu belirtir. CL, PRINT. prg öğesini tanımaz.

> CL MAIN. C/Tctest,PRG/Tccollate,PRG PRINT. PRG

Bu CL komut satırı, TEST1. c, TEST2. cxx, TEST3. huh ve TEST4. o 'nun C++ dosyaları olarak derlendiğini ve TEST5. z 'nin C dosyası olarak derlendiğini belirtir.

> CL TEST1. C TEST2. CXX TEST3. KUH TEST4. O/TC TEST5. Z/TP

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
