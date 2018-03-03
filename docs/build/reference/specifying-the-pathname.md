---
title: "Yol adını belirtme | Microsoft Docs"
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
- names [C++], compiler output files
- cl.exe compiler, output files
- output files, specifying pathnames
ms.assetid: 7a6595ce-3383-44ae-957a-466bfa29c343
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2412ab15317604e1d6cccc5535226d429d8ba6b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="specifying-the-pathname"></a>Yol Adını Belirtme
Çıktı dosyası seçeneğin kabul eden bir *pathname* bir konum ve çıktı dosyası için bir ad belirtebilirsiniz bağımsız değişkeni. Bağımsız değişkeni bir sürücü adı, dizin ve dosya adı içerebilir. Seçenek ve bağımsız değişken arasında boşluk bulunmamalıdır.  
  
 Varsa *pathname* dosya adı içeren bir uzantısı olmadan Derleyici çıktısı varsayılan uzantısı sağlar. Varsa *pathname* bir dizin ancak hiçbir dosya adı içeren derleyici belirtilen dizindeki bir varsayılan adıyla bir dosya oluşturur. Varsayılan adı kaynak dosyasını ve çıktı dosyası türüne göre varsayılan uzantısı temel adını temel alır. Devre dışı bırakırsanız *pathname* tamamen derleyici varsayılan bir dizin içinde varsayılan adıyla bir dosya oluşturur.  
  
 Alternatif olarak, *pathname* bağımsız değişkeni, bir dosya adı yerine bir aygıt adı (AUX, CON, PRN veya NUL) olabilir. Seçeneğini ve aygıt adı veya iki nokta arasında bir boşluk aygıt adının bir parçası olarak kullanmayın.  
  
|Aygıt adı|Temsil eder|  
|-----------------|----------------|  
|YEDEK|İkincil cihaz|  
|CON|Konsol|  
|PRN|Yazıcı|  
|NUL|NULL aygıt (dosyası oluşturuldu)|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komut satırını bir eşlem yazıcıya gönderir:  
  
```  
CL /FmPRN HELLO.CPP  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çıktı dosyası (/ F) seçenekleri](../../build/reference/output-file-f-options.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)