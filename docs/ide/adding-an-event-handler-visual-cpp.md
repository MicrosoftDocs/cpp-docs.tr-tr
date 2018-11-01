---
title: Olay İşleyici Ekleme (Visual C++)
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.eventhandler.overview
helpviewer_keywords:
- event handlers, adding
- properties [Visual Studio], MSBuild
- MSBuild, properties
ms.assetid: 050bebf0-a9e0-474b-905c-796fe5ac8fc3
ms.openlocfilehash: d9256fca75b6980d87382bbeb794fa90b89f37c0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512450"
---
# <a name="adding-an-event-handler-visual-c"></a>Olay İşleyici Ekleme (Visual C++)

Kaynak Düzenleyicisi'nde, yeni bir olay işleyicisi ekleyebilir, veya Düzenle iletişim kutusu denetimi kullanarak var olan olay işleyicisi, [olay işleyici Sihirbazı](../ide/event-handler-wizard.md).

İletişim kutusunu kullanarak uygulama sınıfa olaya ekleyebilirsiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window). İletişim kutusu sınıf dışında bir sınıfa olaya eklemek istiyorsanız, olay işleyici Sihirbazı'nı kullanın.

### <a name="to-add-an-event-handler-to-a-dialog-box-control"></a>Bir iletişim kutusu denetimi olay işleyicisi eklemek için

1. İletişim kutusu kaynak çift [kaynak görünümü](../windows/resource-view-window.md) denetimi içeren bir iletişim kutusu kaynağına açmak için [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md).

1. Bildirim olayı işlemek istediğiniz denetime sağ tıklayın.

1. Kısayol menüsünde **olay işleyici Ekle** olay işleyici Sihirbazı'nı görüntülemek için.

1. Olay seçin **ileti türü** de seçilen sınıfı eklemek için onay kutusunu **sınıf listesi** kutusu.

1. Varsayılan adı kabul **işlev işleyicisi adı** kutusuna veya tercih ettiğiniz bir ad sağlayın.

1. Tıklayın **ekleme ve düzenleme** projeye olay işleyicisi eklemek ve uygun bir olay işleyici kodu eklemek için yeni işlevi metin düzenleyicisini açın.

   Seçili ileti türü seçilen bir sınıf için bir olay işleyicisi zaten varsa **ekleme ve düzenleme** kullanılamıyor ve **kod düzenleme** kullanılabilir. Tıklayın **kod düzenleme** mevcut işlevi metin düzenleyiciyi açın.

Alternatif olarak, olay işleyicilerindeki ekleyebilirsiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window). Bkz: [iletişim kutusu denetimleri için olay işleyicileri ekleme](../windows/adding-event-handlers-for-dialog-box-controls.md) daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca Bkz.

[Kod sihirbazlarıyla işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md)<br>
[Sınıf ekleme](../ide/adding-a-class-visual-cpp.md)<br>
[Üye değişkeni ekleme](../ide/adding-a-member-variable-visual-cpp.md)<br>
[Üye işlevi ekleme](../ide/adding-a-member-function-visual-cpp.md)<br>
[MFC ileti işleyicisi](../mfc/reference/adding-an-mfc-message-handler.md)<br>
[Sınıf yapısında gezinme](../ide/navigating-the-class-structure-visual-cpp.md)