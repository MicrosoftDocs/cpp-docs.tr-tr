---
title: -IGNOREIDL (Don&#39;MIDL t işlem öznitelikler) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.IgnoreEmbeddedIDL
- /ignoreidl
dev_langs:
- C++
helpviewer_keywords:
- IGNOREIDL linker option
- -IGNOREIDL linker option
- /IGNOREIDL linker option
ms.assetid: 29514098-6a1c-4317-af2f-1dc268972780
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7014440c3479016c89b774f9a80cc03fc4b5d4c3
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45708233"
---
# <a name="ignoreidl-don39t-process-attributes-into-midl"></a>/ IGNOREIDL (Don&#39;MIDL t işlem öznitelikler)

```
/IGNOREIDL
```

## <a name="remarks"></a>Açıklamalar

/ Ignoreıdl seçeneği herhangi bir belirtir [IDL öznitelikleri](../../windows/idl-attributes.md) kaynakta kod .idl dosyasına işlenmemesi.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **katıştırılmış IDL** özellik sayfası.

1. Değiştirme **gömülü IDL'yi Yoksay** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreEmbeddedIDL%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)<br/>
[/ IDLOUT (MIDL çıktı dosyalarının adını)](../../build/reference/idlout-name-midl-output-files.md)
 [ /tlbout (adı. TLB dosyası)](../../build/reference/tlbout-name-dot-tlb-file.md)
[/MIDL (MIDL komut satırı seçeneklerini belirt)](../../build/reference/midl-specify-midl-command-line-options.md)
[öznitelikli Program derleme](../../windows/building-an-attributed-program.md)