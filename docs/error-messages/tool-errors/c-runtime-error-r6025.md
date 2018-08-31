---
title: C çalışma zamanı hatası R6025 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6025
dev_langs:
- C++
helpviewer_keywords:
- R6025
ms.assetid: afa06d98-9c36-445b-b3e7-b6409bc8e779
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b774c5f99387ca4403941d1461593bef8801e5de
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43220638"
---
# <a name="c-runtime-error-r6025"></a>C çalışma zamanı hatası R6025
saf sanal işlev çağrısı  
  
> [!NOTE]
>  Bir uygulama çalıştırırken bu hatayla karşılaşırsanız, dahili bir sorun olduğundan uygulaması kapatıldı. Bu hatanın en yaygın nedeni, uygulama ya da bozuk yükleme için kullanılan bir hatadır.  
>   
>  Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:  
>   
>  -   Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasını **Denetim Masası** onarın veya programı yeniden yükleyin.  
> -   Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.  
> -   Uygulamanın güncelleştirilmiş bir sürümünü denetleyin. Sorun devam ederse uygulama satıcısına başvurun.  
  
 **Programcıları için bilgi**  
  
 Hiçbir nesne, saf sanal işlev çağrısındaki işleneceğini örneği.  
  
 Türetilmiş sınıf türü için bir yayın tarafından oluşturulur ancak gerçekten bir işaretçi temel sınıfın bir işaretçisi aracılığıyla soyut bir temel sınıfta sanal bir işlev çağırarak bu hataya neden olur. Gelen atama olduğunda ortaya çıkabilir bir **void** <strong>\*</strong> bir sınıf işaretçisi olduğunda **void** <strong>\*</strong> oluştu temel sınıf oluşumu sırasında oluşturuldu.  
  
 Daha fazla bilgi için [Microsoft Destek](http://go.microsoft.com/fwlink/p/?linkid=75220) Web sitesi.