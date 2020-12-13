---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: durum çubuğunda komut bilgilerini görüntüleme'
title: 'Nasıl Yapılır: Durum Çubuğunda Komut Bilgilerini Görüntüleme'
ms.date: 11/04/2016
helpviewer_keywords:
- prompts [MFC]
- displaying command status [MFC]
- status bars [MFC], message area
- status bars [MFC], displaying command information
ms.assetid: de895cbe-61ee-46bf-9787-76b247527d6d
ms.openlocfilehash: 568e8d356659d5267e8c4947f2981cd6243a7056
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330217"
---
# <a name="how-to-display-command-information-in-the-status-bar"></a>Nasıl Yapılır: Durum Çubuğunda Komut Bilgilerini Görüntüleme

Uygulamanızın iskektlerini oluşturmak için uygulama Sihirbazı 'Nı çalıştırdığınızda, bir araç çubuğunu ve durum çubuğunu destekleyebilirsiniz. Uygulama sihirbazında yalnızca bir seçenek, her ikisini de destekler. Bir durum çubuğu mevcut olduğunda, Kullanıcı işaretçiyi menülerdeki öğelerin üzerine taşıdıkça uygulama otomatik olarak yararlı geri bildirim sağlar. Menü öğesi vurgulandığında, uygulama otomatik olarak durum çubuğunda bir istem dizesi görüntüler. Örneğin, Kullanıcı işaretçiyi **düzenleme** menüsündeki **Kes** komutunun üzerine taşıdığında, durum çubuğu durum çubuğunun Ileti alanında "seçimi keser ve panoya koyar" seçeneğini gösterebilir. İstem, kullanıcının menü öğesinin amacını anlamasına yardımcı olur. Bu, Kullanıcı bir araç çubuğu düğmesine tıkladığında da kullanılır.

Programa eklediğiniz menü öğeleri için istem dizelerini tanımlayarak, bu durum çubuğu yardımına ekleyebilirsiniz. Bunu yapmak için, menü düzenleyicisinde menü öğesinin özelliklerini düzenlerken istem dizelerini sağlayın. Tanımladığınız dizeler uygulama kaynak dosyasında depolanır; Bunlar, anladıkları komutlarla aynı kimliklere sahiptir.

Varsayılan olarak, uygulama Sihirbazı, program yeni iletileri beklerken görünen standart "hazır" iletisinin KIMLIĞINI **AFX_IDS_IDLEMESSAGE** ekler. Uygulama sihirbazında Context-Sensitive yardım seçeneğini belirtirseniz, ileti "yardım Için F1 'e basın" olarak değiştirilir.

## <a name="see-also"></a>Ayrıca bkz.

[İleti Işleme ve eşleme](message-handling-and-mapping.md)
