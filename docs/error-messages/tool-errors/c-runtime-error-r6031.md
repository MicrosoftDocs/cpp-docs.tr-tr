---
title: C çalışma zamanı hatası R6031
ms.date: 11/04/2016
f1_keywords:
- R6031
helpviewer_keywords:
- R6031
ms.assetid: 805d4cd1-cb2f-43fe-87e6-e7bd5b7329c5
ms.openlocfilehash: 6ef3f5fa7d063fdc300e6ac28ca519992525851c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50564235"
---
# <a name="c-runtime-error-r6031"></a>C çalışma zamanı hatası R6031

CRT birden fazla kez başlatmaya girişimi. Bu, uygulamanızda bir hata gösterir.

> [!NOTE]
> Bir uygulama çalıştırırken bu hatayla karşılaşırsanız, dahili bir sorun olduğundan uygulaması kapatıldı. Bu hata uygulamada veya bir hatayı bir eklenti veya uygulamanın kullandığı uzantısı tarafından kaynaklanabilir.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** onarın veya programı yeniden yükleyin.
> - Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** kaldırmak için onarın veya uygulama tarafından kullanılan tüm eklenti veya uzantı programları yeniden yükleyin.
> - Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcıları için bilgi**

Bu tanılama MSIL yönergeleri yükleyici kilidi sırasında yürütülen gösterir. Daha fazla bilgi için [karışık derlemeleri başlatma](../../dotnet/initialization-of-mixed-assemblies.md).