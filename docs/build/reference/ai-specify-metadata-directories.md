---
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
ms.openlocfilehash: 3633cfe34a4f9c627f84cf401cb559f02f8c8229
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273228"
---
# <a name="ai-specify-metadata-directories"></a>/AI (Meta Veri Dizinlerini Belirt)

Geçirilen dosya başvurularını çözümlemek için derleyicinin arama yapacağı dizini belirtir `#using` yönergesi.

## <a name="syntax"></a>Sözdizimi

> **/AI**_dizini_

## <a name="arguments"></a>Arguments

*Dizin*<br/>
Derleyicinin arama yapacağı dizin veya yol.

## <a name="remarks"></a>Açıklamalar

Yalnızca bir dizine geçilebilir bir **/AI** çağırma. Bir tane belirtin **/AI** seçeneği, derleyicinin arama yapmasını istediğiniz her bir yol. Örneğin, derleyici arama yoluna hem C:\Project\Meta hem de C:\Common\Meta eklemek için `#using` yönergeleri ekleme `/AI"C:\Project\Meta" /AI"C:\Common\Meta"` derleyici komut satırına veya her dizine eklemek **ek # dizinleri using** Visual Studio özelliği.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **genel** özellik sayfası.

1. Değiştirme **ek # dizinleri using** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalUsingDirectories%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[#using yönergesi](../../preprocessor/hash-using-directive-cpp.md)
