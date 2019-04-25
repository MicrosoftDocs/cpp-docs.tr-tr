---
title: C Çalışma Zamanı Hatası R6017
ms.date: 11/04/2016
f1_keywords:
- R6017
helpviewer_keywords:
- R6017
ms.assetid: df3ec5f5-6771-4648-ba06-0e26c6a1cc6a
ms.openlocfilehash: 45f3b07f540cb72a955b19420130a5a806b750d7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62299666"
---
# <a name="c-runtime-error-r6017"></a>C Çalışma Zamanı Hatası R6017

Çoklu iş parçacığı beklenmeyen kilitleme hatası

> [!NOTE]
> Bir uygulama çalıştırırken bu hatayla karşılaşırsanız, dahili bir sorun olduğundan uygulaması kapatıldı. Bu hatanın birkaç olası nedeni vardır, ancak genellikle, uygulamanın koddaki bir hata nedeniyle oluşur.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** onarın veya programı yeniden yükleyin.
> - Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcıları için bilgi**

İşlem, C çalışma zamanı çoklu iş parçacığı kilit sistem kaynağına erişmeye çalışılırken beklenmeyen bir hata aldı. Bu hata genellikle işlemi çalışma zamanı yığın verileri yanlışlıkla değiştirirse oluşur. Ancak, bu da çalışma zamanı kitaplığı veya işletim sistemi kod içinde bir iç hata neden olabilir.

Bu sorunu düzeltmek için kodunuzu yığın bozulması hataları kontrol edin. Daha fazla bilgi ve örnekler için bkz. [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ardından, uygulama dağıtımınız için en son yeniden dağıtılabilir dosyaları kullandığınızdan emin olun. Bilgi için [Visual C++ üzerinde dağıtım](../../windows/deployment-in-visual-cpp.md).