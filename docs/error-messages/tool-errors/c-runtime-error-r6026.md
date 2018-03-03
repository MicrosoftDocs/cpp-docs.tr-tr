---
title: "C çalışma zamanı hatası R6026 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- R6026
dev_langs:
- C++
helpviewer_keywords:
- R6026
ms.assetid: 7ea751f8-fc20-46ab-99ef-84c95ca0b6b4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a0baa9806476534bd877f8177d20bbe9da80d3da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="c-runtime-error-r6026"></a>C çalışma zamanı hatası R6026
stdio başlatma için yeterli alan yok  
  
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
  
 C çalışma zamanı standart g/ç desteği başlatmak kullanılabilir yeterli bellek olmadığında bu hata oluşur. Bu hata genellikle uygulama başlatma sırasında oluşur. Uygulamanızı ve sürücüleri ve yüklerken DLL'leri öbek başlatma sırasında bozuk değil olduğunu doğrulayın.