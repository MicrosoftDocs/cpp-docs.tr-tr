---
title: "Önişlemci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: preprocessor
ms.assetid: e120eda3-b413-49f1-a07c-e9fb128cf500
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 596e17d0574f9f4935cf31ec71eb74cb2587d312
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="preprocessor"></a>Ön işlemci
Ön İşlemci kaynak dosyası metnin ilk çeviri aşaması bir parçası olarak işleyen bir metin işlemcisi ' dir. Önişlemci kaynak metni ayrıştırma değil, ancak bunu onu makrosu çağrıları bulma amacıyla belirteçler içine bölün. Derleyici normalde ilk seferde önişlemci çağırır rağmen önişlemci ayrıca ayrı ayrı derleme olmadan metin işlemek için çağrılabilir.  
  
 Ön İşlemci Başvurusu ortama aşağıdaki bölümleri içerir:  
  
-   [Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md)  
  
-   [Ön İşlemci işleçleri](../preprocessor/preprocessor-operators.md)  
  
-   [Önceden tanımlı makrolar](../preprocessor/predefined-macros.md)  
  
-   [Pragmalar](../preprocessor/pragma-directives-and-the-pragma-keyword.md)  
  
 **Microsoft özel**  
  
 Kullanarak ön işleme sonra kaynak kodunuzu listesini elde edebilirsiniz [/E](../build/reference/e-preprocess-to-stdout.md) veya [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) derleyici seçeneği. Her iki seçenek önişlemci çağırma ve sonuçta elde edilen metin olan, çoğu durumda, konsol standart çıktı aygıtına çıktı. /E içerdiğini farktır iki seçenekten `#line` yönergeleri ve /EP bu yönergeleri çıkışı kaldırır.  
  
 **SON Microsoft özel**  
  
##  <a name="_predir_special_terminology"></a>Özel terminolojisi  
 Önişlemci belgelerde "bağımsız değişkeni" terimi bir işleve varlık anlamına gelir. Bazı durumlarda, "gerçek" veya "işlev çağrısında belirtilen bağımsız değişken ifadesi ve sırasıyla işlevi tanımında belirtilen bağımsız değişken bildirimi tanımlayan resmi," değiştirilir.  
  
 "Değişken" terimi basit C türü veri nesnesine başvuruyor. "Nesne" terimi, C++ nesneleri ve değişkenleri için anlamına gelir; Bu kapsayıcı bir terimdir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C/C++ Ön İşlemci Başvurusu](../preprocessor/c-cpp-preprocessor-reference.md)   
 [Çeviri Aşamaları](../preprocessor/phases-of-translation.md)