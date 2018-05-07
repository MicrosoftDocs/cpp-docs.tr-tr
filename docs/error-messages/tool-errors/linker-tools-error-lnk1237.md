---
title: Bağlayıcı araçları hatası LNK1237 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1237
dev_langs:
- C++
helpviewer_keywords:
- LNK1237
ms.assetid: 8722ffa8-096a-4bb0-85f9-f3aa0e10872a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1ffc337d6b1548db4717dc4b87ff8aa25ef92e93
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1237"></a>Bağlayıcı Araçları Hatası LNK1237
kod oluşturma sırasında derleyici simgesi 'Modülü 'ile /GL derlenmiş Modülü' tanımlanmış Sembol' referansı sunmuştur.  
  
 Kod oluşturma sırasında derleyici daha sonra derlenmiş tanımları çözülmüş simgeleri eklemeniz gerekir değil **/GL**. `symbol` kullanılmaya başlanan ve daha sonra ile derlenen bir tanımı çözümlenen bir simge **/GL**.  
  
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