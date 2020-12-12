---
description: 'Daha fazla bilgi edinin: hata ayıklama ve özel durum sınıfları'
title: Hata Ayıklama ve Özel Durum Sınıfları
ms.date: 11/04/2016
f1_keywords:
- vc.classes.debug
helpviewer_keywords:
- debugging [MFC], exception classes
- debugging [MFC], classes for debugging
ms.assetid: 0d158efd-2e62-452e-9d2a-d3c30dfee7f9
ms.openlocfilehash: 2c14ea8d51fd1b63427ad1495e711a906e013ea4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291122"
---
# <a name="debugging-and-exception-classes"></a>Hata Ayıklama ve Özel Durum Sınıfları

Bu sınıflar, dinamik bellek ayırmayı hata ayıklama ve özel durumun yakalandığında işlevin oluşturulduğu işlevden özel durum bilgilerini geçirme desteği sağlar.

[MFC uygulamalarında hata ayıklama](/visualstudio/debugger/mfc-debugging-techniques)konusunda açıklandığı gibi, hata ayıklamaya yardımcı olmak için geliştirme sırasında [CDumpContext](reference/cdumpcontext-class.md) ve [CMemoryState](reference/cmemorystate-structure.md) sınıflarını kullanın. [Run-Time sınıfı bilgilerine erişme](accessing-run-time-class-information.md)makalesinde açıklandığı gibi, çalışma zamanında herhangi bir nesnenin sınıfını öğrenmek Için [CRuntimeClass](reference/cruntimeclass-structure.md) ' ı kullanın. Çerçeve, `CRuntimeClass` belirli bir sınıfın nesnelerini dinamik olarak oluşturmak için kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](class-library-overview.md)
