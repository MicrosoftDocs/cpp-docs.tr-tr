---
title: /SWAPRUN (Bağlayıcı Çıktısını Takas Dosyasına Yükle)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.SwapRunFromNet
- /swaprun
- VC.Project.VCLinkerTool.SwapRunFromCD
helpviewer_keywords:
- -SWAPRUN linker option
- files [C++], LINK
- LINK tool [C++], output
- linker [C++], copying output to swap file
- swap file for linker output
- output files, linker
- /SWAPRUN linker option
- SWAPRUN linker option
ms.assetid: 4a1e7f46-4399-4161-8dfc-d6a71beaf683
ms.openlocfilehash: a21b58cf997c64f099ce3b54f915415243fa9124
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50609917"
---
# <a name="swaprun-load-linker-output-to-swap-file"></a>/SWAPRUN (Bağlayıcı Çıktısını Takas Dosyasına Yükle)

```
/SWAPRUN:{NET|CD}
```

## <a name="remarks"></a>Açıklamalar

Swaprun seçeneği işletim sistemine ilk kopyayı çıktısını bir takas dosyasına ve ardından buradan çalıştırmadan söyler. Bu bir Windows NT 4.0 (ve üzeri) güvenlik özelliğidir.

NET belirtilirse, işletim sistemi önce ikili görüntüyü ağdan bir takas dosyasına kopyalama ve buradan yükleyebilirsiniz. Bu seçenek uygulamaları ağ üzerinde çalıştırmak için yararlıdır. CD belirtildiğinde işletim sistemi çıkarılabilir diskteki görüntüyü sayfa dosyasına kopyalayın ve ardından yükler.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **sistem** özellik sayfası.

1. Aşağıdaki özelliklerden birini değiştirin:

   - **CD'den takasla Çalıştır**

   - **Ağdan takasla Çalıştır**

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromCD%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromNet%2A> özellikleri.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)