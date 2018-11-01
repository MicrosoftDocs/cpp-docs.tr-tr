---
title: C çalışma zamanı hatası R6025
ms.date: 11/04/2016
f1_keywords:
- R6025
helpviewer_keywords:
- R6025
ms.assetid: afa06d98-9c36-445b-b3e7-b6409bc8e779
ms.openlocfilehash: 461bfb2aa46053ec56fff67de70038b1fcd97389
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50639575"
---
# <a name="c-runtime-error-r6025"></a>C çalışma zamanı hatası R6025

saf sanal işlev çağrısı

> [!NOTE]
> Bir uygulama çalıştırırken bu hatayla karşılaşırsanız, dahili bir sorun olduğundan uygulaması kapatıldı. Bu hatanın en yaygın nedeni, uygulama ya da bozuk yükleme için kullanılan bir hatadır.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** onarın veya programı yeniden yükleyin.
> - Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcıları için bilgi**

Hiçbir nesne, saf sanal işlev çağrısındaki işleneceğini örneği.

Türetilmiş sınıf türü için bir yayın tarafından oluşturulur ancak gerçekten bir işaretçi temel sınıfın bir işaretçisi aracılığıyla soyut bir temel sınıfta sanal bir işlev çağırarak bu hataya neden olur. Gelen atama olduğunda ortaya çıkabilir bir **void** <strong>\*</strong> bir sınıf işaretçisi olduğunda **void** <strong>\*</strong> oluştu temel sınıf oluşumu sırasında oluşturuldu.

