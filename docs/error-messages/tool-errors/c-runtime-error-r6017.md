---
title: "C çalışma zamanı hatası R6017 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: R6017
dev_langs: C++
helpviewer_keywords: R6017
ms.assetid: df3ec5f5-6771-4648-ba06-0e26c6a1cc6a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 57345feed2044683a1d5fd2a6ee7d14c412a827d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="c-runtime-error-r6017"></a>C çalışma zamanı hatası R6017
Çoklu iş parçacığı beklenmeyen kilit hatası  
  
> [!NOTE]
>  Bir uygulama çalıştırırken bu hata iletisi alırsanız, dahili bir sorun olduğundan uygulama kapatıldı. Bu hatanın birkaç olası nedeni vardır, ancak genellikle uygulamanın kodu üründe tarafından kaynaklanır.  
>   
>  Bu hatayı düzeltmek için aşağıdaki adımları deneyebilirsiniz:  
>   
>  -   Kullanım **uygulamalar ve Özellikler** veya **programlar ve Özellikler** sayfasındaki **Denetim Masası** onarın veya program yeniden yükleyin.  
> -   Denetleme **Windows Update** içinde **Denetim Masası** yazılım güncelleştirmeleri için.  
> -   Uygulamanın güncelleştirilmiş bir sürümünü denetle. Sorun devam ederse uygulamanın satıcısına başvurun.  
  
 **Programcıları için bilgi**  
  
 İşlem, bir sistem kaynağı C çalışma zamanı çoklu iş parçacığı kilit erişilmeye çalışılırken beklenmeyen bir hata aldı. İşlemin çalışma zamanı yığın veri yanlışlıkla değiştirirse genellikle bu hata oluşur. Ancak, bu da çalışma zamanı kitaplığı veya işletim sistemi koduna bir iç hata neden olabilir.  
  
 Bu sorunu gidermek için kodunuzda yığın bozulması hataları denetleyin. Daha fazla bilgi ve örnekler için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details). Ardından, uygulama dağıtımınız için en son yeniden dağıtılabilir öğeleri kullandığınızdan emin olun. Bilgi için bkz: [Visual C++ üzerinde dağıtım](../../ide/deployment-in-visual-cpp.md).