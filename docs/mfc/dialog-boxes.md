---
title: "İletişim kutuları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- modeless dialog boxes [MFC], MFC dialog boxes
- MFC, dialog boxes
- modal dialog boxes [MFC], MFC dialog boxes
- CDialog class [MFC], MFC dialog boxes
- MFC dialog boxes
ms.assetid: e4feea1a-8360-4ccb-9b84-507f1ccd9ef3
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7e4417fc2d4714a249b04bb0c1d04e5642495835
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="dialog-boxes"></a>İletişim Kutuları
Windows uygulamaları, sık sık iletişim kutuları aracılığıyla kullanıcı ile iletişim kurar. Sınıf [CDialog](../mfc/reference/cdialog-class.md) iletişim kutuları yönetme, Visual C++ iletişim kutusu Düzenleyicisi iletişim kutuları tasarlamak ve iletişim şablonu kaynaklarını oluşturmak kolaylaştırır ve kod sihirbazları başlatma işlemini basitleştirmek için bir arabirim sağlar ve bir iletişim kutusu ve kullanıcı tarafından girilen değerleri toplama denetimlerini doğrulanıyor.  
  
 İletişim kutuları dahil denetimler içerir:  
  
-   Windows ortak denetimleri gibi kutuları, pushbuttons, liste kutuları, birleşik giriş kutuları, ağaç denetimleri, liste denetimleri ve İlerleme göstergesi düzenleyin.  
  
-   ActiveX denetimleri.  
  
-   Sahip tarafından çizilmiş denetimleri: iletişim kutusunda çizim için sorumlu kontrol eder.  
  
 Program, herhangi bir bölümünü kullanmadan önce iletişim kutusunu kapatmak kullanıcının gerektiren kalıcı, çoğu iletişim kutusu. Ancak kullanıcıların iletişim kutusu açıkken diğer windows ile çalışmak izin kalıcı olmayan iletişim kutuları oluşturmak mümkündür. MFC iletişim kutusu sınıfı ile her iki tür destekleyen `CDialog`. Denetimleri düzenlenir ve ile oluşturulan bir iletişim şablonunu kaynağı kullanarak yönetilen [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md).  
  
 [Özellik sayfaları](../mfc/property-sheets-mfc.md), olarak da bilinen sekme iletişim kutuları, farklı iletişim kutusu denetimleri "sayfaların" içeren iletişim kutusu vardır. Her bir sayfa dosya klasörü en üstünde "sekmesinde" vardır. Bu sayfa, bir sekmesini tıklatarak iletişim kutusunun öne getirir.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Örnek: bir iletişim kutusunu menü komutu ile görüntüleme](../mfc/example-displaying-a-dialog-box-via-a-menu-command.md)  
  
-   [Framework'te iletişim kutusu bileşenleri](../mfc/dialog-box-components-in-the-framework.md)  
  
-   [Kalıcı ve kalıcı olmayan iletişim kutuları](../mfc/modal-and-modeless-dialog-boxes.md)  
  
-   [Özellik bölümleri ve özellik sayfaları](../mfc/property-sheets-and-property-pages-mfc.md) iletişim kutusunda  
  
-   [İletişim kaynağını oluşturma](../mfc/creating-the-dialog-resource.md)  
  
-   [Kod sihirbazları ile iletişim kutusu sınıfı oluşturma](../mfc/creating-a-dialog-class-with-code-wizards.md)  
  
-   [İletişim kutusunun yaşam döngüsü](../mfc/life-cycle-of-a-dialog-box.md)  
  
-   [İletişim kutusu veri değişimi (DDX) ve doğrulama (DDV)](../mfc/dialog-data-exchange-and-validation.md)  
  
-   [Bir iletişim kutusundaki denetimlere tür kullanımı uyumlu erişim](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)  
  
-   [Windows iletilerini sınıfınıza eşleme](../mfc/mapping-windows-messages-to-your-class.md)  
  
-   [Yaygın olarak geçersiz kılınan üye işlevleri](../mfc/commonly-overridden-member-functions.md)  
  
-   [Yaygın olarak eklenen üye işlevleri](../mfc/commonly-added-member-functions.md)  
  
-   [Ortak iletişim kutusu sınıfları](../mfc/common-dialog-classes.md)  
  
-   [OLE iletişim kutuları](../mfc/dialog-boxes-in-ole.md)  
  
-   Bir iletişim kutusu, kullanıcı arabirimi olan bir uygulama oluşturun: bkz [CMNCTRL1](../visual-cpp-samples.md) veya [CMNCTRL2](../visual-cpp-samples.md) örnek programlar. Uygulama Sihirbazı'nı bu seçenek de sağlar.  
  
-   [Örnekleri](../mfc/dialog-sample-list.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)
