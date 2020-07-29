---
title: C Çalışma Zamanı Hatası R6025
ms.date: 11/04/2016
f1_keywords:
- R6025
helpviewer_keywords:
- R6025
ms.assetid: afa06d98-9c36-445b-b3e7-b6409bc8e779
ms.openlocfilehash: 6e184ba24ad535697a727276a980fd082625e082
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218058"
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
