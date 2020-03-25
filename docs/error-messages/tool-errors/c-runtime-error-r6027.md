---
title: C Çalışma Zamanı Hatası R6027
ms.date: 11/04/2016
f1_keywords:
- R6027
helpviewer_keywords:
- R6027
ms.assetid: c06a62b3-08d9-4bf5-bcad-8340ec552f69
ms.openlocfilehash: 8c2aab7b090dbfa4553b8d1622f13aef13f58aa3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80197177"
---
# <a name="c-runtime-error-r6027"></a>C Çalışma Zamanı Hatası R6027

lowio başlatması için yeterli alan yok

> [!NOTE]
> Bir uygulamayı çalıştırırken bu hata iletisiyle karşılaşırsanız, bir iç bellek sorunu olduğundan uygulama kapatıldı. Bu hatanın birkaç olası nedeni vardır ancak genellikle son derece düşük bellek koşulunun meydana gelir. Ayrıca, uygulamadaki bir hata, kullandığı görsel C++ kitaplıkların bozulması veya bir sürücü tarafından da oluşabilir.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Çalışan diğer uygulamaları kapatın veya belleği boşaltmak için bilgisayarınızı yeniden başlatın.
> - Programı onarmak ya da yeniden yüklemek için **Denetim Masası** 'ndaki **uygulamalar ve Özellikler** veya **Programlar ve Özellikler** sayfasını kullanın.
> - Uygulama, başka bir uygulama veya sürücünün son yüklemesi öncesinde çalışıyorsa, yeni uygulamayı veya sürücüyü kaldırmak için **Denetim Masası** 'ndaki **uygulamalar ve Özellikler** veya **Programlar ve Özellikler** sayfasını kullanın ve uygulamanızı yeniden deneyin.
> - **Denetim Masası** 'ndaki C++ **uygulamalar ve Özellikler** veya **Programlar ve Özellikler** sayfasını kullanarak Microsoft Visual Redistributable 'ın tüm kopyalarını onarın veya yeniden yükleyin.
> - Yazılım güncelleştirmeleri için **Denetim Masası** 'ndaki **Windows Update** kontrol edin.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcılar için bilgiler**

Bu hata, C çalışma zamanında alt düzey g/ç desteğini başlatmak için yeterli boş bellek olmadığında oluşur. Bu hata genellikle uygulama başlangıcında oluşur. Uygulamanızın ve yüklediği sürücü ve DLL 'lerin başlangıçta yığını bozmadığını doğrulayın.
