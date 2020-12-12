---
description: 'Daha fazla bilgi edinin: C çalışma zamanı hatası R6026'
title: C Çalışma Zamanı Hatası R6026
ms.date: 11/04/2016
f1_keywords:
- R6026
helpviewer_keywords:
- R6026
ms.assetid: 7ea751f8-fc20-46ab-99ef-84c95ca0b6b4
ms.openlocfilehash: f592cfff4dab72cbaac3d6470fdb2423302a08c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237536"
---
# <a name="c-runtime-error-r6026"></a>C Çalışma Zamanı Hatası R6026

stdio başlatması için yeterli alan yok

> [!NOTE]
> Bir uygulamayı çalıştırırken bu hata iletisiyle karşılaşırsanız, bir iç bellek sorunu olduğundan uygulama kapatıldı. Bu hatanın birkaç olası nedeni vardır ancak genellikle son derece düşük bellek koşulunun meydana gelir. Ayrıca, uygulamadaki bir hata, kullandığı Visual C++ kitaplıklarının bozulması veya bir sürücü tarafından da oluşabilir.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Çalışan diğer uygulamaları kapatın veya belleği boşaltmak için bilgisayarınızı yeniden başlatın.
> - Programı onarmak ya da yeniden yüklemek için **Denetim Masası** 'ndaki **uygulamalar ve Özellikler** veya **Programlar ve Özellikler** sayfasını kullanın.
> - Uygulama, başka bir uygulama veya sürücünün son yüklemesi öncesinde çalışıyorsa, yeni uygulamayı veya sürücüyü kaldırmak için **Denetim Masası** 'ndaki **uygulamalar ve Özellikler** veya **Programlar ve Özellikler** sayfasını kullanın ve uygulamanızı yeniden deneyin.
> - Yeniden dağıtılabilir Microsoft Visual C++ tüm kopyalarını onarmak ya da yeniden yüklemek için **Denetim Masası** 'ndaki **uygulamalar ve Özellikler** veya **Programlar ve Özellikler** sayfasını kullanın.
> - Yazılım güncelleştirmeleri için **Denetim Masası** 'ndaki **Windows Update** kontrol edin.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcılar için bilgiler**

Bu hata, C çalışma zamanında standart g/ç desteğini başlatmak için yeterli boş bellek olmadığında oluşur. Bu hata genellikle uygulama başlangıcında oluşur. Uygulamanızın ve yüklediği sürücü ve DLL 'lerin başlangıçta yığını bozmadığını doğrulayın.
