---
title: Genişletilmiş Birleşik giriş kutusu denetimlerinde bildirim iletilerini işleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- extended combo boxes [MFC], notifications
- notifications [MFC], extended combo box controls
ms.assetid: 4e442758-d054-4746-bb1a-6ff84accb127
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a2ea37fb8724a6427e287f1ebef23344662dcb34
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382797"
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

