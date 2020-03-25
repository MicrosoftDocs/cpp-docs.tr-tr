---
title: C Çalışma Zamanı Hatası R6018
ms.date: 11/04/2016
f1_keywords:
- R6018
helpviewer_keywords:
- R6018
ms.assetid: f6dd40d1-a119-4d8b-b39e-97350ea23349
ms.openlocfilehash: 83ad191fe1518e5e6bab0798840415ef392db71e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80197294"
---
# <a name="c-runtime-error-r6018"></a>C Çalışma Zamanı Hatası R6018

beklenmeyen yığın hatası

> [!NOTE]
> Bir uygulamayı çalıştırırken bu hata iletisiyle karşılaşırsanız, bir iç sorun olduğundan uygulama kapatıldı. Bu hatanın birkaç olası nedeni vardır, ancak genellikle uygulamanın kodundaki bir hata nedeniyle oluşur.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Programı onarmak ya da yeniden yüklemek için **Denetim Masası** 'ndaki **uygulamalar ve Özellikler** veya **Programlar ve Özellikler** sayfasını kullanın.
> - Yazılım güncelleştirmeleri için **Denetim Masası** 'ndaki **Windows Update** kontrol edin.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcılar için bilgiler**

Program, bellek yönetimi işlemini gerçekleştirirken beklenmeyen bir hatayla karşılaştı.

Bu hata genellikle, program yanlışlıkla çalışma zamanı yığın verilerini değiştirirse oluşur. Bununla birlikte, çalışma zamanı veya işletim sistemi kodundaki bir iç hata da oluşabilir.

Bu sorunu onarmak için kodunuzda yığın bozulması hatalarını kontrol edin. Daha fazla bilgi ve örnek için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Sonra, uygulama dağıtımınız için en son yeniden dağıtılabilir kullandığınızı kontrol edin. Bilgi için bkz. [Visual C++'te dağıtım ](../../windows/deployment-in-visual-cpp.md).
