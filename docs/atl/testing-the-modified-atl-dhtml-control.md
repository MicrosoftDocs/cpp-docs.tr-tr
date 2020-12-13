---
description: 'Hakkında daha fazla bilgi edinin: değiştirilen ATL DHTML denetimini test etme'
title: Değiştirilen ATL DHTML denetimini test etme
ms.date: 11/06/2018
helpviewer_keywords:
- HTML controls, testing
- testing controls
- DHTML controls, testing
ms.assetid: 42316118-9433-410f-9d8a-0efcc1eff824
ms.openlocfilehash: a797eab308ad7fb8c5c7b72566ec3d57a169370b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138339"
---
# <a name="testing-the-modified-atl-dhtml-control"></a>Değiştirilen ATL DHTML denetimini test etme

Nasıl çalıştığını görmek için yeni denetiminizi deneyin.

## <a name="to-build-and-test-the-modified-control"></a>Değiştirilen denetimi derlemek ve test etmek için

1. Projeyi yeniden derleyin ve **Test kapsayıcısında** açın. **Test kapsayıcısına** erişme hakkında bilgi için bkz. test [kapsayıcısı Ile özellikleri ve olayları test etme](../mfc/testing-properties-and-events-with-test-container.md) .

   Eklediğiniz tüm düğmeleri göstermek için denetimi yeniden boyutlandırın.

1. HTML 'yi değiştirerek eklediğiniz iki düğmeyi inceleyin. Her düğme [, atl dhtml denetimini değiştirme](../atl/modifying-the-atl-dhtml-control.md)bölümünde belirlediğiniz etiketi kapsar: **Refresh** ve **HelloHTML**.

1. Nasıl çalıştığını görmek için iki yeni düğme test edin.

Şimdi, Kullanıcı arabiriminin parçası olmayan yöntemleri test edin.

1. Denetimi vurgulayın, bu nedenle sınır etkinleştirilir.

1. **Denetim** menüsünde **yöntemleri çağır**' ı seçin.

   Listedeki **Yöntem adı** etiketli Yöntemler kapsayıcının çağırayteme yöntemleridir: `MethodInvoked` ve `GoToURL` . Diğer tüm yöntemler Kullanıcı arabirimi tarafından denetlenir.

1. Çağrılacak yöntemi seçin ve yöntemin ileti kutusunu veya ' ye gitmek için **çağır** ' ı seçin `www.microsoft.com` .

1. **Yöntemleri çağır** Iletişim kutusunda **Kapat**' ı seçin.

ATL DHTML denetimini oluşturan çeşitli öğeler ve dosyalar hakkında daha fazla bilgi edinmek için bkz. [DHTML denetim projesinin öğelerini tanımlama](../atl/identifying-the-elements-of-the-dhtml-control-project.md).

## <a name="see-also"></a>Ayrıca bkz.

[DHTML denetimi desteği](../atl/atl-support-for-dhtml-controls.md)
