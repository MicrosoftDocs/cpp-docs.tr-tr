---
title: /FIXED (Sabit Temel Adres)
ms.date: 11/04/2016
f1_keywords:
- /fixed
- VC.Project.VCLinkerTool.FixedBaseAddress
helpviewer_keywords:
- preferred base address for loading program
- /FIXED linker option
- -FIXED linker option
- FIXED linker option
ms.assetid: 929bba5e-b7d8-40ed-943e-056aa3710fc5
ms.openlocfilehash: ccb89b7dfed78ddebf73aaf6e2a1a8529b065042
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57423046"
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

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
