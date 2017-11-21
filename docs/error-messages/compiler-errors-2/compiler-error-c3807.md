---
title: "Derleyici Hatası C3807 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3807
dev_langs: C++
helpviewer_keywords: C3807
ms.assetid: 7e2b0aab-8c61-4e71-b9c1-fcaeb6a1b5ea
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fc8e760d295cc0a4c2482449038ea09e89547425
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3807"></a>Derleyici Hatası C3807
'type': 'type2' bir sınıf ComImport özniteliğine sahip türetilemez, yalnızca arabirim uygulamasına izin verilir  
  
 Türetilen bir tür <xref:System.Runtime.InteropServices.ComImportAttribute> yalnızca bir arabirimi uygulayabilirsiniz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3807 oluşturur.  
  
```  
// C3807.cpp  
// compile with: /clr /c  
ref struct S {};  
interface struct I {};  
  
[System::Runtime::InteropServices::ComImportAttribute()]  
ref struct S1 : S {};   // C3807  
ref struct S2 : I {};  
```