---
description: Daha fazla bilgi edinin:/SWAPRUN (bağlayıcı çıktısını takas dosyasına yükle)
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
ms.openlocfilehash: f62d5e32432a2c738b7782c0fbf0cd4fd76a7f9a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230217"
---
# <a name="swaprun-load-linker-output-to-swap-file"></a>/SWAPRUN (Bağlayıcı Çıktısını Takas Dosyasına Yükle)

```
/SWAPRUN:{NET|CD}
```

## <a name="remarks"></a>Açıklamalar

/SWAPRUN seçeneği işletim sistemine ilk olarak bağlayıcı çıkışını bir takas dosyasına kopyalamasını söyler ve sonra görüntüyü oradan çalıştırır. Bu bir Windows NT 4,0 (ve üzeri) özelliğidir.

NET belirtilirse, işletim sistemi ilk olarak ağdan ikili görüntüyü bir takas dosyasına kopyalar ve buradan yükler. Bu seçenek, ağ üzerinden uygulama çalıştırmak için yararlıdır. CD belirtildiğinde, işletim sistemi çıkarılabilir bir diskteki görüntüyü bir sayfa dosyasına kopyalar ve ardından yükler.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Sistem** Özellik sayfasına tıklayın.

1. Aşağıdaki özelliklerden birini değiştirin:

   - **CD 'Den takas Çalıştır**

   - **Ağdan takas çalıştırması**

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromCD%2A> <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromNet%2A> . ve Özellikler.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
