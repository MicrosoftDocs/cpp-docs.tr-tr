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
ms.openlocfilehash: d550b80beb124f3d8ec36ba81dad1a9ca7e9fa15
ms.sourcegitcommit: 65ed563a8a1d4d90f872a2a6edcb086f84ec9f77
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/06/2019
ms.locfileid: "66741613"
---
# <a name="declaring-a-variable-based-on-your-new-control-class"></a>Yeni Denetim Sınıfınıza Dayalı Değişken Bildirme

MFC denetim sınıfı oluşturduktan sonra bunu temel alan bir değişken bildirebilirsiniz. Yeni değişken için bir bağlam sağlamak için iletişim kutusu düzenleyicisini açın ve yeniden kullanılabilir denetiminizi kullanmak istediğiniz iletişim kutusu düzenlemeniz gerekir. Ayrıca, iletişim kutusu zaten kendisiyle ilişkilendirilmiş bir sınıf olması gerekir. İletişim kutusu düzenleyicisini kullanma hakkında daha fazla bilgi için bkz: [iletişim kutusu Düzenleyicisi](../../windows/dialog-editor.md).

### <a name="to-declare-a-variable-based-on-your-reusable-class"></a>Yeniden kullanılabilir sınıfınıza dayalı değişken bildirme

1. İletişim kutusu düzenlerken, yeni denetiminizin temel sınıf olarak aynı türde bir denetim iletişim kutusunun denetimleri araç çubuğuna sürükleyin.

1. Fare işaretçisini bırakılan denetimin üzerine getirin.

1. CTRL tuşunu basılı tutarak denetimi çift tıklatın.

   [Üye değişkeni ekleme](../../ide/add-member-variable-wizard.md) iletişim kutusu görüntülenir.

1. İçinde **erişim** kutusunda, denetiminiz için doğru erişim'i seçin.

1. Tıklayın **denetim değişkeni** onay kutusu.

1. İçinde **değişken adı** bir ad yazın.

1. Altında **kategori**, tıklayın **denetim**.

1. İçinde **denetim kimliği** listesinde, eklediğiniz denetimin seçin. **Değişken türü** listesi doğru değişken türü olarak görüntülenmelidir ve **denetim türü** doğru denetim türünü kutusu görüntülenmelidir.

9. İçinde **yorum** kutusunda, kodunuzda görünmesini istediğiniz herhangi bir yorum ekleyin.

10. **Tamam**'ı tıklatın.

## <a name="see-also"></a>Ayrıca bkz.

[İletileri İşlevlere Eşleme](../../mfc/reference/mapping-messages-to-functions.md)<br/>
[Kod Sihirbazlarıyla İşlevsellik Ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)<br/>
[Üye işlevi ekleme](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Üye değişkeni ekleme](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Bir sanal işlevi geçersiz kılma](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC ileti işleyicisi](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Sınıf yapısında gezinme](../../ide/navigate-code-cpp.md)
