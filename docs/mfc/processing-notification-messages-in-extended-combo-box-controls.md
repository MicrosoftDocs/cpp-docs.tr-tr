---
title: Genişletilmiş Birleşik Giriş Kutusu Denetimlerinde Bildirim İletilerini İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- extended combo boxes [MFC], notifications
- notifications [MFC], extended combo box controls
ms.assetid: 4e442758-d054-4746-bb1a-6ff84accb127
ms.openlocfilehash: 6a007af9bf92868049edba99943e080d509a40da
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431005"
---
# <a name="processing-notification-messages-in-extended-combo-box-controls"></a>Genişletilmiş Birleşik Giriş Kutusu Denetimlerinde Bildirim İletilerini İşleme

Genişletilmiş Birleşik giriş kutusu, denetimi kullanıcıların etkileşimli olarak (`CComboBoxEx`) üst pencereye bildirim iletilerini gönderen genellikle bir görünüm veya iletişim nesnesi. Yanıt bir şey yapmak istiyorsanız, bu iletileri işler. Örneğin, kullanıcı açılır listede etkinleştirir veya denetimin düzenleme kutusuna tıkladığında CBEN_BEGINEDIT bildirim gönderilir.

Üst sınıf uygulamak istediğiniz bu iletileri için bildirim işleyicileri eklemek için Özellikler penceresini kullanın.

Genişletilmiş Birleşik giriş kutusu denetimi tarafından gönderilen çeşitli bildirimler aşağıdaki listede açıklanmaktadır.

- Kullanıcının açılan listesini etkinleştirir veya denetimin düzenleme kutusuna tıkladığında CBEN_BEGINEDIT gönderilir.

- Bir öğe silindiğinde CBEN_DELETEITEM gönderilir.

- Kullanıcı denetimi düzenleme bölümünde görüntülenen öğe görüntüsü sürükleyerek başladığında CBEN_DRAGBEGIN gönderilir.

- Kullanıcı düzenleme kutusu içine bir işlemini sonlandırdığını veya bir öğe denetimin aşağı açılan listeden seçtiği CBEN_ENDEDIT gönderilir.

- Bir geri çağırma öğesi hakkında bilgi görüntüler alınacak gönderilen CBEN_GETDISPINFO.

- CBEN_INSERTITEM denetiminde yeni bir öğe eklendiğinde gönderilen.

## <a name="see-also"></a>Ayrıca Bkz.

[CComboBoxEx Kullanma](../mfc/using-ccomboboxex.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

