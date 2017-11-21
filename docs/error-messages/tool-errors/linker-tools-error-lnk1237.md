---
title: "Bağlayıcı araçları hatası LNK1237 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1237
dev_langs: C++
helpviewer_keywords: LNK1237
ms.assetid: 8722ffa8-096a-4bb0-85f9-f3aa0e10872a
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 43ab77f153b6e53709422a1826a6beee25d65b2a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1237"></a>Bağlayıcı Araçları Hatası LNK1237
kod oluşturma sırasında derleyici simgesi 'Modülü 'ile /GL derlenmiş Modülü' tanımlanmış Sembol' referansı sunmuştur.  
  
 Kod oluşturma sırasında derleyici daha sonra derlenmiş tanımları çözülmüş simgeleri eklemeniz gerekir değil **/GL**. `symbol`kullanılmaya başlanan ve daha sonra ile derlenen bir tanımı çözümlenen bir simge **/GL**.  
  
 Daha fazla bilgi için bkz: [/GL (bütün Program iyileştirmesi)](../../build/reference/gl-whole-program-optimization.md).  
  
 LNK1237 çözmek için simgesiyle derleme değil **/GL** veya [exclude dışlama kuralı belirler (simge başvurularını zorla)](../../build/reference/include-force-symbol-references.md) simgenin başvuru zorlamak için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek LNK1237 oluşturur. Bu hatayı gidermek için değil LNK1237_a.cpp dizisinde başlatın ve ekleme **/ içerir: __chkstk** bağlantı komutu.  
  
```  
// LNK1237_a.cpp  
int main() {  
   char c[5000] = {0};  
}  
```  
  
```  
// LNK1237_b.cpp  
// compile with: /GS- /GL /c LNK1237_a.cpp  
// processor: x86  
// post-build command: (lib LNK1237_b.obj /LTCG & link LNK1237_a.obj LNK1237_b.lib /nodefaultlib /entry:main /LTCG)  
extern "C" void _chkstk(size_t s) {}  
```