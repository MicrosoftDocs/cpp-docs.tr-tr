---
title: Bağlayıcı araçları hatası LNK1312 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1312
dev_langs:
- C++
helpviewer_keywords:
- LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 748276ed8fa459c41174f23d32bcef127cbdd510
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1312"></a>Bağlayıcı Araçları Hatası LNK1312
geçersiz veya bozuk dosya: derleme içeri aktarılamıyor  
  
 Derleme yaparken bir derleme, modül veya ile derlenmiş derlemeyi başka bir dosya **/CLR** geçirilmedi **/ASSEMBLYMODULE** bağlayıcı seçeneği.  Bir nesne dosyasına aktarılırsa **/ASSEMBLYMODULE**, nesne bağlayıcı doğrudan yerine için geçirmeniz yeterlidir **/ASSEMBLYMODULE**.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek .obj dosyası oluşturulur.  
  
```  
// LNK1312.cpp  
// compile with: /clr /LD  
public ref class A {  
public:  
   int i;  
};  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek LNK1312 oluşturur.  
  
```  
// LNK1312_b.cpp  
// compile with: /clr /LD /link /assemblymodule:LNK1312.obj  
// LNK1312 error expected  
public ref class M {};  
```