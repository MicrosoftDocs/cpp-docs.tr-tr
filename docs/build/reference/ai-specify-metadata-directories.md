---
title: -AI (meta veri dizinlerini belirt) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.AdditionalUsingDirectories
- VC.Project.VCNMakeTool.AssemblySearchPath
- /AI
- VC.Project.VCCLWCECompilerTool.AdditionalUsingDirectories
dev_langs:
- C++
helpviewer_keywords:
- /AI compiler option [C++]
- AI compiler option [C++]
- -AI compiler option [C++]
ms.assetid: fb9c1846-504c-4a3b-bb39-c8696de32f6f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 985ff4eb96b904dc9c5b4377b336109b00e06b40
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716599"
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

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

2. Seçin **yapılandırma özellikleri** > **C/C++** > **genel** özellik sayfası.

3. Değiştirme **ek # dizinleri using** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalUsingDirectories%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[#using yönergesi](../../preprocessor/hash-using-directive-cpp.md)