---
description: Daha fazla bilgi edinin:/AI (meta veri dizinlerini belirt)
title: /AI (Meta Veri Dizinlerini Belirt)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.AdditionalUsingDirectories
- VC.Project.VCNMakeTool.AssemblySearchPath
- /AI
- VC.Project.VCCLWCECompilerTool.AdditionalUsingDirectories
helpviewer_keywords:
- /AI compiler option [C++]
- AI compiler option [C++]
- -AI compiler option [C++]
ms.assetid: fb9c1846-504c-4a3b-bb39-c8696de32f6f
ms.openlocfilehash: e30711b1da2d41204bf56520d56dd5101f3168b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179752"
---
# <a name="ai-specify-metadata-directories"></a>/AI (Meta Veri Dizinlerini Belirt)

Derleyicinin yönergeye geçirilen dosya başvurularını çözümlemek için arayacaktır bir dizin belirtir `#using` .

## <a name="syntax"></a>Syntax

> **/AI**_dizini_

## <a name="arguments"></a>Arguments

*dizinden*<br/>
Derleyicinin arama yapacağı dizin veya yol.

## <a name="remarks"></a>Açıklamalar

Bir **/AI** çağrısına yalnızca bir dizin geçirilebilir. Derleyicinin aramasını istediğiniz her yol için bir **/AI** seçeneği belirtin. Örneğin, yönergeler için derleyici arama yoluna C:\Project\Meta ve C:\Common\Meta eklemek için `#using` , `/AI"C:\Project\Meta" /AI"C:\Common\Meta"` derleyici komut satırına ekleyin veya her bir dizini Visual Studio 'daki **ek #using dizinleri** özelliğine ekleyin.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **genel** özellik sayfasını seçin.

1. **Ek #using dizinleri** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalUsingDirectories%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)<br/>
[#using yönergesi](../../preprocessor/hash-using-directive-cpp.md)
