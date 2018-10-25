---
title: Yeni Denetim sınıfınıza dayalı değişken bildirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.classes.control.variable
dev_langs:
- C++
helpviewer_keywords:
- variables [MFC], control classes
- control classes [MFC], variables
- classes [MFC], declaring variables based on
ms.assetid: 5722dc38-c0eb-40bd-93da-67a808140d03
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6d2e5e91465df0c3e7608b949c6e1f4b8dfc80bc
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50064153"
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

## <a name="see-also"></a>Ayrıca Bkz.

[İletileri İşlevlere Eşleme](../../mfc/reference/mapping-messages-to-functions.md)<br/>
[Kod sihirbazlarıyla işlevsellik ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)<br/>
[Üye işlevi ekleme](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Üye değişkeni ekleme](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Bir sanal işlevi geçersiz kılma](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC ileti işleyicisi](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Sınıf yapısında gezinme](../../ide/navigating-the-class-structure-visual-cpp.md)
