---
title: Köşeli parantez içindeki dosya adlarını dahil etme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 6a4e5411-c35e-48b8-90ef-b37ac324ed94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7ba45c21029a428784e1c8410dcf42295aa6350f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32383832"
---
# <a name="including-bracketed-filenames"></a>Köşeli Parantez İçindeki Dosya Adlarını Dahil Etme
**ANSI 3.8.2** includable kaynak dosyaları bulma yöntemi  
  
 Köşeli ayraçlar içine alınan dosya belirtimleri için, önişlemci ana dosyaların dizinlerinde arama yapmaz. Dosyaları bir "üst" dosyasıdır [#include](../preprocessor/hash-include-directive-c-cpp.md) da yönergesi. Bunun yerine, derleyici komut satırında /I öğesinden sonra belirtilen dizinlerde dosyayı arayarak başlar. Önişlemci INCLUDE ortam değişkeni /ı seçeneği mevcut değil veya başarısız olursa, köşeli parantez içinde içerme dosyaları bulmak için kullanır. INCLUDE ortam değişkeni noktalı virgülle ayırarak birden fazla yol içerebilir (**;**). Birden fazla dizine parçası olarak /ı seçeneği veya INCLUDE ortam değişkeni içinde görünüyorsa, önişlemci bunları göründükleri sırada arar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ön işleme Yönergeleri](../c-language/preprocessing-directives.md)