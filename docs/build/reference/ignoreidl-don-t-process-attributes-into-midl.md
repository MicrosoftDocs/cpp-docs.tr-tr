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
ms.openlocfilehash: 210778adecd87ffdd5f2702c10106f12bd5a1b79
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820435"
---
# <a name="ignoreidl-don39t-process-attributes-into-midl"></a>/ IGNOREIDL (Don&#39;MIDL t işlem öznitelikler)

```
/IGNOREIDL
```

## <a name="remarks"></a>Açıklamalar

/ Ignoreıdl seçeneği herhangi bir belirtir [IDL öznitelikleri](../../windows/idl-attributes.md) kaynakta kod .idl dosyasına işlenmemesi.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **katıştırılmış IDL** özellik sayfası.

1. Değiştirme **gömülü IDL'yi Yoksay** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreEmbeddedIDL%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)<br/>
[/IDLOUT (MIDL Çıktı Dosyalarını Adlandır)](idlout-name-midl-output-files.md)<br/>
[/TLBOUT (.TLB Dosyası Adlandır)](tlbout-name-dot-tlb-file.md)<br/>
[/MIDL (MIDL Komut Satırı Seçeneklerini Belirt)](midl-specify-midl-command-line-options.md)<br/>
[Öznitelikli Program Derleme](../../windows/building-an-attributed-program.md)
