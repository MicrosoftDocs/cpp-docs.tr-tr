---
title: Değiştirilen ATL DHTML denetimini test etme
ms.date: 11/06/2018
helpviewer_keywords:
- HTML controls, testing
- testing controls
- DHTML controls, testing
ms.assetid: 42316118-9433-410f-9d8a-0efcc1eff824
ms.openlocfilehash: 99f55807a7da647af0961f73c600ae0e31166cdc
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51330976"
---
# <a name="testing-the-modified-atl-dhtml-control"></a>Değiştirilen ATL DHTML denetimini test etme

Şimdi nasıl çalıştığını görmek için yeni denetim deneyin.

## <a name="to-build-and-test-the-modified-control"></a>Derleme ve değiştirilmiş denetim test etmek için

1. Projeyi oluşturmak ve açılır **Test kapsayıcısı**. Bkz: [Test kapsayıcısı ile test etme özellikleri ve olayları](../mfc/testing-properties-and-events-with-test-container.md) erişim hakkında daha fazla bilgi için **Test kapsayıcısı**.

   Tüm eklediğiniz düğmeleri göstermek için denetimin boyutunu ayarlayın.

1. HTML değiştirerek eklediğiniz iki düğme inceleyin. Her düğme içinde tanımlanan etiketi taşıyan [ATL DHTML denetimini değiştirme](../atl/modifying-the-atl-dhtml-control.md): **Yenile** ve **HelloHTML**.

1. Nasıl çalıştıklarını görmeniz için iki yeni düğme test edin.

Artık kullanıcı Arabirimi parçası olmayan yöntemleri test edin.

1. Denetimin kenarlık etkin şekilde vurgulayın.

1. Üzerinde **denetimi** menüsünde seçin **çağırma yöntemleri**.

   Etiketli yöntemlerle **yöntem adı** kapsayıcı çağırabileceğiniz yöntemler şunlardır: `MethodInvoked` ve `GoToURL`. Tüm diğer yöntemler kullanıcı Arabirimi tarafından denetlenir.

1. Çağırmak ve bir yöntem Seç **Invoke** yöntemin ileti kutusu görüntülemek için veya gitmek için `www.microsoft.com`.

1. İçinde **çağırma yöntemleri** iletişim kutusunda **Kapat**.

Çeşitli öğeler ve bir ATL DHTML denetimini oluşturan dosyaları hakkında daha fazla bilgi için bkz: [DHTML denetim projesinin öğelerini tanımlama](../atl/identifying-the-elements-of-the-dhtml-control-project.md).

## <a name="see-also"></a>Ayrıca Bkz.

[DHTML denetimi için destek](../atl/atl-support-for-dhtml-controls.md)
