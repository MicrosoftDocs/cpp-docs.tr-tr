---
title: C çalışma zamanı hatası R6018 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6018
dev_langs:
- C++
helpviewer_keywords:
- R6018
ms.assetid: f6dd40d1-a119-4d8b-b39e-97350ea23349
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4946e3a8341963ee1a1ca2c3ad65d64cfbad8080
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302834"
---
# <a name="c-runtime-error-r6018"></a>C çalışma zamanı hatası R6018
Beklenmeyen yığın hatası  
  
> [!NOTE]
>  Bir uygulama çalıştırırken bu hata iletisi alırsanız, dahili bir sorun olduğundan uygulama kapatıldı. Bu hatanın birkaç olası nedeni vardır, ancak genellikle uygulamanın kodu üründe tarafından kaynaklanır.  
>   
>  Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:  
>   
>  -   Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasındaki **Denetim Masası** onarın veya program yeniden yükleyin.  
> -   Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.  
> -   Uygulamanın güncelleştirilmiş bir sürümünü denetle. Sorun devam ederse uygulamanın satıcısına başvurun.  
  
 **Programcıları için bilgi**  
  
 Program, bir bellek yönetimi işlemi gerçekleştirilirken beklenmeyen bir hatayla karşılaştı.  
  
 Programın çalışma zamanı yığın veri yanlışlıkla değiştirirse genellikle bu hata oluşur. Ancak, bu da işletim sistemi kod ve Çalışma Zamanı Modülü bir iç hata neden olabilir.  
  
 Bu sorunu gidermek için kodunuzda yığın bozulması hataları denetleyin. Daha fazla bilgi ve örnekler için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ardından, uygulama dağıtımınız için en son yeniden dağıtılabilir öğeleri kullandığınızdan emin olun. Bilgi için bkz: [Visual C++ üzerinde dağıtım](../../ide/deployment-in-visual-cpp.md).