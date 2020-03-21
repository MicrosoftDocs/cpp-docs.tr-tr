---
title: C Çalışma Zamanı Hatası R6025
ms.date: 11/04/2016
f1_keywords:
- R6025
helpviewer_keywords:
- R6025
ms.assetid: afa06d98-9c36-445b-b3e7-b6409bc8e779
ms.openlocfilehash: d5edb08278b7b6b9b3eb62e92fc04410f96a8f09
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80075122"
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

Bu hata, türetilmiş sınıfın türüne atama tarafından oluşturulan bir işaretçi aracılığıyla soyut bir temel sınıfta bir sanal işlevin çağrılmasından kaynaklanır, ancak aslında temel sınıfa bir işaretçidir. Bu durum, bir **void** <strong>\*</strong> , temel sınıfın oluşturulması sırasında **void** <strong>\*</strong> oluşturulduğunda bir sınıfa işaretçiye atama yapıldığında meydana gelebilir.
