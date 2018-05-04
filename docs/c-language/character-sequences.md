---
title: Karakter dizileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 85cf817a4d50346b9d10a9a9d1bc27abb5904433
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="character-sequences"></a>Karakter Sıraları
**ANSI 3.8.2** kaynak dosya karakter sıraları eşleme  
  
 Önişlemci deyimleri, kaçış dizilerinin desteklenmemesi dışında kaynak dosyası deyimleriyle aynı karakter kümesini kullanır.  
  
 Bu nedenle, bir içerme dosyasına yönelik bir yol belirtmek istediğinizde yalnızca bir ters eğik çizgi kullanın:  
  
```  
#include "path1\path2\myfile"  
```  
  
 Kaynak kodu içinde iki ters eğik çizgi gereklidir:  
  
```  
fil = fopen( "path1\\path2\\myfile", "rt" );  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ön işleme Yönergeleri](../c-language/preprocessing-directives.md)