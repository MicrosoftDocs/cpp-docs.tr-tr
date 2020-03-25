---
title: C Çalışma Zamanı Hatası R6017
ms.date: 11/04/2016
f1_keywords:
- R6017
helpviewer_keywords:
- R6017
ms.assetid: df3ec5f5-6771-4648-ba06-0e26c6a1cc6a
ms.openlocfilehash: 2d868939425c11f13dffd84e28c1afee45e3b11a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80197308"
---
# <a name="c-runtime-error-r6017"></a>C Çalışma Zamanı Hatası R6017

beklenmeyen çoklu iş parçacığı kilit hatası

> [!NOTE]
> Bir uygulamayı çalıştırırken bu hata iletisiyle karşılaşırsanız, bir iç sorun olduğundan uygulama kapatıldı. Bu hatanın birkaç olası nedeni vardır, ancak genellikle uygulamanın kodundaki bir hata nedeniyle oluşur.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Programı onarmak ya da yeniden yüklemek için **Denetim Masası** 'ndaki **uygulamalar ve Özellikler** veya **Programlar ve Özellikler** sayfasını kullanın.
> - Yazılım güncelleştirmeleri için **Denetim Masası** 'ndaki **Windows Update** kontrol edin.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcılar için bilgiler**

İşlem, bir sistem kaynağında C Runtime çoklu iş parçacığı kilidine erişmeye çalışırken beklenmeyen bir hata aldı. Bu hata genellikle işlem, çalışma zamanı yığın verilerini yanlışlıkla değiştirirse oluşur. Bununla birlikte, çalışma zamanı kitaplığındaki veya işletim sistemi kodundaki bir iç hata da oluşabilir.

Bu sorunu onarmak için kodunuzda yığın bozulması hatalarını kontrol edin. Daha fazla bilgi ve örnek için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Sonra, uygulama dağıtımınız için en son yeniden dağıtılabilir kullandığınızı kontrol edin. Bilgi için bkz. [Visual C++'te dağıtım ](../../windows/deployment-in-visual-cpp.md).
