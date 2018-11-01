---
title: C çalışma zamanı hatası R6018
ms.date: 11/04/2016
f1_keywords:
- R6018
helpviewer_keywords:
- R6018
ms.assetid: f6dd40d1-a119-4d8b-b39e-97350ea23349
ms.openlocfilehash: e0d229b4fd8c1a4f8e067c0e59a278344fd4e113
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531924"
---
# <a name="c-runtime-error-r6018"></a>C çalışma zamanı hatası R6018

yığın beklenmeyen hata

> [!NOTE]
> Bir uygulama çalıştırırken bu hatayla karşılaşırsanız, dahili bir sorun olduğundan uygulaması kapatıldı. Bu hatanın birkaç olası nedeni vardır, ancak genellikle, uygulamanın koddaki bir hata nedeniyle oluşur.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** onarın veya programı yeniden yükleyin.
> - Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcıları için bilgi**

Program bir bellek yönetimi işlemi gerçekleştirilirken beklenmeyen bir hatayla karşılaştı.

Bu hata genellikle programın çalışma zamanı yığın verileri yanlışlıkla değiştirirse oluşur. Ancak, bu da işletim sistemi kod ve çalışma zamanı içinde bir iç hata neden olabilir.

Bu sorunu düzeltmek için kodunuzu yığın bozulması hataları kontrol edin. Daha fazla bilgi ve örnekler için bkz. [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ardından, uygulama dağıtımınız için en son yeniden dağıtılabilir dosyaları kullandığınızdan emin olun. Bilgi için [Visual C++ üzerinde dağıtım](../../ide/deployment-in-visual-cpp.md).