---
title: Kaydırıcı denetimlerini kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CSliderCtrl class [MFC], using
- slider controls
- slider controls [MFC], using
ms.assetid: 2b1a8ac8-2b17-41e1-aa24-83c1fd737049
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d0496a15b289ec055fd2706975603f25cef13938
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388842"
---
# <a name="using-slider-controls"></a>Kaydırıcı Denetimlerini Kullanma

Bir kaydırıcı denetimi tipik kullanımını aşağıdaki deseni izler:

- Denetim oluşturulur. Denetim bir iletişim kutusu şablonunda belirtilmezse, iletişim kutusu oluşturulurken oluşturma otomatik olarak gerçekleşir. (Olması bir [CSliderCtrl](../mfc/reference/csliderctrl-class.md) kaydırıcı denetimi için karşılık gelen iletişim sınıfınızı üye.) Alternatif olarak, [Oluştur](../mfc/reference/csliderctrl-class.md#create) herhangi bir pencerenin alt pencere olarak denetimi oluşturmak için üye işlevi.

- Denetim değerlerini ayarlamak için çeşitli küme üyesi işlevleri çağırın. Kaydırıcı için minimum ve maksimum konumlarını ayarlama, değer çizgileri çizim, bir seçim aralığını ayarlama ve kaydırıcıyı yeniden konumlandırma yapabileceğiniz değişiklikleri içerir. Bir iletişim kutusu denetimleri için bunu yapmak için bir iletişim kutusunda 's zamandır [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) işlevi.

- Kullanıcı denetimle etkileşim gibi çeşitli bildirim iletileri gönderir. Kaydırıcı değeri çağırarak denetiminden ayıklayabilmeniz için [GetPos](../mfc/reference/csliderctrl-class.md#getpos) üye işlevi.

- Denetim ile işiniz bittiğinde, düzgün bir şekilde imha emin olmanız gerekir. Kaydırıcı denetimi bir iletişim kutusunda, varsa onu ve `CSliderCtrl` nesne otomatik olarak silinecektir. Her iki denetim sağlamak ihtiyacınız değil, varsa ve `CSliderCtrl` nesne düzgün bir şekilde yok.

## <a name="see-also"></a>Ayrıca Bkz.

[CSliderCtrl Kullanma](../mfc/using-csliderctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

