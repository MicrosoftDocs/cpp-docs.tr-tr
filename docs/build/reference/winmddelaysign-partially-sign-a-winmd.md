---
title: "-WINMDDELAYSIGN (kısmen imzala winmd) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.WINMDDelaySign
dev_langs: C++
ms.assetid: 445cd602-62cb-400a-8e3a-4beb6572724d
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 18f168c9a3faf4a6bc2676e142a35ee6314db391
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)