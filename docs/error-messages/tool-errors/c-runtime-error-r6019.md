---
title: C çalışma zamanı hatası R6019
ms.date: 11/04/2016
f1_keywords:
- R6019
helpviewer_keywords:
- R6019
ms.assetid: 8129923e-7db2-40ee-9602-def9365f8d28
ms.openlocfilehash: 93d340b2a12a00420a9003429251387b2f04ad37
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548076"
---
# <a name="c-runtime-error-r6019"></a>C çalışma zamanı hatası R6019

Konsol cihaz açılamıyor

> [!NOTE]
> Bir uygulama çalıştırırken bu hatayla karşılaşırsanız, uygulamayı Konsolu'na erişmeye çalıştı, ancak yeterli izne sahip oldu çünkü kapatıldı. Bu hatanın birkaç olası nedeni vardır, ancak bu programı yönetici olarak çalıştırmanız gerekir veya programında bir hata olduğu için genelde olduğu.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Programını Yönetici olarak çalıştırın.
> - Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** onarın veya programı yeniden yükleyin.
> - Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcıları için bilgi**

Uygulamayı bir konsol işlev çağrıldı, ancak işletim sistemi konsol erişimi veremez bu hata oluşur. Dışında hata ayıklama modunda Konsolu işlevleri genellikle Microsoft Store uygulamalarında izin verilmez. Uygulamanızı çalıştırmak için yönetici ayrıcalıkları gerektiriyorsa, varsayılan olarak yönetici olarak çalıştırmak için yüklü emin olun.