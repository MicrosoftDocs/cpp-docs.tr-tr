---
title: Yeni Denetim Sınıfınıza Dayalı Değişken Bildirme
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.classes.control.variable
helpviewer_keywords:
- variables [MFC], control classes
- control classes [MFC], variables
- classes [MFC], declaring variables based on
ms.assetid: 5722dc38-c0eb-40bd-93da-67a808140d03
ms.openlocfilehash: a828351a9e789228143d43d4c0a756abda879989
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91506677"
---
# <a name="declaring-a-variable-based-on-your-new-control-class"></a>Yeni Denetim Sınıfınıza Dayalı Değişken Bildirme

Bir MFC denetim sınıfı oluşturduktan sonra, ona göre bir değişken bildirebilirsiniz. Yeni değişken için bir bağlam sağlamak üzere, iletişim kutusu düzenleyicisini açmanız ve yeniden kullanılabilir denetiminizi kullanmak istediğiniz iletişim kutusunu düzenlemeniz gerekir. Ayrıca, iletişim kutusunda onunla ilişkilendirilmiş bir sınıf zaten olmalıdır. İletişim kutusu düzenleyicisini kullanma hakkında daha fazla bilgi için bkz. [Iletişim kutusu Düzenleyicisi](../../windows/dialog-editor.md).

### <a name="to-declare-a-variable-based-on-your-reusable-class"></a>Yeniden kullanılabilir sınıfınıza göre bir değişken bildirmek için

1. İletişim kutusunu düzenlenirken, denetimler araç çubuğundan, iletişim kutusunda aynı türdeki bir denetimi yeni denetiminizin temel sınıfıyla sürükleyin.

1. Fare işaretçisini bırakılan denetimin üzerine yerleştirin.

1. CTRL tuşuna basıldığında denetime çift tıklayın.

   [Üye değişkeni Ekle](../../ide/adding-a-member-variable-visual-cpp.md#add-member-variable-wizard) iletişim kutusu görüntülenir.

1. **Erişim** kutusunda, denetiminiz için doğru erişimi seçin.

1. **Denetim değişkeni** onay kutusuna tıklayın.

1. **Değişken adı** kutusuna bir ad yazın.

1. **Kategori**altında **Denetim**' e tıklayın.

1. **DENETIM kimliği** listesinde, eklediğiniz denetimi seçin. **Değişken türü** listesi doğru değişken türünü görüntülemelidir ve **Denetim türü** kutusu doğru denetim türünü görüntülemelidir.

1. **Yorum** kutusuna kodunuzda görünmesini istediğiniz herhangi bir yorumu ekleyin.

1. **Tamam**'a tıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[Iletileri IŞLEVLERE eşleme](../../mfc/reference/mapping-messages-to-functions.md)<br/>
[Kod Sihirbazlarıyla İşlevsellik Ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)<br/>
[Üye Işlevi ekleme](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Üye değişkeni ekleme](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Sanal Işlevi geçersiz kılma](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC Ileti Işleyicisi](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Sınıf yapısında gezinme](../../ide/navigate-code-cpp.md)
