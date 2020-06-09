---
title: Hata Ayıklama ve Özel Durum Sınıfları
ms.date: 11/04/2016
f1_keywords:
- vc.classes.debug
helpviewer_keywords:
- debugging [MFC], exception classes
- debugging [MFC], classes for debugging
ms.assetid: 0d158efd-2e62-452e-9d2a-d3c30dfee7f9
ms.openlocfilehash: 6c7d1fc20556993c3c6690122786d7a767d895ad
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625930"
---
# <a name="debugging-and-exception-classes"></a>Hata Ayıklama ve Özel Durum Sınıfları

Bu sınıflar, dinamik bellek ayırmayı hata ayıklama ve özel durumun yakalandığında işlevin oluşturulduğu işlevden özel durum bilgilerini geçirme desteği sağlar.

[MFC uygulamalarında hata ayıklama](/visualstudio/debugger/mfc-debugging-techniques)konusunda açıklandığı gibi, hata ayıklamaya yardımcı olmak için geliştirme sırasında [CDumpContext](reference/cdumpcontext-class.md) ve [CMemoryState](reference/cmemorystate-structure.md) sınıflarını kullanın. Çalışma [zamanı sınıf bilgilerine erişme](accessing-run-time-class-information.md)makalesinde açıklandığı gibi, çalışma zamanında herhangi bir nesnenin sınıfını öğrenmek Için [CRuntimeClass](reference/cruntimeclass-structure.md) ' ı kullanın. Çerçeve, `CRuntimeClass` belirli bir sınıfın nesnelerini dinamik olarak oluşturmak için kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](class-library-overview.md)
