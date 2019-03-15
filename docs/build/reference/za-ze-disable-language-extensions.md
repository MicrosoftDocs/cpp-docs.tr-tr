---
title: /Za, /Ze (Dil Uzantılarını Devre Dışı Bırak)
ms.date: 02/19/2019
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
ms.openlocfilehash: 1db1dbdba4829ccf939cdc4f07ccfefe2474a35d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812310"
---
# <a name="za-ze-disable-language-extensions"></a>/Za, /Ze (Dil Uzantılarını Devre Dışı Bırak)

**/Za** derleyici seçeneği devre dışı bırakır ve C için ANSI C89/ISO C90 ile uyumlu değil Microsoft uzantıları için hataları yayar. Kullanım dışı **/Ze** derleyici seçeneği Microsoft uzantıları sağlar. Microsoft uzantıları varsayılan olarak etkindir.

## <a name="syntax"></a>Sözdizimi

> **/Za**<br/>
> **/Ze**

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Kullanımını **/Za** zaman kodu derlendiğinde gibi C++ önerilmez. **/Ze** davranışını varsayılan olarak açık olduğundan seçeneği kullanım dışı. Kullanım dışı derleyici seçeneklerinin bir listesi için bkz. [kullanım dışı ve kaldırılan derleyici seçenekleri](compiler-options-listed-by-category.md#deprecated-and-removed-compiler-options).

Microsoft C/C++ derleyicisi, C kodu, derleme iki yolla destekler:

- Bir kaynak dosyası varsa derleyici C derleme modu varsayılan olarak kullanır. bir *.c* uzantısı veya [/Tc](tc-tp-tc-tp-specify-source-file-type.md) veya [/TC](tc-tp-tc-tp-specify-source-file-type.md) seçeneği belirtildi. C derleyicisi C diline yönelik Microsoft uzantıları varsayılan olarak etkinleştirir, C89/C90 derleyicisidir. Belirli uzantılar hakkında daha fazla bilgi için bkz. [C ve C++ için Microsoft Extensions](microsoft-extensions-to-c-and-cpp.md). Hem C derleme ve **/Za** seçeneği belirtilirse, C Derleyici uyumlu kesinlikle C89/C90 standart. Microsoft genişletilmiş anahtar sözcükleri basit tanımlayıcıları olarak değerlendirir, diğer Microsoft uzantılarını devre dışı bırakır ve otomatik olarak tanımlar derleyici [ \_ \_STDC\_ \_ ](../../preprocessor/predefined-macros.md) önceden tanımlanmış Makro C programları için.

- Derleyici C++ derleme modunda C kodu olarak derleyebilirsiniz. Bu, davranıştır olmayan kaynak dosyaları için varsayılan bir *.c* uzantısı ve ne zaman [/Tp](tc-tp-tc-tp-specify-source-file-type.md) veya [/TP](tc-tp-tc-tp-specify-source-file-type.md) seçeneği belirtildi. C++ derleme modunda, derleyici standart C++ dahil ISO C99 ve C11 standartları bölümlerine destekler. Neredeyse tüm C kodu aynı zamanda geçerli C++ kodudur. C anahtar sözcükleri ve kod yapıları az sayıda C++ kodu geçerli değil veya c++'ta farklı şekilde yorumlanır. Derleyici, bu gibi durumlarda standart C++ göre davranır. C++ derleme modunda **/Za** seçeneği beklenmeyen davranışlara neden olabilir ve önerilmez.

Diğer derleyici seçenekleri, derleyici standartlara uyumluluk nasıl sağlar? etkileyebilir. Belirli standart C ve C++ davranışı ayarları belirtmek daha fazla yolu için bkz [/Zc](zc-conformance.md) derleyici seçeneği. Ek C++ Standart uyumluluk ayarları için bkz [/ permissive-](permissive-standards-conformance.md) ve [/Std](std-specify-language-standard-version.md) derleyici seçenekleri.

Visual C++ ile uyumluluk sorunları hakkında daha fazla bilgi için bkz. [standart dışı davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Gezinti bölmesinde **yapılandırma özellikleri** > **C/C++** > **dil**.

1. Değiştirme **dil uzantılarını devre dışı** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableLanguageExtensions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Seçenekleri](compiler-options.md)<br/>
[/Zc (Uyumluluk)](zc-conformance.md)<br/>
[/permissive- (Standartlara uyumluluk)](permissive-standards-conformance.md)<br/>
[/std (Dil Standart Sürümünü Belirt)](std-specify-language-standard-version.md)<br/>
