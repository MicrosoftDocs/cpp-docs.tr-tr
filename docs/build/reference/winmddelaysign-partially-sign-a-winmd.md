---
title: -WINMDDELAYSIGN (kısmen imzala winmd) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.WINMDDelaySign
dev_langs:
- C++
ms.assetid: 445cd602-62cb-400a-8e3a-4beb6572724d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5c50480fae1f4f3e7421236615d059a642d1074f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="winmddelaysign-partially-sign-a-winmd"></a>/WINMDDELAYSIGN (winmd Dosyasını Kısmen İmzalayın)
Kısmi bir Windows çalışma zamanı meta verileri (.winmd) dosya imzalama dosyasında ortak anahtarı koyarak sağlar.  
  
```  
/WINMDDELAYSIGN[:NO]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Benzer [/delaysign](../../build/reference/delaysign-partially-sign-an-assembly.md) .winmd dosyaya uygulanan bağlayıcı seçeneği. Kullanım **/WINMDDELAYSIGN** .winmd dosyasında yalnızca ortak anahtar koymak istiyorsanız. Varsayılan olarak, bağlayıcı davranır gibi **/WINMDDELAYSIGN:NO** belirtilmiş; diğer bir deyişle, onu winmd dosyasını imzalayın değil.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **bağlayıcı** klasör.  
  
3.  Seçin **Windows meta verileri** özellik sayfası.  
  
4.  İçinde **Windows meta verileri geciktirin** aşağı açılan liste kutusunda, kullanmak istediğiniz seçeneği seçin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)