---
title: "C çalışma zamanı hatası R6008 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- R6008
dev_langs:
- C++
helpviewer_keywords:
- R6008
ms.assetid: f0f304fc-709a-4843-bc7e-bad1ae0d1649
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 86b64f97768359b95d2c5e2003cfb5b95a2aac71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="c-runtime-error-r6008"></a>C çalışma zamanı hatası R6008
bağımsız değişkenler için yeterli alan yok  
  
> [!NOTE]
>  Bir uygulama çalıştırırken bu hata iletisi alırsanız, bir iç bellek sorunu olduğundan uygulama kapatıldı. Bu hatanın birkaç olası nedeni vardır, ancak genellikle bir son derece düşük bellek durumu, ortam değişkenleri ya da hata programı tarafından gerçekleştirilecek çok fazla bellek tarafından kaynaklanır.  
>   
>  Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:  
>   
>  -   Çalışan diğer uygulamaları kapatın veya belleği boşaltmak için bilgisayarınızı yeniden başlatın.  
> -   Uygulamaya sayısını ve komut satırı bağımsız değişkenleri boyutunu azaltın.  
> -   Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasındaki **Denetim Masası** onarın veya program yeniden yükleyin.  
> -   Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.  
> -   Uygulamanın güncelleştirilmiş bir sürümünü denetle. Sorun devam ederse uygulamanın satıcısına başvurun.  
  
 **Programcıları için bilgi**  
  
 Programı yüklemek için yeterli bellek ancak oluşturmak için yeterli bellek yoktu **argv** dizi. Bu, son derece düşük bellek koşulları veya olağan dışı derecede büyük komut satırları veya ortam değişkeni kullanımı kaynaklanabilir. Aşağıdaki çözümlerden birini göz önünde bulundurun:  
  
-   Programa kullanılabilir bellek miktarını artırın.  
  
-   Sayısını ve komut satırı bağımsız değişkenleri boyutunu azaltın.  
  
-   Gereksiz değişkenleri kaldırarak ortam boyutunu azaltın.