---
description: 'Daha fazla bilgi edinin: kaydırıcı denetimlerini kullanma'
title: Kaydırıcı Denetimlerini Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- CSliderCtrl class [MFC], using
- slider controls
- slider controls [MFC], using
ms.assetid: 2b1a8ac8-2b17-41e1-aa24-83c1fd737049
ms.openlocfilehash: b9134d76261bf5c15bfef90260394ee6a4c760e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322678"
---
# <a name="using-slider-controls"></a>Kaydırıcı Denetimlerini Kullanma

Kaydırıcı denetiminin tipik kullanımı aşağıdaki kalıbı izler:

- Denetim oluşturulur. Denetim bir iletişim kutusu şablonunda belirtilmişse, iletişim kutusu oluşturulduğunda oluşturma otomatik olur. (Kaydırıcı denetimine karşılık gelen iletişim sınıfınızın bir [CSliderCtrl](../mfc/reference/csliderctrl-class.md) üyesine sahip olmanız gerekir.) Alternatif olarak, denetimi herhangi bir pencerenin alt penceresi olarak oluşturmak için üye [Oluştur](../mfc/reference/csliderctrl-class.md#create) işlevini de kullanabilirsiniz.

- Denetimin değerlerini ayarlamak için çeşitli set member işlevlerini çağırın. Yapabileceğiniz değişiklikler kaydırıcı için en düşük ve en yüksek pozisyonları ayarlamayı, değer işaretlerini çizmeyi, seçim aralığını ayarlamayı ve kaydırıcıyı yeniden konumlandırmayı içerir. İletişim kutusundaki denetimler için, bunu yapmak için iyi bir zaman, iletişim kutusunun [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) işleviydi.

- Kullanıcı denetimle etkileşime geçtiğinde, çeşitli bildirim iletileri gönderilir. [GetPos](../mfc/reference/csliderctrl-class.md#getpos) üye işlevini çağırarak kaydırıcı değerini denetimden ayıklayabilirsiniz.

- Denetimle işiniz bittiğinde, doğru şekilde yok edildiğinizden emin olmanız gerekir. Kaydırıcı denetimi bir iletişim kutusunda ise, ve `CSliderCtrl` nesnesi otomatik olarak yok edilir. Aksi takdirde, hem denetimin hem de `CSliderCtrl` nesnenin düzgün şekilde yok edildiğini güvence altına almanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[CSliderCtrl Kullanma](../mfc/using-csliderctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
