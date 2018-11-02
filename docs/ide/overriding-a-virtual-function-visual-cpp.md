---
title: Sanal İşlevi Geçersiz Kılma (Visual C++)
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.virtualfunc.override
helpviewer_keywords:
- virtual functions, overriding
- base classes, overriding virtual functions defined in
- Properties window, overriding virtual functions in
ms.assetid: 2d8c76f2-7a6b-4c9c-8de5-4282ce7755b6
ms.openlocfilehash: 193c84d2b9a0fe50ae84d3e69834feab27342042
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484148"
---
# <a name="overriding-a-virtual-function-visual-c"></a>Sanal İşlevi Geçersiz Kılma (Visual C++)

Visual Studio temel sınıfta tanımlı sanal işlevleri geçersiz kılma [Özellikler penceresi](/visualstudio/ide/reference/properties-window).

### <a name="to-override-a-virtual-function-in-the-properties-window"></a>Özellikler penceresinde bir sanal işlev geçersiz kılınamıyor

1. Sınıf Görünümü'nde sınıfı tıklayın.

1. Özellikler penceresinde tıklayın **geçersiz kılmalar** düğmesi.

   > [!NOTE]
   >  **Geçersiz kılmalar** düğmesi, sınıf görünümü veya kaynak pencereye tıkladığınızda, sınıf adı seçtiğinizde kullanılabilir.

   Sol sütunda, sanal işlevleri listeler. Sanal bir işlevin adını sağ sütunda da görünüyorsa, bir geçersiz kılma zaten uygulandı.

1. İşlev geçersiz kılma hücrenin sağ sütunda önerilen işlevin adını görüntülemek için Özellikler penceresindeki'a tıklayın, varsa olarak geçersiz kılma \<Ekle >*FuncName*.

1. İşlev için saptama kodu eklemek için önerilen adına tıklayın.

1. Bir geçersiz kılma işlevi düzenlemek için Sınıf Görünümü'nde işlev adına çift tıklayın ve kaynak penceresinde kodu düzenleyin.

Bir geçersiz kılma kaldırmak için sağ sütunda geçersiz kılma işlev adına tıklayın ve seçin \<sil >*FuncName*. İşlev kod dışı bırakılmıştır.

## <a name="see-also"></a>Ayrıca Bkz.

[Kod sihirbazlarıyla işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md)<br>
[Sınıf ekleme](../ide/adding-a-class-visual-cpp.md)<br>
[Üye işlevi ekleme](../ide/adding-a-member-function-visual-cpp.md)<br>
[Üye değişkeni ekleme](../ide/adding-a-member-variable-visual-cpp.md)<br>
[MFC ileti işleyicisi](../mfc/reference/adding-an-mfc-message-handler.md)<br>
[Sınıf yapısında gezinme](../ide/navigating-the-class-structure-visual-cpp.md)