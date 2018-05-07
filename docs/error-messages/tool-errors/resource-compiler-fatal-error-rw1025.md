---
title: Kaynak Derleyicisi önemli hatası RW1025 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RW1025
dev_langs:
- C++
helpviewer_keywords:
- RW1025
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ba216e63cb0cae92b4541800493a2fb6195553a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="resource-compiler-fatal-error-rw1025"></a>Kaynak Derleyicisi Önemli Hatası RW1025
Şimdiye kadar yığın bellek yetersiz  
  
 Çok fazla yer işgal bellekte yazılım olup olmadığını denetleyin. CHKDSK program elinizde ne kadar bellek bulmak için kullanın.  
  
 Büyük kaynak dosyası oluşturuyorsanız, bir kaynak betik iki dosyaya bölün. İki .res dosyaları oluşturduktan sonra bunları birlikte katılmaya MS-DOS komut satırını kullanın:  
  
```  
copy first.res /b + second.res /b full.res  
```