---
title: Ağaç denetimlerini kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CTreeCtrl class [MFC], using
- tree controls [MFC], about tree controls
ms.assetid: 4e92941a-e477-4fb1-b1ce-4abeafbef1c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1fc3efbf48a9005bf117c2dd7ab5f1bd01ed556d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46403688"
---
# <a name="using-tree-controls"></a>Ağaç Denetimlerini Kullanma

Ağaç denetimi tipik kullanımını ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) aşağıdaki deseni izler:

- Denetim oluşturulur. Denetim bir iletişim kutusu şablonunda belirtilirse veya kullanıyorsanız `CTreeView`, oluşturma, iletişim kutusu ya da Görünüm oluşturulduğunda otomatiktir. Ağaç denetimi başka bir pencere bir alt pencere olarak oluşturmak istediğiniz kullanırsanız [Oluştur](../mfc/reference/ctreectrl-class.md#create) üye işlevi.

- Görüntüleri kullanmak için ağaç denetimi istiyorsanız, bir görüntü listesi çağırarak ayarlayın [SetImageList](../mfc/reference/ctreectrl-class.md#setimagelist). Çağırarak girinti değiştirebilirsiniz [SetIndent](../mfc/reference/ctreectrl-class.md#setindent). Bunu yapmak için iyi bir zaman yer [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) (için iletişim kutularındaki denetimler) veya [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) (için görünümler).

- Çağırarak denetime verilerinizden `CTreeCtrl`'s [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) işlevi için her bir veri öğesi için bir kez. `InsertItem` öğesine daha sonra ne zaman gibi başvurduğu için kullanabileceğiniz bir tanıtıcı döndürür, alt öğe ekleme. Verileri başlatma zamanı bulunduğu `OnInitDialog` (için iletişim kutularındaki denetimler) veya `OnInitialUpdate` (için görünümler).

- Kullanıcı denetimle etkileşim gibi çeşitli bildirim iletileri gönderir. Her on_notıfy_reflect makrosu ileti eşlemede denetimi pencerenin ekleme veya ana pencerenin ileti eşlemesi için on_notıfy makrosu ekleyerek işlemek istediğiniz tüm iletileri işlemek için bir işlev belirtebilirsiniz. Bkz: [ağaç denetimi bildirim iletileri](../mfc/tree-control-notification-messages.md) olası bildirimler listesi için bu konuda daha sonra.

- Denetim değerlerini ayarlamak için çeşitli küme üyesi işlevleri çağırın. Yaptığınız değişiklikler girinti ayarlama ve text, Image veya bir öğeyle ilişkili veri değiştirme içerir.

- Denetimin içeriğini incelemek için çeşitli Get işlevlerini kullanın. Ağaç denetimi üst, alt ve eşdüzey belirtilen öğe tanıtıcıları almanızı sağlayan işlevler ile içeriğini çapraz geçiş yapabilirsiniz. Belirli bir düğüm alt bile sıralayabilirsiniz.

- Denetim ile işiniz bittiğinde, düzgün bir şekilde imha emin olun. Ağaç denetimi içinde bir iletişim kutusu ise ya da bir görünüm ise bunu ve `CTreeCtrl` nesne otomatik olarak silinecektir. Her iki denetim sağlamak ihtiyacınız değil, varsa ve `CTreeCtrl` nesne düzgün bir şekilde yok.

## <a name="see-also"></a>Ayrıca Bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

