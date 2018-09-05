---
title: Değiştirilen ATL DHTML denetimini test etme | Microsoft Docs
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
ms.openlocfilehash: 9730f8ef9bfc89d65ffb89ddbbfe67ce247138e9
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755611"
---
# <a name="testing-the-modified-atl-dhtml-control"></a>Değiştirilen ATL DHTML denetimini test etme

Şimdi nasıl çalıştığını görmek için yeni denetim deneyin.

#### <a name="to-build-and-test-the-modified-control"></a>Derleme ve değiştirilmiş denetim test etmek için

1. Projeyi yeniden derleyin ve Test kapsayıcısında açın. Bkz: [Test kapsayıcısı ile test etme özellikleri ve olayları](../mfc/testing-properties-and-events-with-test-container.md) Test kapsayıcısı erişim hakkında daha fazla bilgi için.

     Tüm eklediğiniz düğmeleri göstermek için denetimin boyutunu ayarlayın.

2. HTML değiştirerek eklediğiniz iki düğme inceleyin. Her düğme içinde tanımlanan etiketi taşıyan [ATL DHTML denetimini değiştirme](../atl/modifying-the-atl-dhtml-control.md): **Yenile** ve **HelloHTML**.

3. Nasıl çalıştıklarını görmeniz için iki yeni düğme test edin.

Artık kullanıcı Arabirimi parçası olmayan yöntemleri test edin.

1. Denetimin kenarlık etkin şekilde vurgulayın.

2. Üzerinde **denetimi** menüsünde tıklatın **çağırma yöntemleri**.

Etiketli yöntemlerle **yöntem adı** kapsayıcı çağırabileceğiniz yöntemler şunlardır: `MethodInvoked` ve `GoToURL`. Tüm diğer yöntemler kullanıcı Arabirimi tarafından denetlenir.

1. ' A tıklayın ve çağırmak için bir yöntem seçin `Invoke` yöntemin ileti kutusu görüntülemek için veya www.microsoft.com gidin.

2. İçinde **çağırma yöntemleri** iletişim kutusu, tıklayın **Kapat**.

Çeşitli öğeler ve bir ATL DHTML denetimini oluşturan dosyaları hakkında daha fazla bilgi için bkz: [DHTML denetim projesinin öğelerini tanımlama](../atl/identifying-the-elements-of-the-dhtml-control-project.md).

## <a name="see-also"></a>Ayrıca Bkz.

[DHTML denetimi için destek](../atl/atl-support-for-dhtml-controls.md)

