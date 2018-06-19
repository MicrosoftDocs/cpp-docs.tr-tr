---
title: -NATVIS (Natvis eklemek için PDB) | Microsoft Docs
ms.date: 08/10/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /natvis
- VC.Project.VCLinkerTool.ImportLIbrary
dev_langs:
- C++
helpviewer_keywords:
- NATVIS linker option
- /NATVIS linker option
- -NATVIS linker option
- Add Natvis file to PDB
ms.assetid: 8747fc0c-701a-4796-bb4d-818ab4465cca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3bce34095aec1558d2466447770a8ac4c46528f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377108"
---
# <a name="natvis-add-natvis-to-pdb"></a>/ NATVIS (Natvis PDB için ekleme)
  
> / NATVIS:*dosya adı*  
  
## <a name="parameters"></a>Parametreler  
  
*Dosya adı*  
PDB dosyasına eklemek için bir Natvis dosyası. Natvis dosyasında hata ayıklayıcı görselleştirmeleri PDB katıştırır.  
  
## <a name="remarks"></a>Açıklamalar  
  
/NATVIS seçeneği Natvis dosyasında tanımlanan hata ayıklayıcı görselleştirmeleri katıştırır *filename* bağlantı tarafından oluşturulan PDB dosyasına. Bu görsel .natvis dosya bağımsız olarak görüntülenecek hata ayıklayıcı sağlar. Oluşturulan PDB dosyasında birden fazla Natvis dosya eklemek için birden çok /NATVIS seçeneklerini kullanabilirsiniz.  
  
BAĞLANTI yok sayıyor /NATVIS PDB dosyası kullanılarak oluşturulduğunda değil, bir [/DEBUG](../../build/reference/debug-generate-debug-info.md) seçeneği. Oluşturma ve .natvis dosyalarının kullanılması hakkında daha fazla bilgi için bkz: [Visual Studio Hata Ayıklayıcısı'ndaki yerel nesnelerin özel görünümlerini oluşturma](/visualstudio/debugger/create-custom-views-of-native-objects).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Seçin **komut satırı** özellik sayfasında **bağlayıcı** klasör.  
  
3.  /NATVIS seçeneğine eklemek **ek seçenekler** metin kutusu.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bu seçenek programatik eşdeğeri yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
  
[Visual Studio Hata Ayıklayıcısı'ndaki yerel nesnelerin özel görünümlerini oluşturma](/visualstudio/debugger/create-custom-views-of-native-objects)  
[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)  
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)