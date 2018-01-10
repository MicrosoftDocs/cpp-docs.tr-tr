---
title: "C dili API ilişkisi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.mfc
dev_langs: C++
helpviewer_keywords:
- books [MFC], about MFC and Windows SDK
- books [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- Windows API [MFC], and MFC
ms.assetid: 334e8efc-f3cc-4018-bc2e-02908b2a39fe
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 26458242ab6afcf69d6e70065ba70e31f0adbe74
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="relationship-to-the-c-language-api"></a>C Dili API'sına yönelik ilişki
Diğer sınıf kitaplıkları dışında Windows için Microsoft Foundation Class (MFC) kitaplığı ayarlayan tek karakteristiğini, C dilinde yazılmış Windows API çok yakın eşlemedir. Ayrıca, genellikle sınıf kitaplığı çağrıları serbestçe doğrudan Windows API çağrıları ile karıştırabilirsiniz. Bu doğrudan erişim ancak sınıflar bu API için tam yenileme olduğunu göstermez. Geliştiriciler hala bazen olmalısınız bazı Windows işlevleri için doğrudan çağrılar gibi [SetCursor](http://msdn.microsoft.com/library/windows/desktop/ms648393) ve [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385), örneğin. Yalnızca bunu yapmak için açık bir avantajı olduğunda bir Windows işlevi bir sınıf üye işlevi tarafından paketlenir.  
  
 Bazen yerel Windows işlev çağrıları yapma gerektiğinden, C dili Windows API belgelerine erişiminiz olması. Bu belge, Microsoft Visual C++ ile dahil edilir.  
  
> [!NOTE]
>  MFC Kitaplığı framework nasıl çalıştığını genel bakış için bkz: [yazma uygulamaları Windows için sınıfları kullanma](../mfc/using-the-classes-to-write-applications-for-windows.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel Sınıf Tasarımı Felsefesi](../mfc/general-class-design-philosophy.md)
