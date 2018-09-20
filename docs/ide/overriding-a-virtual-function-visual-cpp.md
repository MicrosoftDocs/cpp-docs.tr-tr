---
title: (Visual C++) bir sanal işlevi geçersiz kılma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.virtualfunc.override
dev_langs:
- C++
helpviewer_keywords:
- virtual functions, overriding
- base classes, overriding virtual functions defined in
- Properties window, overriding virtual functions in
ms.assetid: 2d8c76f2-7a6b-4c9c-8de5-4282ce7755b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c150360294277653c777e5142cbf1dc57a97b2b2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409798"
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