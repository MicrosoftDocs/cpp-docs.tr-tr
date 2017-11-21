---
title: "Bağlayıcı araçları hatası LNK1312 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1312
dev_langs: C++
helpviewer_keywords: LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0fc7bf47ff05f817b36ff9ff641fe7823aa38d9a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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