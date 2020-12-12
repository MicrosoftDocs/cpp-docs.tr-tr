---
description: Şu konuda daha fazla bilgi edinin:/LARGEADDRESSAWARE (büyük adresleri Işle)
title: /LARGEADDRESSAWARE (Büyük Adresleri İşle)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.LargeAddressAware
- /largeaddressaware
helpviewer_keywords:
- LARGEADDRESSAWARE linker option
- -LARGEADDRESSAWARE linker option
- /LARGEADDRESSAWARE linker option
ms.assetid: a29756c8-e893-47a9-9750-1f0d25359385
ms.openlocfilehash: 72b2ba20b2ea2b91ecd234497c433bcdd9e9ee42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199577"
---
# <a name="largeaddressaware-handle-large-addresses"></a>/LARGEADDRESSAWARE (Büyük Adresleri İşle)

```
/LARGEADDRESSAWARE[:NO]
```

## <a name="remarks"></a>Açıklamalar

/LARGEADDRESSAWARE seçeneği, bağlayıcıya uygulamanın 2 gigabayt 'tan daha büyük adresler işleyebileceğini söyler. 64 bit derleyicilerde, bu seçenek varsayılan olarak etkindir. Bağlayıcı satırında/LARGEADDRESSAWARE belirtilmemişse, 32 bit derleyicilerde/LARGEADDRESSAWARE: NO etkinleştirilir.

Bir uygulama/LARGEADDRESSAWARE ile bağlanmışsa, DUMPBIN [/Headers](headers.md) bu efekte bilgi görüntüler.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Sistem** Özellik sayfasına tıklayın.

1. **Büyük adresleri etkinleştir** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LargeAddressAware%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
