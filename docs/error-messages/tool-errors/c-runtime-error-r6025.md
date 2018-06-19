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
ms.openlocfilehash: abdbdbf918462dfb83eff07190c32af1f1b3d015
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302032"
---
# <a name="c-runtime-error-r6025"></a>C çalışma zamanı hatası R6025
saf sanal işlev çağrısı  
  
> [!NOTE]
>  Bir uygulama çalıştırırken bu hata iletisi alırsanız, dahili bir sorun olduğundan uygulama kapatıldı. Bu hatanın en yaygın nedeni, uygulama veya bozuk yükleme hatasıdır.  
>   
>  Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:  
>   
>  -   Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasındaki **Denetim Masası** onarın veya program yeniden yükleyin.  
> -   Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.  
> -   Uygulamanın güncelleştirilmiş bir sürümünü denetle. Sorun devam ederse uygulamanın satıcısına başvurun.  
  
 **Programcıları için bilgi**  
  
 Hiçbir nesne, saf sanal işlev çağrısını işlemek için örneği.  
  
 Bu hata, bir Özet temel sınıf bir cast türde bir türetilmiş sınıf tarafından oluşturulur, ancak gerçekte bir temel sınıf işaretçidir işaretçi üzerinden bir sanal işlev çağırarak kaynaklanır. Bu gelen atama ortaya çıkabilir bir **void\***  bir sınıf için bir işaretçi için zaman **void\***  temel sınıfı oluşturma sırasında oluşturuldu.  
  
 Daha fazla bilgi için bkz: [Microsoft Destek](http://go.microsoft.com/fwlink/p/?linkid=75220) Web sitesi.