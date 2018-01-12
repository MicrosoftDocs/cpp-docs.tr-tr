---
title: "Nasıl yapılır: durum çubuğunda komut bilgilerini görüntüleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- prompts [MFC]
- displaying command status [MFC]
- status bars [MFC], message area
- status bars [MFC], displaying command information
ms.assetid: de895cbe-61ee-46bf-9787-76b247527d6d
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: da836f48592d97b3526c568eb9d9a830428f53a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-display-command-information-in-the-status-bar"></a>Nasıl Yapılır: Durum Çubuğunda Komut Bilgilerini Görüntüleme
Uygulamanızın çatıyı oluşturmak için Uygulama Sihirbazı'nı çalıştırdığınızda, araç çubuğu ve durum çubuğu destekler. Uygulama Sihirbazı'nda tek bir seçeneği her ikisi de destekler. Durum çubuğu bulunduğunda, kullanıcı işaretçiyi menülerde öğeler üzerinde hareket ederken uygulama otomatik olarak yararlı geri bildirim sağlar. Menü öğesi vurgulanmış, uygulama bir istem dizesi durum çubuğunda otomatik olarak görüntüler. Örneğin, ne zaman kullanıcı işaretçiyi üzerine taşıdığında **Kes** komutunu **Düzenle** menüsünde durum çubuğu durum çubuğu ileti alanına "Seçimi kesip Pano'ya yerleştirir" görüntülenebilir. İstemi menü öğesi amacını anlamasına yardımcı olur. Kullanıcı bir araç çubuğu düğmesini tıklattığında de çalışır.  
  
 Bu durum çubuğu Yardım için program Ekle menü öğeleri için komut istemi dizeleri tanımlayarak ekleyebilirsiniz. Bunu yapmak için menü öğesini menü Düzenleyicisi'nde özelliklerini düzenlerken komut istemi dizeleri girin. Tanımladığınız dizeleri uygulama kaynak dosyasında depolanır; Bunlar açıklayan komutları olarak aynı kimlikleri sahiptirler.  
  
 Varsayılan olarak, Uygulama Sihirbazı'nı ekler `AFX_IDS_IDLEMESSAGE`, yeni iletiler için bekliyor. program kurduğunuzda gösterilen bir standart "Hazır" ileti kimliği. Uygulama Sihirbazı'nda Context-Sensitive yardımcı seçeneğini belirtirseniz, ileti "Yardım için F1 tuşuna basın için." değiştirilir  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İleti İşleme ve Eşleme](../mfc/message-handling-and-mapping.md)

