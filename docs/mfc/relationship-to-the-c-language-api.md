---
title: C Dili API'sına yönelik ilişki
ms.date: 11/04/2016
helpviewer_keywords:
- books [MFC], about MFC and Windows SDK
- books [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- Windows API [MFC], and MFC
ms.assetid: 334e8efc-f3cc-4018-bc2e-02908b2a39fe
ms.openlocfilehash: c52b11a7395e3972f8bf9d83501fbafb61e6f4a6
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446380"
---
# <a name="relationship-to-the-c-language-api"></a>C Dili API'sına yönelik ilişki

Microsoft Foundation Class (MFC) kitaplığını Windows için diğer sınıf kitaplıklarından ayrı ayarlayan tek özellik C dilinde yazılan Windows API 'sine yönelik çok yakın eşlemedir. Ayrıca, genellikle Windows API 'sine doğrudan çağrılar ile sınıf kitaplığına yapılan çağrıları serbestçe karıştırabilirsiniz. Ancak bu doğrudan erişim, sınıfların bu API için bir bütün olarak değişiklik olduğunu göstermez. Geliştiriciler yine de [SetCursor](/windows/win32/api/winuser/nf-winuser-setcursor) ve [getsystemölçümleri](/windows/win32/api/winuser/nf-winuser-getsystemmetrics)gibi bazı Windows işlevlerine doğrudan çağrı yapmalıdır. Bir Windows işlevi, bir sınıf üyesi işlevi tarafından yalnızca bunu yapmanın açık bir avantajı olduğunda sarmalanır.

Bazen yerel Windows işlev çağrıları yapmanız gerektiğinden, C dili Windows API belgelerine erişiminizin olması gerekir. Bu belge Microsoft Visual C++ile birlikte gelir.

> [!NOTE]
>  MFC kitaplık çerçevesinin nasıl çalıştığı hakkında genel bir bakış için bkz. [Windows Için uygulama yazmak üzere sınıfları kullanma](../mfc/using-the-classes-to-write-applications-for-windows.md).

## <a name="see-also"></a>Ayrıca bkz.

[Genel Sınıf Tasarımı Felsefesi](../mfc/general-class-design-philosophy.md)
