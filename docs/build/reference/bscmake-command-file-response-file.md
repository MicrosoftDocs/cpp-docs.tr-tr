---
title: "BSCMAKE komut dosyası (yanıt dosyası) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- BSCMAKE, response file
- BSCMAKE, command file
- response files, BSCMAKE
- command files, BSCMAKE
- response files
- command files
ms.assetid: abdffeea-35c7-4f2d-8c17-7d0d80bac314
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1d5dd2696a48a84672350b90b569c8f0caf7c3cd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="bscmake-command-file-response-file"></a>BSCMAKE Komut Dosyası (Yanıt Dosyası)
Bölümünü veya tümünü bir komut dosyası komut satırı girişinde sağlayabilir. Aşağıdaki sözdizimini kullanarak komut dosyasını belirtin:  
  
```  
BSCMAKE @filename  
```  
  
 Yalnızca bir komut dosyası izin verilir. Bir yol belirtebilirsiniz *filename*. Öncesinde *filename* ile bir at işareti (@). BSCMAKE uzantı varsaymaz. Ek belirtebilirsiniz *sbrfiles* sonra komut satırında *filename*. Komut dosyası komut satırında belirtirsiniz gibi BSCMAKE girdisi aynı sırada içeren bir metin dosyasıdır. Komut satırı bağımsız değişkenleri, bir veya daha fazla boşluk, sekme veya yeni satır karakteri ile ayırın.  
  
 Aşağıdaki komutu bir komut dosyası kullanarak BSCMAKE çağırır:  
  
```  
BSCMAKE @prog1.txt  
```  
  
 Bir örnek komut dosyası verilmiştir:  
  
```  
/n /v /o main.bsc /El  
/S (  
toolbox.h  
verdate.h c:\src\inc\screen.h  
)  
file1.sbr file2.sbr file3.sbr file4.sbr  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [BSCMAKE başvurusu](../../build/reference/bscmake-reference.md)