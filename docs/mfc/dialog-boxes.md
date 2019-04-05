---
title: İletişim Kutuları
ms.date: 11/04/2016
helpviewer_keywords:
- modeless dialog boxes [MFC], MFC dialog boxes
- MFC, dialog boxes
- modal dialog boxes [MFC], MFC dialog boxes
- CDialog class [MFC], MFC dialog boxes
- MFC dialog boxes
ms.assetid: e4feea1a-8360-4ccb-9b84-507f1ccd9ef3
ms.openlocfilehash: 32a8f8784459338131d4893f25d8798f8031b68b
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58778500"
---
# <a name="dialog-boxes"></a>İletişim Kutuları

Windows uygulamaları, sık iletişim kutusu kullanıcıyı ile iletişim kurar. Sınıf [CDialog](../mfc/reference/cdialog-class.md) iletişim kutuları yönetme, Visual C++ iletişim kutusu Düzenleyicisi iletişim kutuları tasarlama ve oluşturma iletişim şablonu kaynaklarına kolaylaştırır ve kod sihirbazları başlatma işlemini basitleştirmek için bir arabirim sağlar ve Denetimler iletişim kutusunda ve kullanıcı tarafından girilen değerleri toplama doğrulanıyor.

İletişim kutuları gibi denetimleri içerir:

- Windows ortak denetimleri gibi kutuları, pushbuttons, liste kutuları, birleşik giriş kutuları, ağaç denetimleri, liste denetimleri ve ilerleme göstergeleri düzenleyin.

- ActiveX denetimleri.

- Kullanıcı çizimli denetimler: iletişim kutusundaki çizmek için sorumlu olan denetimler.

Herhangi bir program parçasını kullanmadan önce iletişim kutusunu kapatmak kullanıcı gerektiren çoğu iletişim kutusu kalıcı, vardır. Ancak kullanıcılar iletişim kutusu açıkken, diğer windows ile çalışmak olanak sağlayan ve kalıcı olmayan iletişim kutuları oluşturmak mümkündür. MFC iletişim kutusu sınıfı ile her iki tür destekler `CDialog`. Denetimleri düzenlenir ve ile oluşturulan bir iletişim şablonunu kaynağı kullanarak yönetilen [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md).

[Özellik sayfaları](../mfc/property-sheets-mfc.md), olarak da bilinen sekme iletişim kutuları, farklı iletişim kutusu denetimleri olan "sayfalar" içeren bir iletişim kutusu vardır. Her sayfanın üstündeki "sekmesinde" dosya klasörü vardır. Bu sayfa, tıklayarak bir sekme iletişim kutusunun öne getirir.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Örnek: Bir iletişim kutusunu menü komutu ile görüntüleme](../mfc/example-displaying-a-dialog-box-via-a-menu-command.md)

- [Framework'te iletişim kutusu bileşenleri](../mfc/dialog-box-components-in-the-framework.md)

- [Kalıcı ve kalıcı olmayan iletişim kutuları](../mfc/modal-and-modeless-dialog-boxes.md)

- [Özellik bölümleri ve özellik sayfaları](../mfc/property-sheets-and-property-pages-mfc.md) iletişim kutusunda

- [İletişim kaynağını oluşturma](../mfc/creating-the-dialog-resource.md)

- [Kod sihirbazları ile iletişim kutusu sınıfı oluşturma](../mfc/creating-a-dialog-class-with-code-wizards.md)

- [Bir iletişim kutusunun yaşam döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

- [İletişim kutusu veri değişimi (DDX) ve doğrulama (DDV)](../mfc/dialog-data-exchange-and-validation.md)

- [İletişim kutusundaki denetimlere tür kullanımı uyumlu erişim](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)

- [Windows iletilerini sınıfınıza eşleme](../mfc/mapping-windows-messages-to-your-class.md)

- [Yaygın Olarak Geçersiz Kılınan Üye İşlevleri](../mfc/commonly-overridden-member-functions.md)

- [Yaygın Olarak Eklenen Üye İşlevleri](../mfc/commonly-added-member-functions.md)

- [Ortak iletişim kutusu sınıfları](../mfc/common-dialog-classes.md)

- [Ole'deki iletişim kutuları](../mfc/dialog-boxes-in-ole.md)

- Bir iletişim kutusu, kullanıcı arabirimi olan bir uygulama oluşturun: bkz [CMNCTRL1](../overview/visual-cpp-samples.md) veya [CMNCTRL2](../overview/visual-cpp-samples.md) örnek programlar. Uygulama Sihirbazı'nı bu seçeneği de sağlar.

- [Örnekler](../mfc/dialog-sample-list.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı Arabirim Öğeleri](../mfc/user-interface-elements-mfc.md)
