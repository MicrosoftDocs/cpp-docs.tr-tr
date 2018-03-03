---
title: "Derleyici Hatası C3807 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3807
dev_langs:
- C++
helpviewer_keywords:
- C3807
ms.assetid: 7e2b0aab-8c61-4e71-b9c1-fcaeb6a1b5ea
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5be5f1f4d28393f561eda280ab555ba58cf5a228
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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