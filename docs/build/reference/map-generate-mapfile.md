---
title: -MAP (eşlem dosyası oluştur) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /map
- VC.Project.VCLinkerTool.MapFileName
- VC.Project.VCLinkerTool.GenerateMapFile
dev_langs:
- C++
helpviewer_keywords:
- mapfiles, creating linker
- generate mapfile linker option
- mapfile linker option
- mapfiles, information about program being linked
- MAP linker option
- -MAP linker option
- mapfiles, specifying file name
- /MAP linker option
ms.assetid: 9ccce53d-4e36-43da-87b0-7603ddfdea63
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10f4b23cf8f1c05fb8bd196dc9a6cd54971b1572
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374677"
---
# <a name="map-generate-mapfile"></a>/MAP (Eşlem Dosyası Oluştur)
```  
/MAP[:filename]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 burada:  
  
 *Dosya adı*  
 Mapfile kullanıcı tanımlı adı. Varsayılan adı değiştirir.  
  
## <a name="remarks"></a>Açıklamalar  
 / Map seçenek bir eşlem dosyası oluşturmak için bağlayıcı söyler.  
  
 Varsayılan olarak, bağlayıcı temel programının adını ve uzantısını .map ile mapfile adları. İsteğe bağlı *filename* bir eşlem için varsayılan adı geçersiz kılmanıza olanak sağlar.  
  
 Bir eşlem bağlantılandırılan program hakkında aşağıdaki bilgileri içeren bir metin dosyasıdır:  
  
-   Temel dosyanın adıdır modül adı  
  
-   Zaman damgası (değil, dosya sistemi) programı dosya üstbilgisinden  
  
-   Programında, her grubun başlangıç adresi gruplarının bir listesini (olarak *bölüm*:*uzaklık*), uzunluk, grup adı ve sınıfı  
  
-   Her adresle genel simgeler listesini (olarak *bölüm*:*uzaklık*), simge adı, düz adres ve simgenin tanımlandığı .obj dosya  
  
-   Giriş noktası (olarak *bölüm*:*uzaklık*)  
  
 [/MAPINFO](../../build/reference/mapinfo-include-information-in-mapfile.md) seçeneği eşlem dosyasına dahil edilecek ek bilgileri belirtir.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **hata ayıklama** özellik sayfası.  
  
4.  Değiştirme **eşleme dosyası oluştur** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateMapFile%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MapFileName%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)