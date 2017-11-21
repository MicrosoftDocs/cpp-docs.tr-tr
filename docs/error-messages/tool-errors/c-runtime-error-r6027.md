---
title: "C çalışma zamanı hatası R6027 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: R6027
dev_langs: C++
helpviewer_keywords: R6027
ms.assetid: c06a62b3-08d9-4bf5-bcad-8340ec552f69
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4f8110dc8d3ee580c8ba94336bd4818dd928310e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="c-runtime-error-r6027"></a>C çalışma zamanı hatası R6027
lowio başlatma için yeterli alan yok  
  
> [!NOTE]
>  Bir uygulama çalıştırırken bu hata iletisi alırsanız, bir iç bellek sorunu olduğundan uygulama kapatıldı. Bu hatanın birkaç olası nedeni vardır, ancak genellikle son derece düşük bellek koşul tarafından kaynaklanır. Ayrıca uygulama bir hata, kullandığı Visual C++ kitaplıkları'nın Bozulması veya bir sürücüsü tarafından kaynaklanabilir.  
>   
>  Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:  
>   
>  -   Çalışan diğer uygulamaları kapatın veya belleği boşaltmak için bilgisayarınızı yeniden başlatın.  
> -   Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasındaki **Denetim Masası** onarın veya program yeniden yükleyin.  
> -   Uygulama başka bir uygulama veya sürücü yeni yüklemeden önce çalışan kullanırsanız **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasındaki **Denetim Masası** kaldırmak için Yeni uygulama veya sürücü, uygulamanızı yeniden deneyin.  
> -   Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasındaki **Denetim Masası** onarın veya Microsoft Visual C++ yeniden dağıtılabilir tüm kopyalarını yeniden yükleyin.  
> -   Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.  
> -   Uygulamanın güncelleştirilmiş bir sürümünü denetle. Sorun devam ederse uygulamanın satıcısına başvurun.  
  
 **Programcıları için bilgi**  
  
 C çalışma zamanı düşük düzey g/ç desteği başlatmak yeterli bellek olmadığında bu hata oluşur. Bu hata genellikle uygulama başlatma sırasında oluşur. Uygulamanızı ve sürücüleri ve yüklerken DLL'leri öbek başlatma sırasında bozuk değil olduğunu doğrulayın.