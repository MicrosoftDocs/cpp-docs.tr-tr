---
title: -VERSION (sürüm bilgileri) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.Version
- /version
dev_langs:
- C++
helpviewer_keywords:
- -VERSION linker option
- Version Information linker option
- version numbers, specifying in .exe
- /VERSION linker option
- VERSION linker option
ms.assetid: b86d0e86-dca6-4316-aee2-d863ccb9f223
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 092fd11d7bf062afb59c9b33d620624c63b5e01f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378996"
---
# <a name="version-version-information"></a>/VERSION (Sürüm Bilgileri)
```  
/VERSION:major[.minor]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 burada:  
  
 *Ana*ve *küçük*  
 .Exe veya .dll dosyasının üstbilgisinde istediğiniz sürüm numarası.  
  
## <a name="remarks"></a>Açıklamalar  
 / VERSION seçenek .exe veya .dll dosyasının üstbilgisinde bir sürüm numarası koymak için bağlayıcı söyler. DUMPBIN kullanmak [/HEADERS](../../build/reference/headers.md) görüntü sürümü alanın/VERSION etkisini görmek için isteğe bağlı üstbilgi değerleri görmek için.  
  
 *Ana* ve *küçük* bağımsız değişkenler 0 ile 65.535 aralıktaki ondalık sayılar. Varsayılan değer 0,0 sürümüdür.  
  
 / VERSION ile belirtilen bilgileri dosya Gezgini'nde özelliklerini görüntülerken bir uygulama için görüntülenen sürüm bilgileri etkilemez. Bu sürüm bilgileri uygulama oluşturmak için kullanılan bir kaynak dosyasından gelir. Bkz: [sürüm bilgileri Düzenleyicisi](../../windows/version-information-editor.md) daha fazla bilgi için.  
  
 Bir sürüm numarası eklemek için başka bir yolu [sürüm](../../build/reference/version-c-cpp.md) modül tanımlama deyimi.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **genel** özellik sayfası.  
  
4.  Değiştirme **sürüm** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Version%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)