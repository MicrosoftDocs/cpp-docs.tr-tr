---
title: C Çalışma Zamanı Hatası R6033
ms.date: 11/04/2016
f1_keywords:
- R6033
helpviewer_keywords:
- R6033
ms.assetid: f9cffdc9-81bd-4a64-a698-02762cbd82c9
ms.openlocfilehash: 39d8a20dacb0cdeb2a767529e9716bd476f406dc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400012"
---
# <a name="c-runtime-error-r6033"></a>C Çalışma Zamanı Hatası R6033

MSIL kodunu yerel kod başlatma sırasında bu derlemedeki kullanmayı dener. Bu, uygulamanızda bir hata gösterir. Bu büyük olasılıkla bir MSIL olarak derlenmiş çağırma sonucu olan (/ clr) yerel bir oluşturucu veya DllMain işlevi.

> [!NOTE]
> Bir uygulama çalıştırırken bu hatayla karşılaşırsanız, dahili bir sorun olduğundan uygulaması kapatıldı. Bu hata, uygulamada bir hata veya bir hatayı bir eklenti veya kullandığı uzantısında neden olabilir.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** onarın veya programı yeniden yükleyin.
> - Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** kaldırmak onarın veya tüm eklentileri veya uzantıları yeniden yükleyin.
> - Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcıları için bilgi**

Bu tanılama MSIL yönergeleri yükleyici kilidi sırasında yürütülen gösterir. Yerel C++/CLR bayrağı kullanılarak derlenmiş ise bu durum oluşabilir. Yalnızca yönetilen kod içeren modülleri/CLR bayrağı kullanın. Daha fazla bilgi için [karışık derlemeleri başlatma](../../dotnet/initialization-of-mixed-assemblies.md).