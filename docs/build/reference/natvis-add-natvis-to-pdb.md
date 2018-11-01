---
title: / NATVIS (Natvıs PDB'ye natvis Ekle)
ms.date: 08/10/2017
f1_keywords:
- /natvis
- VC.Project.VCLinkerTool.ImportLIbrary
helpviewer_keywords:
- NATVIS linker option
- /NATVIS linker option
- -NATVIS linker option
- Add Natvis file to PDB
ms.assetid: 8747fc0c-701a-4796-bb4d-818ab4465cca
ms.openlocfilehash: 475eb377fd55d6118c109f4e03ea1cf624a563f7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50446026"
---
# <a name="natvis-add-natvis-to-pdb"></a>/ NATVIS (Natvıs PDB'ye natvis Ekle)

> / NATVIS:*dosya adı*

## <a name="parameters"></a>Parametreler

*Dosya adı*<br/>
PDB dosyasına eklemek için bir Natvis dosyası. Natvis dosyasında hata ayıklayıcı Görselleştirmelerini PDB katıştırır.

## <a name="remarks"></a>Açıklamalar

Natvis dosyasında tanımlanan hata ayıklayıcı Görselleştirmelerini /NATVIS seçeneği katıştırır *filename* bağlantı tarafından oluşturulmuş bir PDB dosyası içine. Bu, hata ayıklayıcı görselleştirmeleri değiştirebilir .natvis dosyasını bağımsız olarak görüntülemek sağlar. Oluşturulan PDB dosyası içinde birden fazla Natvis dosyası eklemek için birden çok /NATVIS seçeneklerini kullanabilirsiniz.

BAĞLANTI yok sayar /NATVIS bir PDB dosyası kullanılarak oluşturulan değil, bir [/DEBUG](../../build/reference/debug-generate-debug-info.md) seçeneği. Oluşturma ve .natvis dosyaları kullanımı hakkında daha fazla bilgi için bkz. [Visual Studio hata ayıklayıcıda yerel nesnelerin özel görünümlerini oluşturma](/visualstudio/debugger/create-custom-views-of-native-objects).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Seçin **komut satırı** özellik sayfasında **bağlayıcı** klasör.

1. /NATVIS seçeneği ekleyin **ek seçenekler** metin kutusu.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bu seçenek, bir program eşdeğerini yok.

## <a name="see-also"></a>Ayrıca Bkz.

[Visual Studio hata ayıklayıcıda yerel nesnelerin özel görünümlerini oluşturma](/visualstudio/debugger/create-custom-views-of-native-objects)<br/>
[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)