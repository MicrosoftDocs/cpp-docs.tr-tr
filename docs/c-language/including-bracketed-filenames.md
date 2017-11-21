---
title: "Köşeli parantez içindeki dosya adlarını dahil etme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 6a4e5411-c35e-48b8-90ef-b37ac324ed94
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f118417a7ed2fdf8cad77775e144b81655c56916
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="including-bracketed-filenames"></a>Köşeli Parantez İçindeki Dosya Adlarını Dahil Etme
**ANSI 3.8.2** includable kaynak dosyaları bulma yöntemi  
  
 Köşeli ayraçlar içine alınan dosya belirtimleri için, önişlemci ana dosyaların dizinlerinde arama yapmaz. Dosyaları bir "üst" dosyasıdır [#include](../preprocessor/hash-include-directive-c-cpp.md) da yönergesi. Bunun yerine, derleyici komut satırında /I öğesinden sonra belirtilen dizinlerde dosyayı arayarak başlar. Önişlemci INCLUDE ortam değişkeni /ı seçeneği mevcut değil veya başarısız olursa, köşeli parantez içinde içerme dosyaları bulmak için kullanır. INCLUDE ortam değişkeni noktalı virgülle ayırarak birden fazla yol içerebilir (**;**). Birden fazla dizine parçası olarak /ı seçeneği veya INCLUDE ortam değişkeni içinde görünüyorsa, önişlemci bunları göründükleri sırada arar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ön işleme yönergeleri](../c-language/preprocessing-directives.md)