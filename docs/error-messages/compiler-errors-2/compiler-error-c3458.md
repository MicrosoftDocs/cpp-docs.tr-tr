---
title: "Derleyici Hatası C3458 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3458
dev_langs: C++
helpviewer_keywords: C3458
ms.assetid: 940202fd-8dcc-4042-9c96-3f9e9127d2f1
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fc2d65f3be48f65469a4d4c7a5c165fc3331d4c0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3458"></a>Derleyici Hatası C3458
'öznitelik1': 'zaten 'yapısı için' belirtilen öznitelik2' özniteliği  
  
 Birbirini dışlayan iki öznitelik aynı yapı için belirtildi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3458 oluşturur  
  
```  
// C3458.cpp  
// compile with: /clr /c  
[System::Reflection::DefaultMember("Chars")]  
public ref class MyString {  
public:  
   [System::Runtime::CompilerServices::IndexerName("Chars")]   // C3458  
   property char default[int] {  
      char get(int index);  
      void set(int index, char c);  
   }  
};  
```