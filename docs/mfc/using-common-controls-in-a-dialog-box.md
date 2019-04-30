---
title: İletişim Kutusunda Ortak Denetimleri Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- common controls [MFC], in dialog boxes
- dialog box controls [MFC], common controls
- Windows common controls [MFC], in dialog boxes
ms.assetid: 17713caf-09f8-484a-bf54-5f48bf09cce9
ms.openlocfilehash: ade1b464d3851fb9294a1ba7180b48771f0468cc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411792"
---
# <a name="using-common-controls-in-a-dialog-box"></a>İletişim Kutusunda Ortak Denetimleri Kullanma

Windows ortak denetimleri kullanılabilir [iletişim kutuları](../mfc/dialog-boxes.md), görünümleri, kayıt görünümleri ve bir iletişim şablonunu temel alarak başka bir pencere oluşturur. Aşağıdaki yordam, bazı küçük değişikliklerle forms de çalışır.

## <a name="procedures"></a>Yordamlar

#### <a name="to-use-a-common-control-in-a-dialog-box"></a>İletişim kutusunda bir ortak denetimi kullanmak için

1. Bir iletişim şablonunu denetimi yerleştirin [iletişim kutusu düzenleyicisini kullanma](../mfc/using-the-dialog-editor-to-add-controls.md).

1. İletişim kutusu sınıfı için denetimini temsil eden bir üye değişkeni ekleyin. İçinde **üye değişkeni ekleme** iletişim kutusu, onay **denetim değişkeni** olduğundan emin olun **denetimi** seçildiğini **kategori**.

1. Bu yaygın bir denetim girişi programa sağlıyorsa ek üye bildirmek variable(s) olanlar işlemek için iletişim kutusu sınıfı içinde giriş değerleri.

    > [!NOTE]
    >  Sınıf Görünümü'nde bağlam menüsünü kullanarak bu üye değişkenleri ekleyebilirsiniz (bkz [bir üye değişkeni ekleme](../ide/adding-a-member-variable-visual-cpp.md)).

1. İçinde [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) iletişim sınıfınızı için ortak denetimi için ilk koşulları ayarlayın. Üye işlevleri, önceki adımda oluşturulan üye değişkeni kullanarak, ilk değer ve diğer ayarları ayarlamak için kullanın. Denetimleri ayrıntıları için aşağıdaki açıklamaları ayarlarına bakın.

   Ayrıca [iletişim kutusu veri değişimi](../mfc/dialog-data-exchange-and-validation.md) (DDX) iletişim kutusunda denetimleri başlatılamadı.

1. İletişim kutusundaki denetimler için işleyiciler içinde üye değişkeni, denetimi işlemek için kullanın. Ayrıntılar için denetimleri aşağıdaki açıklamaları yöntemlerde bakın.

    > [!NOTE]
    >  İletişim kutusu yalnızca mevcut olduğu sürece bir üye değişkeni bulunur. İletişim kutusu kapatıldıktan sonra denetim için giriş değerlerini sorgulamak mümkün olmayacaktır. Bir ortak denetimi giriş değerlerini çalışmak için geçersiz kılma `OnOK` iletişim sınıfınızdaki. Geçersiz kılma, denetim için giriş değerlerini sorgulamak ve iletişim kutusu sınıfı üye değişkenlerinde bu değerleri depolamak.

    > [!NOTE]
    >  İletişim kutusu veri değişimi, bir iletişim kutusu denetimleri değerleri almak veya ayarlamak için de kullanabilirsiniz.

## <a name="remarks"></a>Açıklamalar

Bazı ortak bir iletişim kutusu denetimlerine ekleme iletişim kutusuna çalışmamasına neden olur. Başvurmak [bir iletişim kutusu denetimlerine ekleme iletişim kutusu artık işlev için neden](../windows/adding-controls-to-a-dialog-causes-the-dialog-to-no-longer-function.md) bu durum işleme hakkında daha fazla bilgi.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz

- [Denetimleri bir Ekle iletişim kutusu için el ile yerine ile iletişim kutusu Düzenleyicisi](../mfc/adding-controls-by-hand.md)

- [My denetimi bir standart Windows ortak denetimleri noktasından türettikten](../mfc/deriving-controls-from-a-standard-control.md)

- [Bir ortak denetimi alt pencere olarak kullanma](../mfc/using-a-common-control-as-a-child-window.md)

- [Bir denetimi bildirim iletilerini alma](../mfc/receiving-notification-from-common-controls.md)

- [İletişim kutusu veri değişimi (DDX) kullanın](../mfc/dialog-data-exchange-and-validation.md)

## <a name="see-also"></a>Ayrıca bkz.

[Denetimleri Yapma ve Kullanma](../mfc/making-and-using-controls.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
