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
ms.openlocfilehash: bd0b3a46f52ec9b5a292e2f45671523d8c5cdf5e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317555"
---
# <a name="swaprun-load-linker-output-to-swap-file"></a>/SWAPRUN (Bağlayıcı Çıktısını Takas Dosyasına Yükle)

```
/SWAPRUN:{NET|CD}
```

## <a name="remarks"></a>Açıklamalar

Swaprun seçeneği işletim sistemine ilk kopyayı çıktısını bir takas dosyasına ve ardından buradan çalıştırmadan söyler. Bu bir Windows NT 4.0 (ve üzeri) güvenlik özelliğidir.

NET belirtilirse, işletim sistemi önce ikili görüntüyü ağdan bir takas dosyasına kopyalama ve buradan yükleyebilirsiniz. Bu seçenek uygulamaları ağ üzerinde çalıştırmak için yararlıdır. CD belirtildiğinde işletim sistemi çıkarılabilir diskteki görüntüyü sayfa dosyasına kopyalayın ve ardından yükler.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **sistem** özellik sayfası.

1. Aşağıdaki özelliklerden birini değiştirin:

   - **CD'den takasla Çalıştır**

   - **Ağdan takasla Çalıştır**

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromCD%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromNet%2A> özellikleri.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
