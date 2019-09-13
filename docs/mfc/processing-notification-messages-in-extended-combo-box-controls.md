---
title: Genişletilmiş Birleşik Giriş Kutusu Denetimlerinde Bildirim İletilerini İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- extended combo boxes [MFC], notifications
- notifications [MFC], extended combo box controls
ms.assetid: 4e442758-d054-4746-bb1a-6ff84accb127
ms.openlocfilehash: 044cef644f746f7cb70944805882bd8e2f2806b4
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70908105"
---
# <a name="processing-notification-messages-in-extended-combo-box-controls"></a>Genişletilmiş Birleşik Giriş Kutusu Denetimlerinde Bildirim İletilerini İşleme

Kullanıcılar Genişletilmiş Birleşik giriş kutusuyla etkileşim kurarken, denetim (),`CComboBoxEx`ana penceresine (genellikle bir görünüm veya iletişim nesnesi) bildirim iletileri gönderir. Yanıtta bir şey yapmak istiyorsanız bu iletileri işleyin. Örneğin, Kullanıcı açılır listeyi etkinleştirdiğinde veya denetimin düzenleme kutusunda tıkladığı zaman, CBEN_BEGINEDIT bildirimi gönderilir.

Uygulamak istediğiniz iletilerin üst sınıfına bildirim işleyicileri eklemek için [sınıf Sihirbazı](reference/mfc-class-wizard.md) ' nı kullanın.

Aşağıdaki listede, Genişletilmiş Birleşik giriş kutusu denetimi tarafından gönderilen çeşitli bildirimler açıklanmaktadır.

- CBEN_BEGINEDIT, Kullanıcı açılır listeyi etkinleştirdiğinde veya denetimin düzenleme kutusunda tıkladığı zaman gönderilir.

- Bir öğe silindiğinde, CBEN_DELETEITEM gönderilir.

- CBEN_DRAGBEGIN, Kullanıcı denetimin düzenleme bölümünde görüntülenmekte olan öğenin görüntüsünü sürüklemeye başladığında gönderilir.

- CBEN_ENDEDIT, Kullanıcı düzenleme kutusu içinde bir işlemi sonlandırmışsa veya denetimin açılan listesinden bir öğe seçtikten sonra gönderilir.

- Geri çağırma öğesiyle ilgili görüntü bilgilerini almak için CBEN_GETDISPINFO gönderildi.

- CBEN_INSERTITEM, denetime yeni bir öğe yerleştirildiğinde gönderilir.

## <a name="see-also"></a>Ayrıca bkz.

[CComboBoxEx Kullanma](../mfc/using-ccomboboxex.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
