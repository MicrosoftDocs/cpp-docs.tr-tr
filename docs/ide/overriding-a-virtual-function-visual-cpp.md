---
title: Sanal işlevi (Visual C++) geçersiz kılma | Microsoft Docs
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
ms.openlocfilehash: d8580d27442b0cae7e343a568beaa9aeae500461
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="overriding-a-virtual-function-visual-c"></a>Sanal İşlevi Geçersiz Kılma (Visual C++)
Visual Studio'dan bir taban sınıf içinde tanımlı sanal işlevleri geçersiz kılma [Özellikler penceresini](/visualstudio/ide/reference/properties-window).  
  
### <a name="to-override-a-virtual-function-in-the-properties-window"></a>Özellikleri penceresinde sanal işlevi geçersiz kılmak için  
  
1.  Sınıf Görünümü'nde sınıfı'ı tıklatın.  
  
2.  Özellikler penceresinde **geçersiz kılmaları** düğmesi.  
  
    > [!NOTE]
    >  **Geçersiz kılmaları** düğmesi, sınıf görünümünde veya kaynak pencereye tıkladığınızda, sınıf adını seçtiğinizde kullanılabilir.  
  
     Sol sütunda sanal işlevleri listeler. Sanal bir işlevin adını sağ sütunda da görünüyorsa, bir geçersiz kılma zaten uygulanmıştır.  
  
3.  İşlevi geçersiz kılma işlevi önerilen adını görüntülemek için Özellikler penceresini sağ sütunda hücreyi tıklatın, varsa olarak geçersiz kılma \<Ekle >*FuncName*.  
  
4.  İşlev için saplama kodu eklemek için önerilen adına tıklayın.  
  
5.  Bir geçersiz kılma işlevi düzenlemek için Sınıf Görünümü'nde işlevi adına çift tıklayın ve kaynak penceresini kodda düzenleyin.  
  
 Bir geçersiz kılma kaldırmak için sağ sütunda geçersiz kılma işlevi adına tıklayın ve seçin \<sil >*FuncName*. İşlevin kodunu dışı bırakılmıştır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kod sihirbazlarıyla işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Sınıf ekleme](../ide/adding-a-class-visual-cpp.md)   
 [Üye işlevi ekleme](../ide/adding-a-member-function-visual-cpp.md)   
 [Üye değişkeni ekleme](../ide/adding-a-member-variable-visual-cpp.md)   
 [MFC ileti işleyicisi](../mfc/reference/adding-an-mfc-message-handler.md)   
 [Sınıf yapısında gezinme](../ide/navigating-the-class-structure-visual-cpp.md)