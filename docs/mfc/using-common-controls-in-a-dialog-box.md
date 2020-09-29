---
title: İletişim Kutusunda Ortak Denetimleri Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- common controls [MFC], in dialog boxes
- dialog box controls [MFC], common controls
- Windows common controls [MFC], in dialog boxes
ms.assetid: 17713caf-09f8-484a-bf54-5f48bf09cce9
ms.openlocfilehash: 1a3dcb7151952b52affcfeb838ced15f0d116fce
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91500343"
---
# <a name="using-common-controls-in-a-dialog-box"></a>İletişim Kutusunda Ortak Denetimleri Kullanma

Windows ortak denetimleri [iletişim kutularında](../mfc/dialog-boxes.md), form görünümlerinde, kayıt görünümlerinde ve bir iletişim şablonuna dayanan diğer herhangi bir pencerede kullanılabilir. Küçük değişikliklerle aşağıdaki yordam formlar için de çalışacaktır.

## <a name="procedures"></a>Yordamlar

#### <a name="to-use-a-common-control-in-a-dialog-box"></a>İletişim kutusunda ortak bir denetim kullanmak için

1. İletişim [kutusu düzenleyicisini kullanarak](../mfc/using-the-dialog-editor-to-add-controls.md)denetimi iletişim şablonuna yerleştirin.

1. İletişim kutusu sınıfına, denetimi temsil eden bir üye değişkeni ekleyin. **Üye değişkeni Ekle** Iletişim kutusunda **Denetim değişkenini** denetleyin ve **Kategori**için **denetimin** seçili olduğundan emin olun.

1. Bu ortak denetim programa giriş sağladıysanız, bu giriş değerlerini işlemek için diyalog sınıfında ek üye değişkenleri bildirin.

    > [!NOTE]
    >  Sınıf Görünümü içindeki bağlam menüsünü kullanarak bu üye değişkenlerini ekleyebilirsiniz (bkz. [üye değişkeni ekleme](../ide/adding-a-member-variable-visual-cpp.md)).

1. İletişim sınıfınız için [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) ' da, ortak denetim için başlangıç koşulları ' nı ayarlayın. Önceki adımda oluşturulan üye değişkenini kullanarak, ilk değeri ve diğer ayarları ayarlamak için üye işlevlerini kullanın. Ayarlarla ilgili ayrıntılar için aşağıdaki açıklamalara bakın.

   İletişim kutusunda denetimleri başlatmak için [iletişim kutusu veri değişimi](../mfc/dialog-data-exchange-and-validation.md) 'ni (DDX) de kullanabilirsiniz.

1. İletişim kutusundaki denetimler için işleyiciler ' de, denetimi işlemek için üye değişkenini kullanın. Yöntemleriyle ilgili ayrıntılar için aşağıdaki açıklamalara bakın.

    > [!NOTE]
    >  Üye değişkeni yalnızca iletişim kutusunun kendisi olduğu sürece var olur. İletişim kutusu kapatıldıktan sonra giriş değerleri için denetimi sorgulameyeceksiniz. Ortak bir denetimden gelen giriş değerleriyle çalışmak için `OnOK` iletişim sınıfınız içinde geçersiz kılın. Geçersiz kılmada, giriş değerleri için denetimi sorgulayın ve bu değerleri iletişim kutusu sınıfının üye değişkenlerinde saklayın.

    > [!NOTE]
    >  İletişim kutusundaki denetimlerden değerleri ayarlamak veya almak için iletişim kutusu veri değişimi de kullanabilirsiniz.

## <a name="remarks"></a>Açıklamalar

Bir iletişim kutusuna bazı yaygın denetimlerin eklenmesi iletişim kutusunun artık çalışmamasına neden olur. Iletişim kutusuna denetim eklemek için bkz. iletişim kutusu, bu durumu işleme hakkında daha fazla bilgi için [Iletişim kutusunun artık çalışmamasına neden olur](../windows/adding-editing-or-deleting-controls.md) .

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [İletişim kutusuna iletişim kutusu Düzenleyicisi yerine el ile denetim ekleme](../mfc/adding-controls-by-hand.md)

- [Standart Windows ortak denetimlerinden birinden denetimi türet](../mfc/deriving-controls-from-a-standard-control.md)

- [Ortak bir denetimi alt pencere olarak kullanma](../mfc/using-a-common-control-as-a-child-window.md)

- [Bir denetimden bildirim iletileri alma](../mfc/receiving-notification-from-common-controls.md)

- [İletişim kutusu veri değişimi (DDX) kullanma](../mfc/dialog-data-exchange-and-validation.md)

## <a name="see-also"></a>Ayrıca bkz.

[Denetimleri yapma ve kullanma](../mfc/making-and-using-controls.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
