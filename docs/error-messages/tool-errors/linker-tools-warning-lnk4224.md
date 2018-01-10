---
title: "Bağlayıcı araçları uyarısı LNK4224 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4224
dev_langs: C++
helpviewer_keywords: LNK4224
ms.assetid: 8624b70e-0b93-43cf-b457-834d38632d0b
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 96399e0c66eb3cb719073b2318513cd680723d97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4224"></a>Bağlayıcı Araçları Uyarısı LNK4224
seçeneği artık desteklenmiyor; göz ardı  
  
 Geçersiz, artık kullanılmayan bağlayıcı seçeneği belirtilen ve yoksayıldı.  
  
 Örneğin, / Comment yönergesi görünüyorsa LNK4224 ortaya çıkabilir. obj. / Comment yönergesi yoluyla eklenmiş [Açıklama (C/C++)](../../preprocessor/comment-c-cpp.md) pragma, kullanım dışı exestr seçeneğini kullanarak. DUMPBIN kullanmak [/ALL](../../build/reference/all.md) bağlayıcı yönergeleri .obj dosyasında görüntülemek için.  
  
 Mümkünse, .obj kaynağı değiştirmek ve pragma kaldırın. Bu uyarıyı yok sayarsanız bir .executable ile derlenmiş mümkündür **/CLR: pure** beklendiği gibi çalışmaz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek LNK4224 oluşturur.  
  
```  
// LNK4224.cpp  
// compile with: /c /Zi  
// post-build command: link LNK4224.obj /debug /debugtype:map  
int main () {  
   return 0;  
}  
```