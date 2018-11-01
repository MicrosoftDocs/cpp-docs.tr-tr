---
title: C çalışma zamanı hatası R6032
ms.date: 11/04/2016
f1_keywords:
- R6032
helpviewer_keywords:
- R6032
ms.assetid: 52092a63-cc51-444a-bfc3-fad965a3558e
ms.openlocfilehash: e0ae3acc491658840d74e262f3ab2719e613d60e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50571346"
---
# <a name="c-runtime-error-r6032"></a>C çalışma zamanı hatası R6032

Yerel ayar bilgileri için yeterli alan yok

> [!NOTE]
> Bir uygulama çalıştırırken bu hatayla karşılaşırsanız, dahili bellek sorunu olduğundan uygulaması kapatıldı. Bu hatanın birkaç olası nedeni vardır, ancak son derece düşük bellek durumu veya bir programın hata genellikle neden olur.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Çalışan diğer uygulamaları kapatın veya belleği boşaltmak için bilgisayarınızı yeniden başlatın.
> - Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** onarın veya programı yeniden yükleyin.
> - Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcıları için bilgi**

Yerel ayar duyarlı işlevleri çağrıları işleyebilmesi çalışma zamanı, her iş parçacığı yerel ayarı hakkında bilgi tutar. Bu bilgiler için bellek ayırma başarısız olursa, çalışma zamanı temel kendi tesislerinde çok fazla ona bağımlı olduğundan işleme devam edilemiyor.