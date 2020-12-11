---
description: 'Hakkında daha fazla bilgi edinin: Genişletilmiş Birleşik giriş kutusu denetimlerinde bildirim Iletilerini Işleme'
title: Genişletilmiş Birleşik Giriş Kutusu Denetimlerinde Bildirim İletilerini İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- extended combo boxes [MFC], notifications
- notifications [MFC], extended combo box controls
ms.assetid: 4e442758-d054-4746-bb1a-6ff84accb127
ms.openlocfilehash: ef004c3649ce78b24aa1c77aa90488ae6391dcca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154818"
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
