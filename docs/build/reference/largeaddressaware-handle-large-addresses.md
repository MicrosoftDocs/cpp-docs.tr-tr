---
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
ms.openlocfilehash: 6a83ac89c6ddf14885107193b32d9b7fe7853659
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543061"
---
# <a name="largeaddressaware-handle-large-addresses"></a>/LARGEADDRESSAWARE (Büyük Adresleri İşle)

```
/LARGEADDRESSAWARE[:NO]
```

## <a name="remarks"></a>Açıklamalar

/ Largeaddressaware seçeneği, bağlayıcıya uygulamanın 2 gigabayttan büyük adresleri işleyebileceğini bildirir. 64-bit derleyiciler bu seçenek varsayılan olarak etkindir. / Largeaddressaware bağlayıcı satırında aksi belirtilmediği takdirde, 32-bit derleyicilerde: No etkinleştirilir.

/ Largeaddressaware ile DUMPBIN uygulamanın bağlı olduğu [OPTIONAL](../../build/reference/headers.md) belirlememişse bu bağlamda bilgileri görüntüler.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **sistem** özellik sayfası.

1. Değiştirme **büyük adresleri etkinleştir** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LargeAddressAware%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)