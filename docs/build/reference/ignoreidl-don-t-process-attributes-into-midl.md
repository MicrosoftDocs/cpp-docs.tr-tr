---
description: Şu konuda daha fazla bilgi edinin:/ıGNOREıDL (öznitelikleri MıDL 'de&#39;t)
title: /IGNOREıDL (öznitelikleri MıDL 'de&#39;t)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.IgnoreEmbeddedIDL
- /ignoreidl
helpviewer_keywords:
- IGNOREIDL linker option
- -IGNOREIDL linker option
- /IGNOREIDL linker option
ms.assetid: 29514098-6a1c-4317-af2f-1dc268972780
ms.openlocfilehash: c68b3ec2f9bd5607ef523667bcddc68b22d3c34c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199824"
---
# <a name="ignoreidl-don39t-process-attributes-into-midl"></a>/IGNOREıDL (öznitelikleri MıDL 'de&#39;t)

```
/IGNOREIDL
```

## <a name="remarks"></a>Açıklamalar

/IGNOREıDL seçeneği, kaynak kodundaki tüm [IDL özniteliklerinin](../../windows/attributes/idl-attributes.md) bir. IDL dosyasına işlenmediğini belirtir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **KATıŞTıRıLMıŞ IDL** Özellik sayfasına tıklayın.

1. **Gömülü IDL 'Yi yoksay** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreEmbeddedIDL%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)<br/>
[/IDLOUT (MıDL çıktı dosyalarını Adlandır)](idlout-name-midl-output-files.md)<br/>
[/TLHAKKıNDA (ad. TLB dosyası)](tlbout-name-dot-tlb-file.md)<br/>
[/MıDL (MıDL komut satırı seçeneklerini belirt)](midl-specify-midl-command-line-options.md)<br/>
[Öznitelikli Program Oluşturma](../../windows/attributes/cpp-attributes-com-net.md)
