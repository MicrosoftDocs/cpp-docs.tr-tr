---
title: Değiştirilen ATL DHTML denetimini test etme
ms.date: 11/06/2018
helpviewer_keywords:
- HTML controls, testing
- testing controls
- DHTML controls, testing
ms.assetid: 42316118-9433-410f-9d8a-0efcc1eff824
ms.openlocfilehash: 55cdaba64ccb95ee5695c082a5e146b1e7dc2cf3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62196580"
---
# <a name="testing-the-modified-atl-dhtml-control"></a>Değiştirilen ATL DHTML denetimini test etme

Şimdi nasıl çalıştığını görmek için yeni denetim deneyin.

## <a name="to-build-and-test-the-modified-control"></a>Derleme ve değiştirilmiş denetim test etmek için

1. Projeyi oluşturmak ve açılır **Test kapsayıcısı**. Bkz: [Test kapsayıcısı ile test etme özellikleri ve olayları](../mfc/testing-properties-and-events-with-test-container.md) erişim hakkında daha fazla bilgi için **Test kapsayıcısı**.

   Tüm eklediğiniz düğmeleri göstermek için denetimin boyutunu ayarlayın.

1. HTML değiştirerek eklediğiniz iki düğme inceleyin. Her düğme içinde tanımlanan etiketi taşıyan [ATL DHTML denetimini değiştirme](../atl/modifying-the-atl-dhtml-control.md): **Yenileme** ve **HelloHTML**.

1. Nasıl çalıştıklarını görmeniz için iki yeni düğme test edin.

Artık kullanıcı Arabirimi parçası olmayan yöntemleri test edin.

1. Denetimin kenarlık etkin şekilde vurgulayın.

1. Üzerinde **denetimi** menüsünde seçin **çağırma yöntemleri**.

   Etiketli yöntemlerle **yöntem adı** kapsayıcı çağırabileceğiniz yöntemler şunlardır: `MethodInvoked` ve `GoToURL`. Tüm diğer yöntemler kullanıcı Arabirimi tarafından denetlenir.

1. Çağırmak ve bir yöntem Seç **Invoke** yöntemin ileti kutusu görüntülemek için veya gitmek için `www.microsoft.com`.

1. İçinde **çağırma yöntemleri** iletişim kutusunda **Kapat**.

Çeşitli öğeler ve bir ATL DHTML denetimini oluşturan dosyaları hakkında daha fazla bilgi için bkz: [DHTML denetim projesinin öğelerini tanımlama](../atl/identifying-the-elements-of-the-dhtml-control-project.md).

## <a name="see-also"></a>Ayrıca bkz.

[DHTML denetimi için destek](../atl/atl-support-for-dhtml-controls.md)
