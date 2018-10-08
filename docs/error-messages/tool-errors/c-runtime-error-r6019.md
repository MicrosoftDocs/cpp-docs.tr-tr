---
title: C çalışma zamanı hatası R6019 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6019
dev_langs:
- C++
helpviewer_keywords:
- R6019
ms.assetid: 8129923e-7db2-40ee-9602-def9365f8d28
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 13653f54551501d5e35bd1285dc3d3f1a74343f1
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2018
ms.locfileid: "48861609"
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