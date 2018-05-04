---
title: BSCMAKE komut dosyası (yanıt dosyası) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a879306078c52e0ad11d29f1786a2e55c2480d2f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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