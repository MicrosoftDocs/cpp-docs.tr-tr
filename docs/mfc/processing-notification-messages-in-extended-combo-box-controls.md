---
title: Genişletilmiş Birleşik Giriş Kutusu Denetimlerinde Bildirim İletilerini İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- extended combo boxes [MFC], notifications
- notifications [MFC], extended combo box controls
ms.assetid: 4e442758-d054-4746-bb1a-6ff84accb127
ms.openlocfilehash: 58a7c5ec36807489d24014055c39775b4552be03
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620993"
---
# <a name="processing-notification-messages-in-extended-combo-box-controls"></a>Genişletilmiş Birleşik Giriş Kutusu Denetimlerinde Bildirim İletilerini İşleme

Kullanıcılar Genişletilmiş Birleşik giriş kutusuyla etkileşim kurarken, denetim (), `CComboBoxEx` ana penceresine (genellikle bir görünüm veya iletişim nesnesi) bildirim iletileri gönderir. Yanıtta bir şey yapmak istiyorsanız bu iletileri işleyin. Örneğin, Kullanıcı açılır listeyi etkinleştirdiğinde veya denetimin düzenleme kutusunda tıkladığı zaman CBEN_BEGINEDIT bildirimi gönderilir.

Uygulamak istediğiniz iletilerin üst sınıfına bildirim işleyicileri eklemek için [sınıf Sihirbazı](reference/mfc-class-wizard.md) ' nı kullanın.

Aşağıdaki listede, Genişletilmiş Birleşik giriş kutusu denetimi tarafından gönderilen çeşitli bildirimler açıklanmaktadır.

- Kullanıcı açılır listeyi etkinleştirdiğinde veya denetimin düzenleme kutusunda tıkladığı zaman CBEN_BEGINEDIT gönderilir.

- Bir öğe silindiğinde CBEN_DELETEITEM gönderilir.

- Kullanıcı, denetimin düzenleme bölümünde görüntülenmekte olan öğenin görüntüsünü sürüklemeye başladığında gönderilir CBEN_DRAGBEGIN.

- Kullanıcı düzenleme kutusu içinde bir işlem sonuçlandırtığında veya denetimin açılan listesinden bir öğe seçtiğinde CBEN_ENDEDIT gönderilir.

- Geri çağırma öğesiyle ilgili görüntü bilgilerini almak için CBEN_GETDISPINFO gönderildi.

- Denetime yeni bir öğe yerleştirildiğinde CBEN_INSERTITEM gönderilir.

## <a name="see-also"></a>Ayrıca bkz.

[CComboBoxEx Kullanma](using-ccomboboxex.md)<br/>
[Denetimler](controls-mfc.md)
