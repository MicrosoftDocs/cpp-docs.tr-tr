---
title: Karakter dizileri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c097f213d790a992d12a8c358282a5340fce52c4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Ön işleme yönergeleri](../c-language/preprocessing-directives.md)