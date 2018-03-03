---
title: -SYMBOLS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /symbols
dev_langs:
- C++
helpviewer_keywords:
- symbols, dumping
- public symbols
- symbols, displaying COFF symbol table
- symbol tables
- SYMBOLS dumpbin option
- /SYMBOLS dumpbin option
- -SYMBOLS dumpbin option
ms.assetid: 34bcae90-4561-4c77-a80c-065508dec39a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fb8a1a42bf0bbb3b0bf9b907f93e1c9d0e69cf5b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="symbols"></a>/SYMBOLS
```  
/SYMBOLS  
```  
  
 Bu seçenek COFF sembol tablosunu görüntüler. Sembol tabloları tüm nesne dosyalarda mevcut. COFF sembol tablosunu yalnızca/Debug ile bağlantılı bir görüntü dosyası görüntülenir.  
  
 /SYMBOLS için çıktıyı bir açıklaması verilmiştir. Winnt.h (IMAGE_SYMBOL ve IMAGE_AUX_SYMBOL) veya COFF belgelerine bakarak /SYMBOLS çıktı anlamı hakkında daha fazla bilgi bulunabilir.  
  
 Aşağıdaki örnek dökümü verilen:  
  
```  
Dump of file main.obj  
File Type: COFF OBJECT  
  
COFF    SYMBOL    TABLE  
000    00000000   DEBUG      notype      Filename      | .file  
      main.cpp  
002   000B1FDB   ABS      notype      Static      | @comp.id  
003   00000000   SECT1      notype      Static      | .drectve  
      Section length       26, #relocs   0, #linenums    0, checksum 722C964F  
005   00000000   SECT2      notype      Static      | .text  
      Section length      23, #relocs      1, #linenums    0, checksum 459FF65F, selection    1 (pick no duplicates)  
007   00000000   SECT2      notype ()   External      | _main  
008   00000000   UNDEF      notype ()   External      | ?MyDump@@YAXXZ (void __cdecl MyDump(void))  
  
String Table Size = 0x10 bytes  
  
Summary  
  
      26 .drectve  
      23 .text  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Simge sayıyı ile başlayan satırlar için aşağıdaki açıklama kullanıcılarla ilgili bilgilere sahip sütunlar açıklanmaktadır:  
  
-   İlk üç basamaklı sayı simgesi dizin/sayıdır.  
  
-   Üçüncü sütun bölü içeriyorsa*x*, sembolü nesne dosyasının bu bölümünde tanımlanır. Ancak UNDEF görünüyorsa, o nesnenin tanımlı değil ve başka bir yerde çözümlenmesi gerekir.  
  
-   Simgenin yalnızca söz konusu nesne içinde görünür olup ya da ortak Beşinci sütun (statik, dış) söyler (görünür harici olarak). Statik bir sembol, _sym, bir ortak simgesi _sym bağlı olmayacaktır; Bu işlevler _sym adlı iki farklı örnekleri olacaktır.  
  
 Numaralı satırda son sütun sembol adını, her ikisi de donatılmış ve ve.  
  
 Yalnızca [/HEADERS](../../build/reference/headers.md) DUMPBIN seçeneği ile üretilen dosyalarda kullanıma [/GL](../../build/reference/gl-whole-program-optimization.md) derleyici seçeneği.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DUMPBIN Seçenekleri](../../build/reference/dumpbin-options.md)