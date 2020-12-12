---
description: :/VERSION (sürüm bilgileri) hakkında daha fazla bilgi
title: /VERSION (Sürüm Bilgileri)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.Version
- /version
helpviewer_keywords:
- -VERSION linker option
- Version Information linker option
- version numbers, specifying in .exe
- /VERSION linker option
- VERSION linker option
ms.assetid: b86d0e86-dca6-4316-aee2-d863ccb9f223
ms.openlocfilehash: 7c6a27e4829c4acf66db2887e01a147aceb1c5d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176372"
---
# <a name="version-version-information"></a>/VERSION (Sürüm Bilgileri)

```
/VERSION:major[.minor]
```

## <a name="arguments"></a>Arguments

*büyük* ve *küçük*<br/>
. Exe veya. dll dosyasının üst bilgisinde istediğiniz sürüm numarası.

## <a name="remarks"></a>Açıklamalar

/VERSION seçeneği, bağlayıcının. exe veya. dll dosyasının üstbilgisine bir sürüm numarası vermesini söyler. /Version'in etkisini görmek için Isteğe bağlı üst BILGI DEĞERLERININ görüntü sürümü alanını görmek için DUMPBIN [/Headers](headers.md) komutunu kullanın.

*Büyük* ve *küçük* bağımsız değişkenler 0 ile 65.535 arasında ondalık sayılardır. Varsayılan sürüm 0,0 ' dir.

/VERSION ile belirtilen bilgiler, dosya Gezgini 'nde özelliklerini görüntülediğinizde bir uygulama için görüntülenen sürüm bilgilerini etkilemez. Bu sürüm bilgileri, uygulamayı oluşturmak için kullanılan bir kaynak dosyasından gelir. Daha fazla bilgi için bkz. [sürüm bilgileri Düzenleyicisi](../../windows/version-information-editor.md) .

Sürüm numarası eklemenin başka bir yolu ise [Sürüm](version-c-cpp.md) modülü tanımı deyimidir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Genel** Özellik sayfasına tıklayın.

1. **Version** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Version%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
