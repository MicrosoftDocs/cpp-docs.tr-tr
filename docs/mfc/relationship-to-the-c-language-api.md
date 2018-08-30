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
ms.openlocfilehash: 8d0bb7aa4f647ceeb61c20cccd626d9da999b241
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43200118"
---
# <a name="relationship-to-the-c-language-api"></a>C Dili API'sına yönelik ilişki
Microsoft Foundation Class (MFC) kitaplığı dışında diğer sınıf kitaplıkları için Windows ayarlar tek bir özellik C dilinde yazılan Windows API çok yakın eşleme bir. Ayrıca, genellikle çağrıları sınıf kitaplığı serbestçe Windows API'sine doğrudan çağrı içeren karıştırabilirsiniz. Bu doğrudan erişim ancak sınıfları bu API için tam bir değiştirme olduğunu göstermez. Geliştiriciler hala bazen olmalısınız bazı Windows işlevlere doğrudan çağrıları gibi [SetCursor](/windows/desktop/api/winuser/nf-winuser-setcursor) ve [GetSystemMetrics](https://msdn.microsoft.com/library/windows/desktop/ms724385), örneğin. Bunun yapılması için açık bir avantaj olduğunda bir Windows işlevi bir sınıf üyesi işlevi paketlenir.  
  
 Bazen yerel Windows işlev çağrıları yapmanız gerektiğinden, C dili Windows API belgelerine erişimi olmalıdır. Bu belge, Microsoft Visual C++ ile dahildir.  
  
> [!NOTE]
>  MFC Kitaplığı Framework'te nasıl çalıştığı genel bakış için bkz: [yazma uygulamaları için Windows için sınıfları kullanma](../mfc/using-the-classes-to-write-applications-for-windows.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel Sınıf Tasarımı Felsefesi](../mfc/general-class-design-philosophy.md)
