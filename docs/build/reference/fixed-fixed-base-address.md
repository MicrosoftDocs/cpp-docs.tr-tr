---
title: -FIXED (sabit temel adres) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /fixed
- VC.Project.VCLinkerTool.FixedBaseAddress
dev_langs:
- C++
helpviewer_keywords:
- preferred base address for loading program
- /FIXED linker option
- -FIXED linker option
- FIXED linker option
ms.assetid: 929bba5e-b7d8-40ed-943e-056aa3710fc5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 697f6ccfd98059175311cd04e4e82038877b2110
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723404"
---
# <a name="fixed-fixed-base-address"></a>/FIXED (Sabit Temel Adres)

```
/FIXED[:NO]
```

## <a name="remarks"></a>Açıklamalar

İşletim sistemine programı yalnızca tercih edilen temel adresini yük için söyler. Tercih edilen taban adresi kullanılamıyorsa, işletim sistemi dosyayı yüklemez. Daha fazla bilgi için [/Base (Temel adres)](../../build/reference/base-base-address.md).

Bir DLL ve/FIXED için herhangi bir proje türü için varsayılan/FIXED: No varsayılan ayardır.

/ FIXED belirtildiğinde, bağlantı programda bir yerleştirme bölümü oluşturmaz. Çalışma zamanında, işletim sistemi belirtilen adresteki programı yüklenemiyor ise, bir hata iletisi yayınlar ve programı yüklemez.

Programda bir yeniden konumlandırma bölümü oluşturmak için/FIXED: No belirtin.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **bağlayıcı** klasör.

1. Seçin **komut satırı** özellik sayfası.

1. Seçenek adını yazın ve ayarı **ek seçenekler** kutusu.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)