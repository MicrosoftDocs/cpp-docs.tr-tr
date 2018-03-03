---
title: Karakter dizileri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 09134a17ad8711169a3afc30490c188af47a3f42
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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