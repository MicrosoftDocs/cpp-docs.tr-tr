---
description: 'Hakkında daha fazla bilgi edinin: bir animasyon denetimi kullanma'
title: Animasyon Denetimi Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], animation
- CAnimateCtrl class [MFC], animation controls
- animation controls [MFC]
ms.assetid: a009a464-e12d-4112-bf52-04a09b28dd88
ms.openlocfilehash: 7ef4a7b5eb005569ac2a3e3cb66cc0ed785e9299
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202723"
---
# <a name="using-an-animation-control"></a>Animasyon Denetimi Kullanma

Bir animasyon denetiminin tipik kullanımı aşağıdaki kalıbı izler:

- Denetim oluşturulur. Denetim bir iletişim kutusu şablonunda belirtilmişse, iletişim kutusu oluşturulduğunda oluşturma otomatik olur. (İletişim kutusu sınıfınıza animasyon denetimine karşılık gelen bir [CAnimateCtrl](../mfc/reference/canimatectrl-class.md) üyesi olmanız gerekir.) Alternatif olarak, denetimi herhangi bir pencerenin alt penceresi olarak oluşturmak için üye [Oluştur](../mfc/reference/canimatectrl-class.md#create) işlevini de kullanabilirsiniz.

- [Açık](../mfc/reference/canimatectrl-class.md#open) üye işlevini çağırarak animasyon DENETIMINE bir AVI klibi yükleyin. Animasyon denetiminiz bir iletişim kutusunda ise, bunu yapmak için iyi bir yer kullanılır. iletişim kutusu sınıfının [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) işlevi.

- [Play](../mfc/reference/canimatectrl-class.md#play) üye işlevini çağırarak klibi oynatın. Animasyon denetiminiz bir iletişim kutusunda ise, bunu yapmak için iyi bir yerdir. iletişim kutusu sınıfının `OnInitDialog` işlevi. `Play`Animasyon denetiminin ACS_AUTOPLAY stil kümesi varsa, çağırma gerekli değildir.

- Klibin bölümlerini göstermek veya çerçeveyi çerçeveye göre oynatmak istiyorsanız `Seek` üye işlevini kullanın. Yürütülen bir klibi durdurmak için `Stop` üye işlevini kullanın.

- Denetimi hemen yok etmek istemiyorsanız, üye işlevini çağırarak klibi bellekten kaldırın `Close` .

- Animasyon denetimi bir iletişim kutusunda ise, ve `CAnimateCtrl` nesnesi otomatik olarak yok edilir. Aksi takdirde, hem denetimin hem de `CAnimateCtrl` nesnenin düzgün şekilde yok edildiğini güvence altına almanız gerekir. Denetimin yok edilmesi, otomatik olarak AVI klibini kapatır.

## <a name="see-also"></a>Ayrıca bkz.

[CAnimateCtrl Kullanma](../mfc/using-canimatectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
