---
title: İletişim kutuları
ms.date: 11/04/2016
helpviewer_keywords:
- modeless dialog boxes [MFC], MFC dialog boxes
- MFC, dialog boxes
- modal dialog boxes [MFC], MFC dialog boxes
- CDialog class [MFC], MFC dialog boxes
- MFC dialog boxes
ms.assetid: e4feea1a-8360-4ccb-9b84-507f1ccd9ef3
ms.openlocfilehash: 18b4c4d1386716a0a3282b88d6fdf5a701abce08
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685797"
---
# <a name="dialog-boxes"></a>İletişim kutuları

Windows için uygulamalar genellikle iletişim kutuları aracılığıyla kullanıcıyla iletişim kurar. Sınıf [CDialog](../mfc/reference/cdialog-class.md) , iletişim kutularını yönetmek için bir arabirim sağlar, görsel C++ iletişim kutusu Düzenleyicisi iletişim kutularını tasarlamayı ve iletişim kutusu şablonu kaynaklarını oluşturmayı kolaylaştırır ve kod sihirbazları, bu işlemi başlatma ve doğrulama sürecini basitleştirir. bir iletişim kutusundaki ve Kullanıcı tarafından girilen değerleri toplayan denetimler.

İletişim kutuları aşağıdakiler dahil olmak üzere denetimler içerir:

- Düzenleme kutuları, pushbutton, liste kutuları, Birleşik giriş kutuları, ağaç denetimleri, liste denetimleri ve ilerleme göstergeleri gibi Windows ortak denetimleri.

- ActiveX denetimleri.

- Sahip tarafından çizilmiş denetimler: iletişim kutusunda çizimden sorumlu olduğunuz denetimlerdir.

Çoğu iletişim kutusu, kullanıcının programın başka bir bölümünü kullanmadan önce iletişim kutusunu kapatmasını gerektiren kalıcıdır. Ancak, iletişim kutusu açıkken kullanıcıların diğer pencereler ile çalışmasına izin veren kalıcı olmayan iletişim kutuları oluşturmak mümkündür. MFC `CDialog` sınıfıyla her iki tür iletişim kutusunu destekler. Denetimler iletişim kutusu [Düzenleyicisi](../windows/dialog-editor.md)ile oluşturulmuş bir iletişim kutusu şablonu kaynağı kullanılarak düzenlenir ve yönetilir.

Sekme iletişim kutuları olarak da bilinen [Özellik sayfaları](../mfc/property-sheets-mfc.md), farklı iletişim kutusu denetimlerinin "sayfalarını" içeren iletişim kutularıdır. Her sayfanın üst kısımdaki bir dosya klasörü "Tab" vardır. Bir sekmeye tıklamak bu sayfayı iletişim kutusunun önüne getirir.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Örnek: bir menü komutu aracılığıyla bir Iletişim kutusu görüntüleme](../mfc/example-displaying-a-dialog-box-via-a-menu-command.md)

- [Çerçevede iletişim kutusu bileşenleri](../mfc/dialog-box-components-in-the-framework.md)

- [Kalıcı ve kalıcı olmayan iletişim kutuları](../mfc/modal-and-modeless-dialog-boxes.md)

- İletişim kutusunda [Özellik sayfaları ve özellik sayfaları](../mfc/property-sheets-and-property-pages-mfc.md)

- [İletişim kaynağı oluşturma](../mfc/creating-the-dialog-resource.md)

- [Kod sihirbazları ile iletişim kutusu sınıfı oluşturma](../mfc/creating-a-dialog-class-with-code-wizards.md)

- [MFC 'de Iletişim kutularıyla çalışma](../mfc/life-cycle-of-a-dialog-box.md)

- [İletişim kutusu veri değişimi (DDX) ve doğrulaması (DDV)](../mfc/dialog-data-exchange-and-validation.md)

- [İletişim kutusundaki denetimlere tür kullanımı uyumlu erişim](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)

- [Windows iletilerini sınıfınıza eşleme](../mfc/mapping-windows-messages-to-your-class.md)

- [Yaygın olarak geçersiz kılınan üye Işlevleri](../mfc/commonly-overridden-member-functions.md)

- [Yaygın olarak eklenen üye Işlevleri](../mfc/commonly-added-member-functions.md)

- [Ortak iletişim kutusu sınıfları](../mfc/common-dialog-classes.md)

- [OLE 'deki iletişim kutuları](../mfc/dialog-boxes-in-ole.md)

- Kullanıcı arabirimi bir iletişim kutusu olan bir uygulama oluşturun: [CMNCTRL1](../overview/visual-cpp-samples.md) veya [CMNCTRL2](../overview/visual-cpp-samples.md) örnek programlarına bakın. Uygulama Sihirbazı bu seçeneği de sağlar.

- [Örnekler](../mfc/dialog-sample-list.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)
