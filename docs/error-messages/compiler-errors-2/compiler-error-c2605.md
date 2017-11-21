---
title: "Derleyici Hatası C2605 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2605
dev_langs: C++
helpviewer_keywords: C2605
ms.assetid: a0e6f132-5acf-4e19-b277-ddf196d182bf
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 48b55b06f0d6af12f4b0476bc604089b043ae8a9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2605"></a>Derleyici Hatası C2605
'name': Bu yöntem, yönetilen veya WinRT içinde ayrılmış sınıfı  
  
 Derleyici iç işlevler için tarafından belirli adları ayrılmıştır.  Daha fazla bilgi için bkz: [yok ediciler ve sonlandırıcılar](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2605 oluşturur.  
  
```  
// C2605.cpp  
// compile with: /clr /c  
ref class R {  
protected:  
   void Finalize() {}   // C2605  
};  
```