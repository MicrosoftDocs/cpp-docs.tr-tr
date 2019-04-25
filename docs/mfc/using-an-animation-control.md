---
title: Animasyon Denetimi Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], animation
- CAnimateCtrl class [MFC], animation controls
- animation controls [MFC]
ms.assetid: a009a464-e12d-4112-bf52-04a09b28dd88
ms.openlocfilehash: 10bd8c0c26f92ce5de2261d6aca6fc7cc3a37365
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180511"
---
# <a name="using-an-animation-control"></a>Animasyon Denetimi Kullanma

Animasyon denetimi tipik kullanımını aşağıdaki deseni izler:

- Denetim oluşturulur. Denetim bir iletişim kutusu şablonunda belirtilmezse, iletişim kutusu oluşturulurken oluşturma otomatik olarak gerçekleşir. (Olması bir [CAnimateCtrl](../mfc/reference/canimatectrl-class.md) animasyon denetimi için karşılık gelen iletişim sınıfınızı üye.) Alternatif olarak, [Oluştur](../mfc/reference/canimatectrl-class.md#create) herhangi bir pencerenin alt pencere olarak denetimi oluşturmak için üye işlevi.

- Çağırarak animasyon denetime AVI klibi yük [açık](../mfc/reference/canimatectrl-class.md#open) üye işlevi. İletişim kutusunda, animasyon denetimi ise bunu yapmak için uygun bir iletişim kutusu sınıfının yerdir [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) işlevi.

- Çağırarak klibi [Play](../mfc/reference/canimatectrl-class.md#play) üye işlevi. İletişim kutusunda, animasyon denetimi ise bunu yapmak için uygun bir iletişim kutusu sınıfının yerdir `OnInitDialog` işlevi. Çağırma `Play` animasyon denetimi ACS_AUTOPLAY stil kümesi varsa gerekli değildir.

- Küçük bölümlerini görüntülemek veya kare kare kullanım yürütmek isterseniz `Seek` üye işlevi. Yürütülen bir küçük resim durdurmak için kullanın `Stop` üye işlevi.

- Hemen kontrol edilecek kullanmayacaksanız küçük bellekten çağırarak kaldırmak `Close` üye işlevi.

- Animasyon denetimi bir iletişim kutusunda, varsa onu ve `CAnimateCtrl` nesne otomatik olarak silinecektir. Her iki denetim sağlamak ihtiyacınız değil, varsa ve `CAnimateCtrl` nesne düzgün bir şekilde yok. Otomatik olarak denetim yok etme AVI klibi kapatır.

## <a name="see-also"></a>Ayrıca bkz.

[CAnimateCtrl Kullanma](../mfc/using-canimatectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
