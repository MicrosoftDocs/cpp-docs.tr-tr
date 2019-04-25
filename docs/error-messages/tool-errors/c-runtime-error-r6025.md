---
title: C Çalışma Zamanı Hatası R6025
ms.date: 11/04/2016
f1_keywords:
- R6025
helpviewer_keywords:
- R6025
ms.assetid: afa06d98-9c36-445b-b3e7-b6409bc8e779
ms.openlocfilehash: 461bfb2aa46053ec56fff67de70038b1fcd97389
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62214174"
---
# <a name="c-runtime-error-r6025"></a>C Çalışma Zamanı Hatası R6025

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

