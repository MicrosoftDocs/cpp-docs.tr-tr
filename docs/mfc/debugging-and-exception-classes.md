---
title: Hata Ayıklama ve Özel Durum Sınıfları
ms.date: 11/04/2016
f1_keywords:
- vc.classes.debug
helpviewer_keywords:
- debugging [MFC], exception classes
- debugging [MFC], classes for debugging
ms.assetid: 0d158efd-2e62-452e-9d2a-d3c30dfee7f9
ms.openlocfilehash: 328d7a38c544b56f83ea3e8b1136b1122c4dfa14
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62241194"
---
# <a name="debugging-and-exception-classes"></a>Hata Ayıklama ve Özel Durum Sınıfları

Bu sınıflar, dinamik bellek ayırma hatalarını ayıklama ve özel durum bilgilerini işlevden burada işleve burada Yakalanan özel durum geçirme için destek sağlar.

Sınıfları kullanan [CDumpContext](../mfc/reference/cdumpcontext-class.md) ve [CMemoryState](../mfc/reference/cmemorystate-structure.md) açıklandığı gibi hata ayıklama ile yardımcı olmak için geliştirme sırasında [hata ayıklama MFC uygulamaları](/visualstudio/debugger/mfc-debugging-techniques). Kullanım [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) makalesinde açıklandığı gibi çalışma zamanında, herhangi bir nesnenin sınıfını belirlemek için [çalışma süresi sınıf bilgilerine erişme](../mfc/accessing-run-time-class-information.md). Framework kullanan `CRuntimeClass` belirli bir sınıfın nesnelerini dinamik olarak oluşturmak için.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)
