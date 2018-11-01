---
title: C Dili API'sına yönelik ilişki
ms.date: 11/04/2016
f1_keywords:
- vc.classes.mfc
helpviewer_keywords:
- books [MFC], about MFC and Windows SDK
- books [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- Windows API [MFC], and MFC
ms.assetid: 334e8efc-f3cc-4018-bc2e-02908b2a39fe
ms.openlocfilehash: 8f58a33d3accb8eb81299877df1b0c8a4ebe0576
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525703"
---
# <a name="relationship-to-the-c-language-api"></a>C Dili API'sına yönelik ilişki

Microsoft Foundation Class (MFC) kitaplığı dışında diğer sınıf kitaplıkları için Windows ayarlar tek bir özellik C dilinde yazılan Windows API çok yakın eşleme bir. Ayrıca, genellikle çağrıları sınıf kitaplığı serbestçe Windows API'sine doğrudan çağrı içeren karıştırabilirsiniz. Bu doğrudan erişim ancak sınıfları bu API için tam bir değiştirme olduğunu göstermez. Geliştiriciler hala bazen olmalısınız bazı Windows işlevlere doğrudan çağrıları gibi [SetCursor](/windows/desktop/api/winuser/nf-winuser-setcursor) ve [GetSystemMetrics](/windows/desktop/api/winuser/nf-winuser-getsystemmetrics), örneğin. Bunun yapılması için açık bir avantaj olduğunda bir Windows işlevi bir sınıf üyesi işlevi paketlenir.

Bazen yerel Windows işlev çağrıları yapmanız gerektiğinden, C dili Windows API belgelerine erişimi olmalıdır. Bu belge, Microsoft Visual C++ ile dahildir.

> [!NOTE]
>  MFC Kitaplığı Framework'te nasıl çalıştığı genel bakış için bkz: [yazma uygulamaları için Windows için sınıfları kullanma](../mfc/using-the-classes-to-write-applications-for-windows.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Genel Sınıf Tasarımı Felsefesi](../mfc/general-class-design-philosophy.md)
