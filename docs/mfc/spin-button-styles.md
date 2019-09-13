---
title: Döndür Düğmesi Stilleri
ms.date: 09/09/2019
helpviewer_keywords:
- styles [MFC], CSpinButtonCtrl
- CSpinButtonCtrl class [MFC], styles
- styles [MFC], spin button control
- spin button control, styles
ms.assetid: fb4a7f6f-9182-47be-bccf-0728fdc5332f
ms.openlocfilehash: 1aae4b7e4c63929ebe03c97d50f05754bc13ec26
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907852"
---
# <a name="spin-button-styles"></a>Döndür Düğmesi Stilleri

Bir döndürme düğmesine ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)) ilişkin ayarların birçoğu, stillerle denetlenir. [Sınıf Sihirbazı](reference/mfc-class-wizard.md)'nı kullanarak aşağıdaki stilleri ayarlayabilirsiniz.

- **Yön** Dikey ya da yatay. Ok düğmelerinin yönünü denetler. UDS_HORZ stiliyle ilişkili.

- **Hizalama** Eklenmemiş, sol veya sağdan biri. Döndürme düğmesinin konumunu denetler. Sol ve sağ, arkadaş penceresinin yanındaki döndürme düğmesini konumlandırır. Arkadaş penceresinin genişliği, döndürme düğmesine uyacak şekilde azaltılır. UDS_ALIGNLEFT ve UDS_ALIGNRIGHT stilleriyle ilişkili.

- **Otomatik arkadaş** , Döndürme düğmesine otomatik olarak Z düzeninde bir önceki pencereyi arkadaş penceresinde seçer. İletişim kutusu şablonunda, bu, sekme düzeninde döndürme düğmesinden önce gelen denetimdir. UDS_AUTOBUDDY stiliyle ilişkili.

- **Arkadaş tamsayı ayarla** Geçerli konum değiştiği için, döndürme denetiminin arkadaş penceresinin başlığını artırmasına ve azaltmasına neden olur. UDS_SETBUDDYINT stiliyle ilişkili.

- **Binlik yok** Arkadaş penceresinin açıklamalı alt yazısının değerinde binlik ayırıcısını eklemez. UDS_NOTHOUSANDS stiliyle ilişkili.

    > [!NOTE]
    >  Arkadaş denetiminden tamsayı değerini almak için iletişim kutusu veri değişimi 'ni (DDX) kullanmak istiyorsanız bu stili ayarlayın. `DDX_Text`gömülü binlik ayırıcıları kabul etmez.

- **Sarın** Değer, denetimin aralığının ötesinde artılarak veya azaltılacağından, konumun "Wrap" olmasına neden olur. UDS_WRAP stiliyle ilişkili.

- **Ok tuşları** , Yukarı ok ve aşağı ok tuşlarına basıldığında döndürme düğmesinin konumu artırmasına veya azaltmasına neden olur. UDS_ARROWKEYS stiliyle ilişkili.

## <a name="see-also"></a>Ayrıca bkz.

[CSpinButtonCtrl Kullanma](../mfc/using-cspinbuttonctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
