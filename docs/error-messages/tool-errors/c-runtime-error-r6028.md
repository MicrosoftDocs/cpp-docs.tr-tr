---
title: "C çalışma zamanı hatası R6028 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- R6028
dev_langs:
- C++
helpviewer_keywords:
- R6028
ms.assetid: 81e99079-4388-4244-a4f7-4641c508871c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7d1d7260cd2416e9d157931b037cfd7fbe4c0081
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="c-runtime-error-r6028"></a>C çalışma zamanı hatası R6028
yığın başlatılamıyor  
  
> [!NOTE]
>  Bir uygulama çalıştırırken bu hata iletisi alırsanız, bir iç bellek sorunu olduğundan uygulama kapatıldı. Bu hatanın birçok olası nedeni vardır, ancak bir son derece düşük bellek durumu program hatada veya bozuk donanım sürücüleri tarafından genellikle neden olur.  
>   
>  Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:  
>   
>  -   Çalışan diğer uygulamaları kapatın veya belleği boşaltmak için bilgisayarınızı yeniden başlatın.  
> -   Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasındaki **Denetim Masası** onarın veya program yeniden yükleyin.  
> -   Uygulama başka bir uygulama veya sürücü yeni yüklemeden önce çalışan kullanırsanız **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasındaki **Denetim Masası** kaldırmak için Yeni uygulama veya sürücü, uygulamanızı yeniden deneyin.  
> -   Donanım satıcınızın Web sitesini denetleyin veya **Windows Update** içinde **Denetim Masası** yazılım ve sürücü güncelleştirmeleri.  
> -   Uygulamanın güncelleştirilmiş bir sürümünü denetle. Sorun devam ederse uygulamanın satıcısına başvurun.  
  
 **Programcıları için bilgi**  
  
 Bu hata, işletim sistemi uygulama için bellek havuzunu oluşturamadığında meydana gelir. Özellikle, C çalışma zamanı (CRT) Win32 işlevini çağırdı `HeapCreate`, hata olduğunu gösteren NULL döndürdü.  
  
 Uygulama başlatma sırasında bu hata ortaya çıkarsa, sistem kusurlu sürücülerin yüklü olması sebebiyle yığın isteklerini karşılayamayabilir. Windows Update'e veya güncelleştirilmiş sürücüler için donanım satıcınızın web sitesine bakın.