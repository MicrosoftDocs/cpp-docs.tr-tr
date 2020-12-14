---
description: 'Hakkında daha fazla bilgi edinin: C dili API ile Ilişki'
title: C Dili API'sına yönelik ilişki
ms.date: 11/04/2016
helpviewer_keywords:
- books [MFC], about MFC and Windows SDK
- books [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- Windows API [MFC], and MFC
ms.assetid: 334e8efc-f3cc-4018-bc2e-02908b2a39fe
ms.openlocfilehash: fdfc03d9e8379ee4f19452ce81cba9957930bfe4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218075"
---
# <a name="relationship-to-the-c-language-api"></a>C Dili API'sına yönelik ilişki

Microsoft Foundation Class (MFC) kitaplığını Windows için diğer sınıf kitaplıklarından ayrı ayarlayan tek özellik C dilinde yazılan Windows API 'sine yönelik çok yakın eşlemedir. Ayrıca, genellikle Windows API 'sine doğrudan çağrılar ile sınıf kitaplığına yapılan çağrıları serbestçe karıştırabilirsiniz. Ancak bu doğrudan erişim, sınıfların bu API için bir bütün olarak değişiklik olduğunu göstermez. Geliştiriciler yine de [SetCursor](/windows/win32/api/winuser/nf-winuser-setcursor) ve [getsystemölçümleri](/windows/win32/api/winuser/nf-winuser-getsystemmetrics)gibi bazı Windows işlevlerine doğrudan çağrı yapmalıdır. Bir Windows işlevi, bir sınıf üyesi işlevi tarafından yalnızca bunu yapmanın açık bir avantajı olduğunda sarmalanır.

Bazen yerel Windows işlev çağrıları yapmanız gerektiğinden, C dili Windows API belgelerine erişiminizin olması gerekir. Bu belge Microsoft Visual C++ eklenmiştir.

> [!NOTE]
> MFC kitaplık çerçevesinin nasıl çalıştığı hakkında genel bir bakış için bkz. [Windows Için uygulama yazmak üzere sınıfları kullanma](../mfc/using-the-classes-to-write-applications-for-windows.md).

## <a name="see-also"></a>Ayrıca bkz.

[Genel sınıf tasarımı Felseno](../mfc/general-class-design-philosophy.md)
