---
title: Bağlayıcı araçları uyarısı LNK4224 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4224
dev_langs:
- C++
helpviewer_keywords:
- LNK4224
ms.assetid: 8624b70e-0b93-43cf-b457-834d38632d0b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a051e341a22871b4229617b3958cb68dedc2921
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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