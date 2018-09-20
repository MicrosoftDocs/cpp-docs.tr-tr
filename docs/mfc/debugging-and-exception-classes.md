---
title: Hata ayıklama ve özel durum sınıfları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.debug
dev_langs:
- C++
helpviewer_keywords:
- debugging [MFC], exception classes
- debugging [MFC], classes for debugging
ms.assetid: 0d158efd-2e62-452e-9d2a-d3c30dfee7f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b7c88c5d12f56318bbb37a825e28c2bfcbc132d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418183"
---
# <a name="debugging-and-exception-classes"></a>Hata Ayıklama ve Özel Durum Sınıfları

Bu sınıflar, dinamik bellek ayırma hatalarını ayıklama ve özel durum bilgilerini işlevden burada işleve burada Yakalanan özel durum geçirme için destek sağlar.

Sınıfları kullanan [CDumpContext](../mfc/reference/cdumpcontext-class.md) ve [CMemoryState](../mfc/reference/cmemorystate-structure.md) açıklandığı gibi hata ayıklama ile yardımcı olmak için geliştirme sırasında [hata ayıklama MFC uygulamaları](/visualstudio/debugger/mfc-debugging-techniques). Kullanım [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) makalesinde açıklandığı gibi çalışma zamanında, herhangi bir nesnenin sınıfını belirlemek için [çalışma süresi sınıf bilgilerine erişme](../mfc/accessing-run-time-class-information.md). Framework kullanan `CRuntimeClass` belirli bir sınıfın nesnelerini dinamik olarak oluşturmak için.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)

