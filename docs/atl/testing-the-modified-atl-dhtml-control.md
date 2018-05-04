---
title: Değiştirilen ATL DHTML denetimi sınama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HTML controls, testing
- testing controls
- DHTML controls, testing
ms.assetid: 42316118-9433-410f-9d8a-0efcc1eff824
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b140788cd409aa5a11f93689e96fa40c1a167dfe
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="testing-the-modified-atl-dhtml-control"></a>Değiştirilen ATL DHTML denetimi test etme
Şimdi nasıl çalıştığını görmek için yeni denetim deneyin.  
  
#### <a name="to-build-and-test-the-modified-control"></a>Derleme ve değiştirilmiş denetim sınamak için  
  
1.  Projeyi oluşturmak ve Test kapsayıcısında açın. Bkz: [test özellikleri ve olayları Test kapsayıcısı ile](../mfc/testing-properties-and-events-with-test-container.md) Test kapsayıcısı erişim hakkında bilgi için.  
  
     Denetimin tüm eklediğiniz düğmeleri göstermek için yeniden boyutlandırın.  
  
2.  HTML değiştirilerek eklenen iki düğme inceleyin. Her düğme içinde tanımlanan etiketi taşıyan [ATL DHTML denetimi değiştirme](../atl/modifying-the-atl-dhtml-control.md): **yenileme** ve **HelloHTML**.  
  
3.  Nasıl çalıştıklarını görmeniz için iki yeni düğmeler sınayın.  
  
 Artık test kullanıcı arabirimini parçası olmayan yöntemleri.  
  
1.  Kenarlığın etkin şekilde denetim vurgulayın.  
  
2.  Üzerinde **denetim** menüsünde tıklatın **çağırma yöntemleri**.  
  
 Etiketli listesinde yöntemleri **yöntem adı** kapsayıcı çağırabilirsiniz yöntemler şunlardır: `MethodInvoked` ve `GoToURL`. Diğer tüm yöntemleri UI tarafından denetlenir.  
  
1.  Çağırma ve bir yöntem Seç `Invoke` yöntemin ileti kutusu görüntüleme veya www.microsoft.com gidin.  
  
2.  İçinde **çağırma yöntemleri** iletişim kutusu, tıklatın **Kapat**.  
  
 Çeşitli öğeleri ve ATL DHTML denetimi oluşturan dosyaları hakkında daha fazla bilgi için bkz: [DHTML denetimi proje öğelerini tanımlama](../atl/identifying-the-elements-of-the-dhtml-control-project.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DHTML denetimi için destek](../atl/atl-support-for-dhtml-controls.md)

