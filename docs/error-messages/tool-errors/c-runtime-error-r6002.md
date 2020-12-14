---
description: 'Daha fazla bilgi edinin: C çalışma zamanı hatası R6002'
title: C Çalışma Zamanı Hatası R6002
ms.date: 11/04/2016
f1_keywords:
- R6002
helpviewer_keywords:
- R6002
ms.assetid: 8fbbe65a-9c43-459e-8342-e1f6d1cef7d0
ms.openlocfilehash: 9f72b249b491ada4f143848a95ed6161695aa023
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237789"
---
# <a name="c-runtime-error-r6002"></a>C Çalışma Zamanı Hatası R6002

kayan nokta desteği yüklenmedi

Gerekli kayan nokta kitaplığı bağlanmadı.

> [!NOTE]
> Bir uygulamayı çalıştırırken bu hata iletisiyle karşılaşırsanız, bir iç sorun olduğundan uygulama kapatıldı. Bu hatanın birkaç olası nedeni vardır, ancak genellikle uygulamanın kodundaki bir hata nedeniyle veya belirli bilgisayar işlemciniz için oluşturulmamış bir uygulamayı çalıştırmaya çalışırken meydana gelir.
>
> Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:
>
> - Programı onarmak ya da yeniden yüklemek için **Denetim Masası** 'ndaki **uygulamalar ve Özellikler** veya **Programlar ve Özellikler** sayfasını kullanın.
> - Yazılım güncelleştirmeleri için **Denetim Masası** 'ndaki **Windows Update** kontrol edin.
> - Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.

**Programcılar için bilgiler**

Bu hata, kayan nokta kitaplığı bağlı olmadığında uygulamanızda ortaya çıkabilir. Bu nedenlerin birini kontrol edin:

- OR işlevi için bir biçim `printf_s` dizesi `scanf_s` , kayan noktalı bir biçim belirtimi içeriyordu ve program herhangi bir kayan nokta değeri ya da değişken içermiyordu. Bu sorunu giderecek şekilde, kayan nokta biçim belirtimine karşılık gelen bir kayan nokta bağımsız değişkeni kullanın veya programın başka bir yerinde kayan nokta ataması gerçekleştirin. Bu, kayan nokta desteğinin yüklenmesine neden olur.

- Derleyici, kayan nokta desteğini yalnızca gerekli olduğunda yükleyerek programın boyutunu en aza indirir. Derleyici, Biçim dizelerinde kayan nokta işlemlerini veya kayan nokta biçimi belirtimlerini algılayamaz, bu nedenle gerekli kayan nokta yordamlarını yüklemez. Bu sorunu onarmak için, bir kayan nokta biçim belirtimi kullanın ve bir kayan nokta bağımsız değişkeni sağlayın ya da programın başka bir yerinde kayan nokta ataması gerçekleştirin. Bu, kayan nokta desteğinin yüklenmesine neden olur.

- Karma dildeki bir programda bir C Kitaplığı, program bağlandığında bir FORTRAN kitaplığından önce belirtildi. Son olarak C kitaplığını yeniden bağlayın ve belirtin.
