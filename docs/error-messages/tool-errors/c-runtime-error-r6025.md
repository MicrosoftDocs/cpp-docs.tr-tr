---
description: 'Daha fazla bilgi edinin: C çalışma zamanı hatası R6025'
title: C Çalışma Zamanı Hatası R6025
ms.date: 11/04/2016
f1_keywords:
- R6025
helpviewer_keywords:
- R6025
ms.assetid: afa06d98-9c36-445b-b3e7-b6409bc8e779
ms.openlocfilehash: 7bf3213d81e144f14f6eeb25f108f497267ec4d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237575"
---
# <a name="c-runtime-error-r6025"></a>C Çalışma Zamanı Hatası R6025

saf sanal işlev çağrısı

> [!NOTE]
> Bir uygulamayı çalıştırırken bu hata iletisiyle karşılaşırsanız, bir iç sorun olduğundan uygulama kapatıldı. Bu hatanın en yaygın nedeni, uygulamadaki bir hata veya bozuk bir yüklemedir.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Programı onarmak ya da yeniden yüklemek için **Denetim Masası** 'ndaki **uygulamalar ve Özellikler** veya **Programlar ve Özellikler** sayfasını kullanın.
> - Yazılım güncelleştirmeleri için **Denetim Masası** 'ndaki **Windows Update** kontrol edin.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcılar için bilgiler**

Saf sanal işlev çağrısını işlemek için hiçbir nesne örneği oluşturulmadı.

Bu hata, türetilmiş sınıfın türüne atama tarafından oluşturulan bir işaretçi aracılığıyla soyut bir temel sınıfta bir sanal işlevin çağrılmasından kaynaklanır, ancak aslında temel sınıfa bir işaretçidir. Bu durum **`void`** <strong>\*</strong> , **`void`** <strong>\*</strong> temel sınıfın oluşturulması sırasında oluşturulduğu sırada bir sınıfa işaretçiye atama yapılırken meydana gelebilir.
