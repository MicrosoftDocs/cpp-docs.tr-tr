---
title: C Çalışma Zamanı Hatası R6031
ms.date: 11/04/2016
f1_keywords:
- R6031
helpviewer_keywords:
- R6031
ms.assetid: 805d4cd1-cb2f-43fe-87e6-e7bd5b7329c5
ms.openlocfilehash: 4b75b0855f0f0d60304cfe8b7a00b4ce27a8daab
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80197112"
---
# <a name="c-runtime-error-r6031"></a>C Çalışma Zamanı Hatası R6031

CRT 'ı birden çok kez başlatmayı deneyin. Bu, uygulamanızdaki bir hatayı gösterir.

> [!NOTE]
> Bir uygulamayı çalıştırırken bu hata iletisiyle karşılaşırsanız, bir iç sorun olduğundan uygulama kapatıldı. Bunun nedeni uygulamada hata ya da uygulamanın kullandığı bir eklenti veya uzantıdaki bir hata olabilir.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Programı onarmak ya da yeniden yüklemek için **Denetim Masası** 'ndaki **uygulamalar ve Özellikler** veya **Programlar ve Özellikler** sayfasını kullanın.
> - Uygulama tarafından kullanılan eklenti veya uzantı programlarını kaldırmak, onarmak ya da yeniden yüklemek için **Denetim Masası** 'ndaki **uygulamalar ve Özellikler** veya **Programlar ve Özellikler** sayfasını kullanın.
> - Yazılım güncelleştirmeleri için **Denetim Masası** 'ndaki **Windows Update** kontrol edin.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcılar için bilgiler**

Bu tanılama, yükleyici kilidi sırasında MSIL yönergelerinin yürütüldüğü anlamına gelir. Daha fazla bilgi için bkz. [karışık derlemeleri başlatma](../../dotnet/initialization-of-mixed-assemblies.md).
