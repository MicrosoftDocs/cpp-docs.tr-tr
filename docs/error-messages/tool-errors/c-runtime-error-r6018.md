---
title: C Çalışma Zamanı Hatası R6018
ms.date: 11/04/2016
f1_keywords:
- R6018
helpviewer_keywords:
- R6018
ms.assetid: f6dd40d1-a119-4d8b-b39e-97350ea23349
ms.openlocfilehash: b36e2184e5be131645fb4dd58a361fdb9a31da63
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58774985"
---
# <a name="c-runtime-error-r6018"></a>C Çalışma Zamanı Hatası R6018

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

Bu sorunu düzeltmek için kodunuzu yığın bozulması hataları kontrol edin. Daha fazla bilgi ve örnekler için bkz. [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ardından, uygulama dağıtımınız için en son yeniden dağıtılabilir dosyaları kullandığınızdan emin olun. Bilgi için [Visual C++ üzerinde dağıtım](../../windows/deployment-in-visual-cpp.md).