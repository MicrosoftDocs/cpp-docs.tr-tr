---
description: Daha fazla bilgi edinin:/FIXED (sabit temel adres)
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
ms.openlocfilehash: 08b781b7fbeaf43d6c7e0e82da7bf8319cf77953
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192063"
---
# <a name="fixed-fixed-base-address"></a>/FIXED (Sabit Temel Adres)

```
/FIXED[:NO]
```

## <a name="remarks"></a>Açıklamalar

İşletim sistemine programı yalnızca tercih edilen temel adresinde yüklemeyi söyler. Tercih edilen temel adres kullanılamıyorsa, işletim sistemi dosyayı yüklemez. Daha fazla bilgi için bkz. [/Base (temel adres)](base-base-address.md).

/FIXED: NO bir DLL için varsayılan ayardır ve/FIXED diğer proje türleri için varsayılan ayardır.

/FIXED belirtildiğinde, bağlantı programda bir konum değiştirme bölümü oluşturmaz. Çalışma zamanında, işletim sistemi belirtilen adresteki programı yükleyemezse bir hata iletisi yayınlar ve programı yüklemez.

Programda bir konum değiştirme bölümü oluşturmak için/FIXED: NO belirtin.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörünü seçin.

1. **Komut satırı** özellik sayfasını seçin.

1. Seçenek adı ve ayarı **ek seçenekler** kutusuna yazın.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
