---
title: "C çalışma zamanı hatası R6019 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: R6019
dev_langs: C++
helpviewer_keywords: R6019
ms.assetid: 8129923e-7db2-40ee-9602-def9365f8d28
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 32b2b2f29b1b426ab67f089ae7a54a9730f16535
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="c-runtime-error-r6019"></a>C çalışma zamanı hatası R6019
Konsol cihaz açılamıyor  
  
> [!NOTE]
>  Bir uygulama çalıştırırken bu hata iletisiyle karşılaşırsanız, uygulama konsol erişme girişiminde bulunuldu, ancak yeterli izne sahip oldu çünkü kapatıldı. Bu hatanın birkaç olası nedeni vardır, ancak programı yönetici olarak çalıştırmanız gerekir veya programa bir hata olduğu için genellikle değil.  
>   
>  Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:  
>   
>  -   Programını Yönetici olarak çalıştırın.  
> -   Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasındaki **Denetim Masası** onarın veya program yeniden yükleyin.  
> -   Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.  
> -   Uygulamanın güncelleştirilmiş bir sürümünü denetle. Sorun devam ederse uygulamanın satıcısına başvurun.  
  
 **Programcıları için bilgi**  
  
 Bu hata, uygulama bir konsol işlevi çağrıldı, ancak işletim sistemi konsolu erişim izni yok olduğundan oluşur. Dışında hata ayıklama modunda konsol işlevleri genellikle Windows mağazası uygulamalarında izin verilmez. Uygulamanızı çalıştırmak için yönetici ayrıcalıkları gerektiriyorsa, bu yönetici olarak çalıştırmak için varsayılan olarak yüklendiğinden emin olun.