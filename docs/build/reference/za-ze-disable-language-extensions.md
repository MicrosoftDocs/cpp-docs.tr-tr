---
description: Daha fazla bilgi edinin:/za,/Ze (dil uzantılarını devre dışı bırak)
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
ms.openlocfilehash: 98b3d3a36a0aaf0731e6fe6ded06844f7f1e4213
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263185"
---
# <a name="za-ze-disable-language-extensions"></a>/Za, /Ze (Dil Uzantılarını Devre Dışı Bırak)

**/Za** derleyici SEÇENEĞI, ANSI c89/ISO C90 ile uyumlu olmayan C 'ye Microsoft uzantılarına yönelik hataları devre dışı bırakır ve yayar. Kullanım dışı **/ze** derleyici seçeneği Microsoft uzantılarını sunar. Microsoft uzantıları varsayılan olarak etkinleştirilmiştir.

## <a name="syntax"></a>Syntax

> **/Za**\
> **/Ze**

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Kod C++ olarak derlendiğinde **/za** kullanılması önerilmez. **/Ze** seçeneği, davranışı varsayılan olarak açık olduğundan kullanım dışıdır. Kullanım dışı bırakılan derleyici seçeneklerinin bir listesi için bkz. [kullanım dışı ve kaldırılmış derleyici seçenekleri](compiler-options-listed-by-category.md#deprecated-and-removed-compiler-options).

Microsoft C/C++ derleyicisi, C kodunun derlemesini iki şekilde destekler:

- Derleyici, bir kaynak dosyada *. c* uzantısı olduğunda veya [/TC](tc-tp-tc-tp-specify-source-file-type.md) veya [/TC](tc-tp-tc-tp-specify-source-file-type.md) seçeneği belirtildiğinde varsayılan olarak C derleme modunu kullanır. C derleyicisi, varsayılan olarak C diline Microsoft uzantıları sağlayan bir c89/C90 derleyicisidir. Belirli uzantılar hakkında daha fazla bilgi için bkz. [C ve C++ Için Microsoft uzantıları](microsoft-extensions-to-c-and-cpp.md). Hem C derlemesi hem de **/za** seçeneği belirtildiğinde, c derleyicisi kesinlikle c89/C90 standardına uygundur. Derleyici, Microsoft genişletilmiş anahtar sözcüklerini basit tanımlayıcılar olarak değerlendirir, diğer Microsoft uzantılarını devre dışı bırakır ve C programları için önceden tanımlanmış [ \_ \_ stdc \_ \_ ](../../preprocessor/predefined-macros.md) makrosunu otomatik olarak tanımlar.

- Derleyici, C++ derleme modunda C kodu derleyebilir. Bu davranış, *. c* uzantısına sahip olmayan ve [/TP](tc-tp-tc-tp-specify-source-file-type.md) veya [/TP](tc-tp-tc-tp-specify-source-file-type.md) seçeneği belirtildiğinde kaynak dosyaları için varsayılan seçenektir. C++ derleme modunda, derleyici ISO C99 ve C11 standartlarının C++ standardına dahil olan parçalarını destekler. Neredeyse tüm C kodları da geçerli bir C++ kodudur. Az sayıda C anahtar sözcüğü ve kod yapıları geçerli C++ kodu değildir veya C++ ' da farklı şekilde yorumlanır. Derleyici, bu durumlarda C++ standardına göre davranır. C++ derleme modunda, **/za** seçeneği beklenmeyen davranışlara neden olabilir ve önerilmez.

Diğer derleyici seçenekleri derleyicinin standartlara uygunluğu nasıl güvence altına almasını etkileyebilir. Belirli standart C ve C++ davranış ayarlarını belirtme yolları için [/ZC](zc-conformance.md) derleyici seçeneğine bakın. Ek C++ standart uyumluluk ayarları için [/Permissive-](permissive-standards-conformance.md) ve [/STD](std-specify-language-standard-version.md) derleyici seçeneklerine bakın.

Visual C++ uygunluk sorunları hakkında daha fazla bilgi için bkz. [Standart olmayan davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. Gezinti bölmesinde, **yapılandırma özellikleri**  >  **C/C++**  >  **dili**' ni seçin.

1. **Dil uzantılarını devre dışı bırak** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableLanguageExtensions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici seçenekleri](compiler-options.md)<br/>
[/Zc (Uyumluluk)](zc-conformance.md)<br/>
[/permissive- (Standartlara uyumluluk)](permissive-standards-conformance.md)<br/>
[/STD (dil standart sürümünü belirt)](std-specify-language-standard-version.md)<br/>
