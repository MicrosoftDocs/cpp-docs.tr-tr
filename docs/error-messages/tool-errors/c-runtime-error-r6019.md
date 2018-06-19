---
title: C çalışma zamanı hatası R6019 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6019
dev_langs:
- C++
helpviewer_keywords:
- R6019
ms.assetid: 8129923e-7db2-40ee-9602-def9365f8d28
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 95950254d4a0611d9690b8636eb50f2fc1f0f264
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33314235"
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
  
 Bu hata, uygulama bir konsol işlevi çağrıldı, ancak işletim sistemi konsolu erişim izni yok olduğundan oluşur. Dışında hata ayıklama modunda konsol işlevleri genellikle Microsoft Store uygulamaları izin verilmez. Uygulamanızı çalıştırmak için yönetici ayrıcalıkları gerektiriyorsa, bu yönetici olarak çalıştırmak için varsayılan olarak yüklendiğinden emin olun.