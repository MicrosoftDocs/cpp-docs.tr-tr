---
title: "Bağlayıcı araçları uyarısı LNK4078 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4078
dev_langs: C++
helpviewer_keywords: LNK4078
ms.assetid: 5a16796d-6caf-42d9-8f65-b042843eafb8
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c6fc69436d30500eeb73af8435aad962bb228e07
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-warning-lnk4078"></a>Bağlayıcı Araçları Uyarısı LNK4078
birden çok 'bölüm adı' bölümü farklı özniteliklerle bulundu  
  
 İki bağlantı bulunamadı veya ancak farklı öznitelikleri aynı olan daha fazla bölüm adı.  
  
 Bu uyarı bağlantı veya LIB önceki bir sürümü tarafından oluşturulmuş bir içeri aktarma kitaplığı veya dışarı aktarma dosyası neden olabilir.  
  
 Dosya ve yeniden bağlama yeniden oluşturun.  
  
## <a name="example"></a>Örnek  
 LNK4078 göre önemli bir değişiklik de kaynaklanabilir: tarafından adlandırılmış bölüm [init_seg](../../preprocessor/init-seg.md) x86 üzerinde okuma/yazma, artık salt okunur.  
  
 Aşağıdaki örnek LNK4078 oluşturur.  
  
```  
// LNK4078.cpp  
// compile with: /W1  
// LNK4078 expected  
#include <stdio.h>  
#pragma warning(disable : 4075)  
typedef void (__cdecl *PF)(void);  
int cxpf = 0;   // number of destructors to call  
PF pfx[200];   // pointers to destructors.  
  
struct A { A() {} };  
  
int myexit (PF pf) { return 0; }  
  
#pragma section(".mine$a", read, write)  
// try the following line instead  
// #pragma section(".mine$a", read)  
__declspec(allocate(".mine$a")) int ii = 1;  
  
#pragma section(".mine$z", read, write)  
// try the following line instead  
// #pragma section(".mine$z", read)  
__declspec(allocate(".mine$z")) int i = 1;  
  
#pragma data_seg()  
#pragma init_seg(".mine$m", myexit)  
A bbbb;   
A cccc;  
int main() {}  
```