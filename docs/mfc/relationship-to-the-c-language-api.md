---
title: C dili API ilişkisi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.mfc
dev_langs:
- C++
helpviewer_keywords:
- books [MFC], about MFC and Windows SDK
- books [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- Windows API [MFC], and MFC
ms.assetid: 334e8efc-f3cc-4018-bc2e-02908b2a39fe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5d06c4adfa5493929a24c233fa923451c7bf0f95
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379235"
---
# <a name="relationship-to-the-c-language-api"></a>C Dili API'sına yönelik ilişki
Diğer sınıf kitaplıkları dışında Windows için Microsoft Foundation Class (MFC) kitaplığı ayarlayan tek karakteristiğini, C dilinde yazılmış Windows API çok yakın eşlemedir. Ayrıca, genellikle sınıf kitaplığı çağrıları serbestçe doğrudan Windows API çağrıları ile karıştırabilirsiniz. Bu doğrudan erişim ancak sınıflar bu API için tam yenileme olduğunu göstermez. Geliştiriciler hala bazen olmalısınız bazı Windows işlevleri için doğrudan çağrılar gibi [SetCursor](http://msdn.microsoft.com/library/windows/desktop/ms648393) ve [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385), örneğin. Yalnızca bunu yapmak için açık bir avantajı olduğunda bir Windows işlevi bir sınıf üye işlevi tarafından paketlenir.  
  
 Bazen yerel Windows işlev çağrıları yapma gerektiğinden, C dili Windows API belgelerine erişiminiz olması. Bu belge, Microsoft Visual C++ ile dahil edilir.  
  
> [!NOTE]
>  MFC Kitaplığı framework nasıl çalıştığını genel bakış için bkz: [yazma uygulamaları Windows için sınıfları kullanma](../mfc/using-the-classes-to-write-applications-for-windows.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel Sınıf Tasarımı Felsefesi](../mfc/general-class-design-philosophy.md)
