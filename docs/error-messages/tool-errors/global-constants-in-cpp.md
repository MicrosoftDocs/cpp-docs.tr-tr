---
title: C++'da Global sabitler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- global constants
- constants, global
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 766e1a6f48ecf3f64110e64d916c50d92c89345d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [Bağlayıcı Araçları Hatası LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)