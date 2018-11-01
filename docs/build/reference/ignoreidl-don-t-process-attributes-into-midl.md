---
title: / IGNOREIDL (Don&#39;MIDL t işlem öznitelikler)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.IgnoreEmbeddedIDL
- /ignoreidl
helpviewer_keywords:
- IGNOREIDL linker option
- -IGNOREIDL linker option
- /IGNOREIDL linker option
ms.assetid: 29514098-6a1c-4317-af2f-1dc268972780
ms.openlocfilehash: f6c5fcbae52ed695f2d0c389607ac4231f069788
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534361"
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

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreEmbeddedIDL%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)<br/>
[/IDLOUT (MIDL Çıktı Dosyalarını Adlandır)](../../build/reference/idlout-name-midl-output-files.md)<br/>
[/TLBOUT (.TLB Dosyası Adlandır)](../../build/reference/tlbout-name-dot-tlb-file.md)<br/>
[/MIDL (MIDL Komut Satırı Seçeneklerini Belirt)](../../build/reference/midl-specify-midl-command-line-options.md)<br/>
[Öznitelikli Program Derleme](../../windows/building-an-attributed-program.md)