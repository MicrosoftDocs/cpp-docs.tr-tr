---
title: Yol adını belirtme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- names [C++], compiler output files
- cl.exe compiler, output files
- output files, specifying pathnames
ms.assetid: 7a6595ce-3383-44ae-957a-466bfa29c343
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a2dd121909fbe0aa2f9305b7bd5779b995a69719
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375668"
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