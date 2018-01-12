---
title: "C çalışma zamanı hatası R6033 görülmesine neden olur | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: R6033
dev_langs: C++
helpviewer_keywords: R6033
ms.assetid: f9cffdc9-81bd-4a64-a698-02762cbd82c9
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9f2ef73d3cb82a65c8114d2e7f921b47ffd45d65
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="c-runtime-error-r6033"></a>C çalışma zamanı hatası R6033 görülmesine neden olur
Yerel kod başlatma sırasında bu derlemeye MSIL koddan kullanma girişimi. Bu, uygulamanızın bir hata gösterir. Büyük olasılıkla bir MSIL derlenmiş çağırma sonucu olan (/ clr) yerel bir oluşturucu veya DllMain işlevi.  
  
> [!NOTE]
>  Bir uygulama çalıştırırken bu hata iletisi alırsanız, dahili bir sorun olduğundan uygulama kapatıldı. Bu hata, uygulama bir hata veya eklenti veya kullandığı uzantısı bir hata oluşabilir.  
>   
>  Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:  
>   
>  -   Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasındaki **Denetim Masası** onarın veya program yeniden yükleyin.  
> -   Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasındaki **Denetim Masası** kaldırmayı, onarın veya herhangi bir uzantıları veya eklentileri yeniden yükleyin.  
> -   Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.  
> -   Uygulamanın güncelleştirilmiş bir sürümünü denetle. Sorun devam ederse uygulamanın satıcısına başvurun.  
  
 **Programcıları için bilgi**  
  
 Bu tanılama MSIL yönergeleri yükleyici kilidi sırasında yürütülmekte gösterir. / CLR bayrağını kullanarak yerel C++ derlediğiniz bu durum ortaya çıkabilir. Yalnızca yönetilen kod içeren modülleri/CLR bayrağını kullanın. Daha fazla bilgi için bkz: [karışık derlemeleri başlatma](../../dotnet/initialization-of-mixed-assemblies.md).