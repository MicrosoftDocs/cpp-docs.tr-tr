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
ms.workload: cplusplus
ms.openlocfilehash: 64775ad9f44c55529107b50d0695e95e2b9c3a2f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="overridable-cwinapp-member-functions"></a>Geçersiz Kılınabilir CWinApp Üye İşlevleri
[CWinApp](../mfc/reference/cwinapp-class.md) birkaç anahtar geçersiz kılınabilir üye işlevleri sağlar (`CWinApp` sınıfından bu üyeleri geçersiz kılar [CWinThread](../mfc/reference/cwinthread-class.md), içinden `CWinApp` türetilen):  
  
-   [InitInstance](../mfc/initinstance-member-function.md)  
  
-   [Çalıştırma](../mfc/run-member-function.md)  
  
-   [ExitInstance](../mfc/exitinstance-member-function.md)  
  
-   [ONIDLE](../mfc/onidle-member-function.md)  
  
 Yalnızca `CWinApp` geçersiz kılmanız gerekir üye işlevi `InitInstance`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWinApp: Uygulama Sınıfı](../mfc/cwinapp-the-application-class.md)
