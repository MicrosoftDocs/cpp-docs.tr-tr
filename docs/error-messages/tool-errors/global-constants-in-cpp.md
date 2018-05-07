---
title: C++'da Global sabitler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- global constants
- constants, global
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1f1ee5fdf3d50f30e02bd48fe3664c10d26a8449
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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