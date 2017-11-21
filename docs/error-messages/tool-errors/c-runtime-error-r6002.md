---
title: "C çalışma zamanı hatası R6002 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: R6002
dev_langs: C++
helpviewer_keywords: R6002
ms.assetid: 8fbbe65a-9c43-459e-8342-e1f6d1cef7d0
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8b8bd95ed0b088fcfed61b7c0ff1db6343c69500
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="c-runtime-error-r6002"></a>C çalışma zamanı hatası R6002
kayan nokta desteği yüklenmedi  
  
 Gerekli kayan nokta kitaplığı bağlı değil.  
  
> [!NOTE]
>  Bir uygulama çalıştırırken bu hata iletisi alırsanız, dahili bir sorun olduğundan uygulama kapatıldı. Bu hatanın birkaç olası nedeni vardır, ancak bir üründe uygulamanın koduna veya belirli bir bilgisayar işlemcinizin oluşturulmadı bir uygulamayı çalıştırma denemesi genellikle neden olur.  
>   
>  Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:  
>   
>  -   Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasındaki **Denetim Masası** onarın veya program yeniden yükleyin.  
> -   Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.  
> -   Uygulamanın güncelleştirilmiş bir sürümünü denetle. Sorun devam ederse uygulamanın satıcısına başvurun.  
  
 **Programcıları için bilgi**  
  
 Kayan nokta kitaplığı bağlanmadı bu hata, uygulamanızda ortaya çıkabilir. Bu nedenlerden birinden dolayı denetleyin:  
  
-   Bir biçim dizesi için bir `printf_s` veya `scanf_s` işlevi bir kayan nokta biçim belirtimi içeriyordu ve program herhangi bir kayan nokta değerleri veya değişkenleri içermiyordu. Bu sorunu gidermek için kayan nokta biçimi belirtimlerine uygun olmalıdır için kayan nokta bağımsız değişkenini kullanın veya bir kayan nokta ataması başka bir programda gerçekleştirin. Bu, yüklenecek kayan nokta desteği neden olur.  
  
-   Derleyici kayan nokta desteği yalnızca gerekli olduğunda yükleyerek bir programın boyutu en aza indirir. Gerekli kayan nokta yordamları yüklemez şekilde derleyici biçim dizeleri kayan nokta işlemleri veya kayan nokta biçim belirtimleri algılayamaz. Bu sorunu gidermek için bir kayan nokta biçim belirtimi kullanın ve kayan noktalı bir bağımsız değişken sağlayın veya bir kayan nokta ataması başka bir programda gerçekleştirin. Bu, yüklenecek kayan nokta desteği neden olur.  
  
-   Karışık dil programında program bağlandığında bir C Kitaplığı FORTRAN kitaplığı önce belirtildi. Yeniden bağlayın ve en son C Kitaplığı belirtin.