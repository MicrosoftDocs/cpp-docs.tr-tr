---
title: C++'da Global sabitler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs: C++
helpviewer_keywords:
- global constants
- constants, global
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f47be9bad6cf7c8ccafac5dc8ce3786f8ada0dfb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="global-constants-in-c"></a>C++'da Global Sabitler
C++'da global sabitler statik bağlantı vardır. Bu C. farklı. Bir genel kullanmaya çalışırsa, birden çok dosyalarında c++ sabit bir çözümlenmemiş dış hata alıyorsunuz. Derleyici global sabitler çıkışı, değişken için ayrılmış alan kalmıyor iyileştirir.  
  
 Bu hatayı gidermek için bir üstbilgi dosyasında const başlatmaları içerir ve gerekli olduğunda, yalnızca bu işlev prototipi boşmuş gibi CPP dosyalarınızda bu üstbilgisini yoldur. Diğer bir olasılık değişkeni sabit olmayan yapmak ve sabit başvuru onu değerlendirirken kullanmaktır.  
  
 Aşağıdaki örnek C2019 oluşturur:  
  
```  
// global_constants.cpp  
// LNK2019 expected  
void test(void);  
const int lnktest1 = 0;  
  
int main() {  
   test();  
}  
```  
  
 Ardından,  
  
```  
// global_constants_2.cpp  
// compile with: global_constants.cpp  
extern int lnktest1;  
  
void test() {  
  int i = lnktest1;   // LNK2019  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı araçları hatası LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)