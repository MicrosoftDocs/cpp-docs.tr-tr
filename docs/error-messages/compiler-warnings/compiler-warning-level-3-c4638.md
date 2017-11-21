---
title: "Derleyici Uyarısı (Düzey 3) C4638 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4638
dev_langs: C++
helpviewer_keywords: C4638
ms.assetid: 2c07923a-e103-4e40-bd11-fdfed428a5ec
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f1be99cb087ce664030d116135a2b4fb43c72da9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4638"></a>Derleyici Uyarısı (Düzey 3) C4638
XML Belge açıklama hedef: Bilinmeyen simgesi 'simgesi' referansı  
  
 Derleyici bir simge çözemedi (***simgesi***). Simgenin derlemede geçerli olmalıdır.  
  
 Aşağıdaki örnek C4638 oluşturur:  
  
```  
// C4638.cpp  
// compile with: /clr /doc /LD /W3  
using namespace System;  
  
/// Text for class MyClass.  
public ref class MyClass {   
public:  
   /// <summary> Text </summary>  
   /// <see cref="aSymbolThatAppearsNowhereInMyProject"/>  
   // Try the following line instead:  
   // /// <see cref="System::Console::WriteLine"/>  
   void MyMethod() {}  
};   // C4638  
```