---
title: C çalışma zamanı hatası R6018 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6018
dev_langs:
- C++
helpviewer_keywords:
- R6018
ms.assetid: f6dd40d1-a119-4d8b-b39e-97350ea23349
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a2a35d57bb0136be6f47319c7f268d4fface3641
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2018
ms.locfileid: "48861603"
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