---
title: "Geçersiz kılınabilir CWinApp üye işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CWinApp
dev_langs: C++
helpviewer_keywords:
- overriding [MFC], overridable functions in CWinApp
- application class [MFC]
- CWinApp class [MFC], overridables
ms.assetid: 07183d5e-734b-45d9-a8b6-9dde4adac0b4
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3de4444aaeb55ab30ec6ce7e0ebd187c8468f673
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="overridable-cwinapp-member-functions"></a>Geçersiz Kılınabilir CWinApp Üye İşlevleri
[CWinApp](../mfc/reference/cwinapp-class.md) birkaç anahtar geçersiz kılınabilir üye işlevleri sağlar (`CWinApp` sınıfından bu üyeleri geçersiz kılar [CWinThread](../mfc/reference/cwinthread-class.md), içinden `CWinApp` türetilen):  
  
-   [InitInstance](../mfc/initinstance-member-function.md)  
  
-   [Çalıştırma](../mfc/run-member-function.md)  
  
-   [ExitInstance](../mfc/exitinstance-member-function.md)  
  
-   [ONIDLE](../mfc/onidle-member-function.md)  
  
 Yalnızca `CWinApp` geçersiz kılmanız gerekir üye işlevi `InitInstance`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWinApp: Uygulama sınıfı](../mfc/cwinapp-the-application-class.md)
