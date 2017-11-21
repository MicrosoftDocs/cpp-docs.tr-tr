---
title: "C çalışma zamanı hatası R6025 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: R6025
dev_langs: C++
helpviewer_keywords: R6025
ms.assetid: afa06d98-9c36-445b-b3e7-b6409bc8e779
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 06fd7aa6458a3c7e89d80146ec20a0e3f7587b4b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
  
 Daha fazla bilgi için bkz: [Microsoft Destek](http://go.microsoft.com/fwlink/?LinkId=75220) Web sitesi.