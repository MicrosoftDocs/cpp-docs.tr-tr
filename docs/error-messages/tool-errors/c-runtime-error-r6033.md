---
title: C çalışma zamanı hatası R6033 görülmesine neden olur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6033
dev_langs:
- C++
helpviewer_keywords:
- R6033
ms.assetid: f9cffdc9-81bd-4a64-a698-02762cbd82c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ed66dec4f4eb17378c9901439be2ad1449597a93
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300000"
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