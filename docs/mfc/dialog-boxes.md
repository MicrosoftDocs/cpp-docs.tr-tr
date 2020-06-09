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
ms.openlocfilehash: da6a2eca7c2366e519b9bf2e809b042dc3ee2e50
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616865"
---
# <a name="dialog-boxes"></a>İletişim Kutuları

Windows için uygulamalar genellikle iletişim kutuları aracılığıyla kullanıcıyla iletişim kurar. Sınıf [CDialog](reference/cdialog-class.md) , iletişim kutularını yönetmek için bir arabirim sağlar. Visual C++ iletişim kutusu Düzenleyicisi, iletişim kutularını tasarlamayı ve iletişim kutusu şablonu kaynaklarını oluşturmayı kolaylaştırır ve kod sihirbazları, bir iletişim kutusundaki denetimleri başlatma ve doğrulama işlemini ve Kullanıcı tarafından girilen değerleri toplamayı basitleştirir.

İletişim kutuları aşağıdakiler dahil olmak üzere denetimler içerir:

- Düzenleme kutuları, pushbutton, liste kutuları, Birleşik giriş kutuları, ağaç denetimleri, liste denetimleri ve ilerleme göstergeleri gibi Windows ortak denetimleri.

- ActiveX denetimleri.

- Sahip tarafından çizilmiş denetimler: iletişim kutusunda çizimden sorumlu olduğunuz denetimlerdir.

Çoğu iletişim kutusu, kullanıcının programın başka bir bölümünü kullanmadan önce iletişim kutusunu kapatmasını gerektiren kalıcıdır. Ancak, iletişim kutusu açıkken kullanıcıların diğer pencereler ile çalışmasına izin veren kalıcı olmayan iletişim kutuları oluşturmak mümkündür. MFC, sınıfıyla her iki tür iletişim kutusunu destekler `CDialog` . Denetimler iletişim kutusu [Düzenleyicisi](../windows/dialog-editor.md)ile oluşturulmuş bir iletişim kutusu şablonu kaynağı kullanılarak düzenlenir ve yönetilir.

Sekme iletişim kutuları olarak da bilinen [Özellik sayfaları](property-sheets-mfc.md), farklı iletişim kutusu denetimlerinin "sayfalarını" içeren iletişim kutularıdır. Her sayfanın üst kısımdaki bir dosya klasörü "Tab" vardır. Bir sekmeye tıklamak bu sayfayı iletişim kutusunun önüne getirir.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Örnek: Bir İletişim Kutusunu Menü Komutu ile Görüntüleme](example-displaying-a-dialog-box-via-a-menu-command.md)

- [Framework'te iletişim kutusu bileşenleri](dialog-box-components-in-the-framework.md)

- [Kalıcı ve kalıcı olmayan iletişim kutuları](modal-and-modeless-dialog-boxes.md)

- İletişim kutusunda [Özellik sayfaları ve özellik sayfaları](property-sheets-and-property-pages-mfc.md)

- [İletişim kaynağı oluşturma](creating-the-dialog-resource.md)

- [Kod sihirbazları ile iletişim kutusu sınıfı oluşturma](creating-a-dialog-class-with-code-wizards.md)

- [MFC’de İletişim Kutularıyla çalışma](life-cycle-of-a-dialog-box.md)

- [İletişim kutusu veri değişimi (DDX) ve doğrulaması (DDV)](dialog-data-exchange-and-validation.md)

- [İletişim kutusundaki denetimlere tür kullanımı uyumlu erişim](type-safe-access-to-controls-in-a-dialog-box.md)

- [Windows iletilerini sınıfınıza eşleme](mapping-windows-messages-to-your-class.md)

- [Yaygın olarak geçersiz kılınan üye Işlevleri](commonly-overridden-member-functions.md)

- [Yaygın Olarak Eklenen Üye İşlevleri](commonly-added-member-functions.md)

- [Ortak iletişim kutusu sınıfları](common-dialog-classes.md)

- [OLE'deki iletişim kutuları](dialog-boxes-in-ole.md)

- Kullanıcı arabirimi bir iletişim kutusu olan bir uygulama oluşturun: [CMNCTRL1](../overview/visual-cpp-samples.md) veya [CMNCTRL2](../overview/visual-cpp-samples.md) örnek programlarına bakın. Uygulama Sihirbazı bu seçeneği de sağlar.

- [Örnekler](dialog-sample-list.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı arabirimi öğeleri](user-interface-elements-mfc.md)
