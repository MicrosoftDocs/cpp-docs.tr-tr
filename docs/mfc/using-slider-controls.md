---
title: Kaydırıcı Denetimlerini Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- CSliderCtrl class [MFC], using
- slider controls
- slider controls [MFC], using
ms.assetid: 2b1a8ac8-2b17-41e1-aa24-83c1fd737049
ms.openlocfilehash: b358b4e92c7d9f214291b047a080f71b48183519
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411519"
---
# <a name="using-slider-controls"></a>Kaydırıcı Denetimlerini Kullanma

Bir kaydırıcı denetimi tipik kullanımını aşağıdaki deseni izler:

- Denetim oluşturulur. Denetim bir iletişim kutusu şablonunda belirtilmezse, iletişim kutusu oluşturulurken oluşturma otomatik olarak gerçekleşir. (Olması bir [CSliderCtrl](../mfc/reference/csliderctrl-class.md) kaydırıcı denetimi için karşılık gelen iletişim sınıfınızı üye.) Alternatif olarak, [Oluştur](../mfc/reference/csliderctrl-class.md#create) herhangi bir pencerenin alt pencere olarak denetimi oluşturmak için üye işlevi.

- Denetim değerlerini ayarlamak için çeşitli küme üyesi işlevleri çağırın. Kaydırıcı için minimum ve maksimum konumlarını ayarlama, değer çizgileri çizim, bir seçim aralığını ayarlama ve kaydırıcıyı yeniden konumlandırma yapabileceğiniz değişiklikleri içerir. Bir iletişim kutusu denetimleri için bunu yapmak için bir iletişim kutusunda 's zamandır [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) işlevi.

- Kullanıcı denetimle etkileşim gibi çeşitli bildirim iletileri gönderir. Kaydırıcı değeri çağırarak denetiminden ayıklayabilmeniz için [GetPos](../mfc/reference/csliderctrl-class.md#getpos) üye işlevi.

- Denetim ile işiniz bittiğinde, düzgün bir şekilde imha emin olmanız gerekir. Kaydırıcı denetimi bir iletişim kutusunda, varsa onu ve `CSliderCtrl` nesne otomatik olarak silinecektir. Her iki denetim sağlamak ihtiyacınız değil, varsa ve `CSliderCtrl` nesne düzgün bir şekilde yok.

## <a name="see-also"></a>Ayrıca bkz.

[CSliderCtrl Kullanma](../mfc/using-csliderctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
