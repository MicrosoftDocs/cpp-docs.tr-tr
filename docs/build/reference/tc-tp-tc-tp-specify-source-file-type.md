---
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
ms.openlocfilehash: c93da6d2498d46e4b7bf3ad37dde852bb6bc82a1
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927625"
---
# <a name="tc-tp-tc-tp-specify-source-file-type"></a>/Tc, /Tp, /TC, /TP (Kaynak Dosya Türünü Belirtin)

**/TC** seçeneği,. c uzantısı olmasa bile, filename bağımsız değişkeninin bir C kaynak dosyası olduğunu belirtir. **/TP** seçeneği,. cpp veya. CXX uzantısı olmasa C++ bile, dosya adı bağımsız değişkeninin bir kaynak dosya olduğunu belirtir. Seçenek ve dosya adı arasındaki bir boşluk isteğe bağlıdır. Her seçenek bir dosya belirtir; ek dosyalar belirtmek için seçeneğini tekrarlayın.

**/TC** ve **/TP** , **/TC** ve **/TP**'ın küresel varyantlardır. Bu, komut satırındaki adlı tüm dosyaları, seçeneğe bağlı olarak komut satırındaki konum olmadan C kaynak dosyaları ( **/TC**) veya C++ kaynak dosyaları ( **/TP**) olarak kabul etmek üzere derleyiciye belirtirler. Bu genel seçenekler, **/TC** veya **/TP**aracılığıyla tek bir dosyada geçersiz kılınabilir.

## <a name="syntax"></a>Sözdizimi

> **/TC** _dosya adı_ **/TP dosya** _adı_ **/TC** /TP
>  
> 
> 

## <a name="arguments"></a>Arguments

*kısaltın*<br/>
Bir C veya C++ kaynak dosyası.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, **CL** . c uzantılı dosyaların c kaynak dosya olduğunu ve. cpp veya. cxx uzantılı dosyaları C++ kaynak dosya olduğunu varsayar.

**TC** veya **TC** seçeneği belirtildiğinde, [/Zc: wchar_t (wchar_t yerel tür)](zc-wchar-t-wchar-t-is-native-type.md) seçeneğinin herhangi bir belirtimi yok sayılır.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **C/C++** Gelişmiş > özellik sayfasını seçin.

1. **Derle** özelliğini değiştirin. Değişikliklerinizi uygulamak için **Tamam ' ı** veya **Uygula** ' yı seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAs%2A>.

## <a name="examples"></a>Örnekler

Bu CL komut satırı MAIN. c, TEST. prg ve Harmanla. prg 'nin tüm C kaynak dosyaları olduğunu belirtir. CL, PRINT. prg öğesini tanımaz.

> CL MAIN. C/Tctest,PRG/Tccollate,PRG PRINT. PRG

Bu CL komut satırı, TEST1. c, TEST2. cxx, TEST3. huh ve TEST4. o 'un dosya olarak C++ DERLENDIĞINI ve test5. z 'nin c dosyası olarak derlendiğini belirtir.

> CL TEST1. C TEST2. CXX TEST3. KUH TEST4. O/TC TEST5. Z/TP

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
