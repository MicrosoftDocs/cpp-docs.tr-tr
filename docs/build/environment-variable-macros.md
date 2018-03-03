---
title: "Ortam değişkeni makroları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, environment variable macros
- environment variables, macros in NMAKE
- macros, environment-variable
ms.assetid: f8e96635-0906-47b0-9f56-12a6fdf5e347
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 69fae15b7a12d990d2fb2c8e457bfdc0407f7702
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="environment-variable-macros"></a>Ortam Değişkeni Makroları
NMAKE makrosu tanımları oturum başlamadan önce mevcut ortam değişkenleri için devralır. Bir değişken işletim sistemi ortamında ayarlarsanız, NMAKE makrosu kullanılabilir. Devralınan adları büyük harfe dönüştürülür. Devralma ön işleme önce gerçekleşir. Derleme görevleri dosyası aynı adla makroların geçersiz kılmak için ortam değişkenleri devralınan makroları neden /E seçeneğini kullanın.  
  
 Ortam değişkeni makroları oturumda tanımlanabilir ve bu karşılık gelen ortam değişkenini değiştirir. Ortam değişkenleri SET komutu ile de değiştirebilirsiniz. Bir ortam değişkeni bir oturumda değiştirmek için SET komutunu kullanarak karşılık gelen makrosu ancak değiştirmez.  
  
 Örneğin:  
  
```  
PATH=$(PATH);\nonesuch  
  
all:  
    echo %PATH%  
```  
  
 Bu örnekte, değiştirme `PATH` karşılık gelen ortam değişkenini değiştirir `PATH`; bu ekler `\nonesuch` yolunuz için.  
  
 Bir ortam değişkeni bir makefile sözdizimsel olarak doğru olacak bir dize olarak tanımlanmışsa, hiçbir makrosu oluşturulur ve herhangi bir uyarı üretilir. Bir değişkenin değeri dolar işareti ($) içeriyorsa, NMAKE makrosu çağırma başlayan olarak yorumlar. Makro kullanarak beklenmeyen davranışlara neden olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel NMAKE Makroları](../build/special-nmake-macros.md)