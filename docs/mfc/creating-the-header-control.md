---
description: 'Hakkında daha fazla bilgi edinin: üst bilgi denetimi oluşturma'
title: Üstbilgi Denetimi Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- CHeaderCtrl class [MFC], creating
- header controls [MFC], creating
ms.assetid: 7864d9d2-4a2c-4622-b58b-7b110a1e28d2
ms.openlocfilehash: b75a21a0d855e557bf02a9144fc3712b5bb2ee35
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309699"
---
# <a name="creating-the-header-control"></a>Üstbilgi Denetimi Oluşturma

Üst bilgi denetimi iletişim kutusu düzenleyicisinde doğrudan kullanılamaz (ancak bir başlık denetimi içeren bir liste denetimi ekleyebilirsiniz).

### <a name="to-put-a-header-control-in-a-dialog-box"></a>Bir iletişim kutusuna üst bilgi denetimi koymak için

1. İletişim sınıfınızı [CHeaderCtrl](reference/cheaderctrl-class.md) türünde bir üye değişkenini el ile ekleyin.

1. [OnInitDialog](reference/cdialog-class.md#oninitdialog)' da, için stilleri oluşturun ve ayarlayın `CHeaderCtrl` , konumlandırın ve görüntüleyin.

1. Üst bilgi denetimine öğe ekleyin.

1. İşlemek istediğiniz herhangi bir üst bilgi denetimi bildirim iletisi için İletişim sınıfındaki işleyici işlevlerini eşlemek için [sınıf sihirbazını](reference/mfc-class-wizard.md) kullanın (bkz. [iletileri işlevlere eşleme](reference/mapping-messages-to-functions.md)).

### <a name="to-put-a-header-control-in-a-view-not-a-clistview"></a>Bir görünüme üst bilgi denetimi koymak için (CListView değil)

1. Görünüm sınıfınıza bir [CHeaderCtrl](reference/cheaderctrl-class.md) nesnesi ekleyin.

1. Görünümün [OnInitialUpdate](reference/cview-class.md#oninitialupdate) üye işlevindeki başlık Denetim penceresini stil, konum ve görüntüleme.

1. Üst bilgi denetimine öğe ekleyin.

1. İşlemek için gereken herhangi bir üst bilgi denetimi bildirim iletisi için Görünüm sınıfındaki işleyici işlevlerini eşlemek için [sınıf Sihirbazı](reference/mfc-class-wizard.md) 'nı kullanın (bkz. [iletileri işlevlere eşleme](reference/mapping-messages-to-functions.md)).

Her iki durumda da, görünüm veya iletişim nesnesi oluşturulduğunda katıştırılmış denetim nesnesi oluşturulur. Sonra Denetim penceresini oluşturmak için [CHeaderCtrl:: Create](reference/cheaderctrl-class.md#create) komutunu çağırmanız gerekir. Denetimi konumlandırmak için, denetimin ilk boyutunu ve konumunu ve [SetWindowPos](reference/cwnd-class.md#setwindowpos) 'u istediğiniz konuma göre ayarlamak Için [CHeaderCtrl:: Layout](reference/cheaderctrl-class.md#layout) komutunu çağırın. Ardından [üst bilgi denetimine öğe ekleme](adding-items-to-the-header-control.md)bölümünde açıklandığı gibi öğeleri ekleyin.

Daha fazla bilgi için, bkz. Windows SDK [üst bilgi denetimi oluşturma](/windows/win32/Controls/header-controls) .

## <a name="see-also"></a>Ayrıca bkz.

[CHeaderCtrl Kullanma](using-cheaderctrl.md)<br/>
[Denetimler](controls-mfc.md)
