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
ms.openlocfilehash: 994f81524001a80d1cf0dd3783b9de742d61e84d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365840"
---
# <a name="declaring-a-variable-based-on-your-new-control-class"></a>Yeni Denetim Sınıfınıza Dayalı Değişken Bildirme

Bir MFC denetim sınıfı oluşturduktan sonra, buna dayalı bir değişken bildirebilirsiniz. Yeni değişken için bir bağlam sağlamak için iletişim düzenleyicisini açmanız ve yeniden kullanılabilir denetiminizi kullanmak istediğiniz iletişim kutusunu yönetmeninizi yönetmeniniz gerekir. Ayrıca, iletişim kutusunun zaten onunla ilişkili bir sınıfı olmalıdır. İletişim düzenleyicisini kullanma hakkında daha fazla bilgi için [İletişim Düzenleyicisi'ne](../../windows/dialog-editor.md)bakın.

### <a name="to-declare-a-variable-based-on-your-reusable-class"></a>Yeniden kullanılabilir sınıfınızı temel alan bir değişkeni bildirmek için

1. İletişim kutusunu düzenlerken, Denetimler araç çubuğundan yeni denetiminizin taban sınıfıyla aynı türde bir denetimi iletişim kutusuna sürükleyin.

1. Fare işaretçisini bırakılan denetimin üzerine yerleştirin.

1. CTRL tuşuna basarken, denetimi çift tıklatın.

   [Üye Değişkenekle](../../ide/add-member-variable-wizard.md) iletişim kutusu görüntülenir.

1. **Access** kutusunda, denetiminiz için doğru erişimi seçin.

1. Denetimi **değişken** onay kutusunu tıklatın.

1. Değişken **ad** kutusuna bir ad yazın.

1. **Kategori**altında , **Denetim'i**tıklatın.

1. Denetim **Kimliği** listesinde, eklediğiniz denetimi seçin. **Değişken türü** listesi doğru değişken türünü, **Denetim türü** kutusu ise doğru denetim türünü görüntülemelidir.

1. **Açıklama** kutusuna, kodunuzda görünmesini istediğiniz herhangi bir yorumu ekleyin.

1. **Tamam**'a tıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[İletileri İşlevlere Eşleme](../../mfc/reference/mapping-messages-to-functions.md)<br/>
[Kod Sihirbazlarıyla İşlevsellik Ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Sınıf Ekleme](../../ide/adding-a-class-visual-cpp.md)<br/>
[Üye İşlev Ekleme](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Üye Değişkeni Ekleme](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Sanal İşlev Geçersiz Kılma](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC İleti Işleyicisi](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Sınıf Yapısında Gezinme](../../ide/navigate-code-cpp.md)
