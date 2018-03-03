---
title: "BSCMAKE komut dosyası (yanıt dosyası) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- BSCMAKE, response file
- BSCMAKE, command file
- response files, BSCMAKE
- command files, BSCMAKE
- response files
- command files
ms.assetid: abdffeea-35c7-4f2d-8c17-7d0d80bac314
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0c250af9f1af96bb051be0b2cd347ecd8d98d809
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [BSCMAKE Başvurusu](../../build/reference/bscmake-reference.md)