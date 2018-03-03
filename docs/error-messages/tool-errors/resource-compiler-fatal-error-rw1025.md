---
title: "Kaynak Derleyicisi önemli hatası RW1025 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RW1025
dev_langs:
- C++
helpviewer_keywords:
- RW1025
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 487968f8a1242dd4c36e4bbd9b4ede08a5ab4d95
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-fatal-error-rw1025"></a>Kaynak Derleyicisi Önemli Hatası RW1025
Şimdiye kadar yığın bellek yetersiz  
  
 Çok fazla yer işgal bellekte yazılım olup olmadığını denetleyin. CHKDSK program elinizde ne kadar bellek bulmak için kullanın.  
  
 Büyük kaynak dosyası oluşturuyorsanız, bir kaynak betik iki dosyaya bölün. İki .res dosyaları oluşturduktan sonra bunları birlikte katılmaya MS-DOS komut satırını kullanın:  
  
```  
copy first.res /b + second.res /b full.res  
```