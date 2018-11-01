---
title: Animasyon Denetimi Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], animation
- CAnimateCtrl class [MFC], animation controls
- animation controls [MFC]
ms.assetid: a009a464-e12d-4112-bf52-04a09b28dd88
ms.openlocfilehash: fa5ce6cc30d4bc31dbe52c0e559ce97e40acacba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631003"
---
# <a name="using-an-animation-control"></a>Animasyon Denetimi Kullanma

Animasyon denetimi tipik kullanımını aşağıdaki deseni izler:

- Denetim oluşturulur. Denetim bir iletişim kutusu şablonunda belirtilmezse, iletişim kutusu oluşturulurken oluşturma otomatik olarak gerçekleşir. (Olması bir [CAnimateCtrl](../mfc/reference/canimatectrl-class.md) animasyon denetimi için karşılık gelen iletişim sınıfınızı üye.) Alternatif olarak, [Oluştur](../mfc/reference/canimatectrl-class.md#create) herhangi bir pencerenin alt pencere olarak denetimi oluşturmak için üye işlevi.

- Çağırarak animasyon denetime AVI klibi yük [açık](../mfc/reference/canimatectrl-class.md#open) üye işlevi. İletişim kutusunda, animasyon denetimi ise bunu yapmak için uygun bir iletişim kutusu sınıfının yerdir [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) işlevi.

- Çağırarak klibi [Play](../mfc/reference/canimatectrl-class.md#play) üye işlevi. İletişim kutusunda, animasyon denetimi ise bunu yapmak için uygun bir iletişim kutusu sınıfının yerdir `OnInitDialog` işlevi. Çağırma `Play` animasyon denetimi ACS_AUTOPLAY stil kümesi varsa gerekli değildir.

- Küçük bölümlerini görüntülemek veya kare kare kullanım yürütmek isterseniz `Seek` üye işlevi. Yürütülen bir küçük resim durdurmak için kullanın `Stop` üye işlevi.

- Hemen kontrol edilecek kullanmayacaksanız küçük bellekten çağırarak kaldırmak `Close` üye işlevi.

- Animasyon denetimi bir iletişim kutusunda, varsa onu ve `CAnimateCtrl` nesne otomatik olarak silinecektir. Her iki denetim sağlamak ihtiyacınız değil, varsa ve `CAnimateCtrl` nesne düzgün bir şekilde yok. Otomatik olarak denetim yok etme AVI klibi kapatır.

## <a name="see-also"></a>Ayrıca Bkz.

[CAnimateCtrl Kullanma](../mfc/using-canimatectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

