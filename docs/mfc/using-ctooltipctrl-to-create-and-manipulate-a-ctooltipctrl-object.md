---
title: CToolTipCtrl Kullanarak bir CToolTipCtrl Nesnesi Oluşturma ve Düzenleme
ms.date: 11/04/2016
f1_keywords:
- CToolTipCtrl
helpviewer_keywords:
- tool tips [MFC], creating
- CToolTipCtrl class [MFC], using
ms.assetid: 0a34583f-f66d-46a1-a239-31b80ea395ad
ms.openlocfilehash: b0f008c70eeb43455408e5b0ad302df6b923608e
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57261212"
---
# <a name="using-ctooltipctrl-to-create-and-manipulate-a-ctooltipctrl-object"></a>CToolTipCtrl Kullanarak bir CToolTipCtrl Nesnesi Oluşturma ve Düzenleme

İşte bir örnek [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md) Kullanım:

### <a name="to-create-and-manipulate-a-ctooltipctrl"></a>Oluşturma ve bir CToolTipCtrl işlemek için

1. Oluşturmak `CToolTipCtrl` nesne.

1. Çağrı [Oluştur](../mfc/reference/ctooltipctrl-class.md#create) Windows araç ipucu ortak denetim oluşturma ve buna eklemek için `CToolTipCtrl` nesne.

1. Çağrı [AddTool](../mfc/reference/ctooltipctrl-class.md#addtool) imleç araç olduğunda araç ipucunda depolanan bilgilerin görüntülenmesi araç ipucu denetimi ile bir aracı kaydetmek için.

1. Çağrı [SetToolInfo](../mfc/reference/ctooltipctrl-class.md#settoolinfo) araç ipucu için bir aracı tutar bilgilerini ayarlamak için.

1. Çağrı [SetToolRect](../mfc/reference/ctooltipctrl-class.md#settoolrect) yeni sınırlayıcı bir dikdörtgen aracı için ayarlanacak.

1. Çağrı [HitTest](../mfc/reference/ctooltipctrl-class.md#hittest) verilen aracının dikdörtgen içinde olup olmadığını ve bu durumda belirlemek için bir nokta test etmek için aracı hakkında bilgi alın.

1. Çağrı [GetToolCount](../mfc/reference/ctooltipctrl-class.md#gettoolcount) araçları sayısını almak için kayıtlı araç ipucunu denetimini.

## <a name="see-also"></a>Ayrıca bkz.

[CToolTipCtrl Kullanma](../mfc/using-ctooltipctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
