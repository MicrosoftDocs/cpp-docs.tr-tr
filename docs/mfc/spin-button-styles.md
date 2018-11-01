---
title: Döndür Düğmesi Stilleri
ms.date: 11/04/2016
helpviewer_keywords:
- styles [MFC], CSpinButtonCtrl
- CSpinButtonCtrl class [MFC], styles
- styles [MFC], spin button control
- spin button control, styles
ms.assetid: fb4a7f6f-9182-47be-bccf-0728fdc5332f
ms.openlocfilehash: 73042dbbdc28819ecc736c282599189ee074ce77
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50457115"
---
# <a name="spin-button-styles"></a>Döndür Düğmesi Stilleri

Birçok değer değiştirme düğmesi için ayarları ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)) stilleri tarafından denetlenir. Aşağıdaki stilleri kullanarak ayarlayabilirsiniz **özellikleri** iletişim kutusu Düzenleyicisi penceresinde.

- **Yönlendirme** dikey veya yatay. Ok düğmelerini yönünü denetler. UDS_HORZ stil ile ilişkili.

- **Hizalama** eklenmemiş, sola veya sağa biri. Değer değiştirme düğmesi konumunu denetler. Sol ve sağda değer değiştirme düğmesi yanındaki buddy penceresindeki getirin. Buddy penceresinin genişliğini değer değiştirme düğmesi uyum sağlayacak şekilde azalır. UDS_ALIGNLEFT ve UDS_ALIGNRIGHT stilleri ile ilişkili.

- **Otomatik Buddy** otomatik buddy penceresindeki Değer değiştirme düğmesi için olarak Z düzeninde önceki pencereyi seçer. Bir iletişim şablonunda sekme sırasının değer değiştirme düğmesi önündeki denetim budur. UDS_AUTOBUDDY stil ile ilişkili.

- **Arkadaş tamsayı ayarlamak** artırmak ve geçerli konumu değiştikçe buddy penceresinin başlık azaltma döndürme denetimi neden olur. UDS_SETBUDDYINT stil ile ilişkili.

- **Binler** binlik eklemez buddy penceresinin başlık değerindeki ayırıcı. UDS_NOTHOUSANDS stil ile ilişkili.

    > [!NOTE]
    >  Arkadaş denetiminden tamsayı değerini almak için iletişim kutusu veri değişimi (DDX) kullanmak istiyorsanız bu stilini ayarlayın. `DDX_Text` Katıştırılmış binlik basamak ayırıcıları kabul etmiyor.

- **Kaydırma** "değer artırılması veya azaltılması denetim aralığının dışında olduğundan sarmalamak için" konumun neden olur. UDS_WRAP stil ile ilişkili.

- **Ok tuşları** artırın veya konumu yukarı ok ve aşağı ok tuşlarına basıldığında azaltma değer değiştirme düğmesi neden olur. UDS_ARROWKEYS stil ile ilişkili.

## <a name="see-also"></a>Ayrıca Bkz.

[CSpinButtonCtrl Kullanma](../mfc/using-cspinbuttonctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

