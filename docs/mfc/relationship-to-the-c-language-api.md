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
ms.openlocfilehash: 1fbd4d332f5ade1cb9415448b138ac5bc838307d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372822"
---
# <a name="relationship-to-the-c-language-api"></a>C Dili API'sına yönelik ilişki

Microsoft Hazırlık Sınıfı (MFC) Kitaplığını Windows için diğer sınıf kitaplıklarından ayıran tek özellik, C dilinde yazılmış Windows API'sine çok yakın eşlemedir. Ayrıca, genellikle sınıf kitaplığına yapılan çağrıları Windows API'ye doğrudan çağrılarla serbestçe karıştırabilirsiniz. Ancak bu doğrudan erişim, sınıfların bu API'nin tam bir yerine olduğu anlamına gelmez. Geliştiriciler yine de bazen [SetCursor](/windows/win32/api/winuser/nf-winuser-setcursor) ve [GetSystemMetrics](/windows/win32/api/winuser/nf-winuser-getsystemmetrics)gibi bazı Windows işlevleri, örneğin doğrudan aramalar yapmak gerekir. Windows işlevi, yalnızca bunu yapmanın açık bir avantajı olduğunda bir sınıf üyesi işlevi tarafından sarılır.

Bazen ana Windows işlev çağrıları yapmanız gerektiğinden, C dili Windows API belgelerine erişiminiz olmalıdır. Bu dokümantasyon Microsoft Visual C++'a dahildir.

> [!NOTE]
> MFC Kitaplığı çerçevesinin nasıl çalıştığına genel bir bakış için windows [için uygulama yazmak için sınıfları kullanma bölümüne](../mfc/using-the-classes-to-write-applications-for-windows.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Genel Sınıf Tasarımı Felsefesi](../mfc/general-class-design-philosophy.md)
