---
title: "Kod sihirbazları olmadan denetimlere tür kullanımı uyumlu erişim | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- dialog boxes [MFC], accessing controls
- dialog box controls [MFC], accessing
ms.assetid: 325b4927-d49b-42b4-8e0b-fc84f31fb059
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 50206ec8196247deb4a63f7ac2685eed47fab5bb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="type-safe-access-to-controls-without-code-wizards"></a>Kod Sihirbazları Olmadan Denetimlere Tür Kullanımı Uyumlu Erişim
Sınıfı'nin dönüş türünü dönüştürmek için bir satır içi üye işlevi denetimlere tür kullanımı uyumlu erişim oluşturmanın ilk yaklaşımı kullanır `CWnd`'s `GetDlgItem` üye işlevi bu örnekte olduğu gibi uygun C++ denetim türü için:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#50](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_1.cpp)]  
  
 Bu üye işlevi sonra aşağıdakine benzer bir kod ile bir tür kullanımı uyumlu şekilde erişim denetimi için de kullanabilirsiniz:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#51](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_2.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir iletişim kutusundaki denetimlere tür kullanımı uyumlu erişim](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)   
 [Kod sihirbazları kullanarak denetimlere tür kullanımı uyumlu erişim](../mfc/type-safe-access-to-controls-with-code-wizards.md)

