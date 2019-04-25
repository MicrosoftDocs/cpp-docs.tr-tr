---
title: C Çalışma Zamanı Hatası R6031
ms.date: 11/04/2016
f1_keywords:
- R6031
helpviewer_keywords:
- R6031
ms.assetid: 805d4cd1-cb2f-43fe-87e6-e7bd5b7329c5
ms.openlocfilehash: 6ef3f5fa7d063fdc300e6ac28ca519992525851c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62242688"
---
# <a name="c-runtime-error-r6031"></a>C Çalışma Zamanı Hatası R6031

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