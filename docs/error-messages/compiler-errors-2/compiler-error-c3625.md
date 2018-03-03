---
title: "Derleyici Hatası C3625 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3625
dev_langs:
- C++
helpviewer_keywords:
- C3625
ms.assetid: fdf49f21-d6b1-42f4-9eec-23b04ae8b4aa
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8f2e61dfee1edb2628e18699d7f7ea204ed716c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3625"></a>Derleyici Hatası C3625
'NATIVE_TYPE': yerel tür yönetilen veya WinRT türetilemez 'type' yazın  
  
Yerel bir sınıf yönetilen veya WinRT devralır sınıfı. Daha fazla bilgi için bkz: [sınıflar ve yapılar](../../windows/classes-and-structs-cpp-component-extensions.md).  
  
## <a name="example"></a>Örnek  
Aşağıdaki örnek C3625 oluşturur:  
  
```  
// C3625.cpp  
// compile with: /clr /c  
ref class B {};  
class D : public B {};   // C3625 cannot inherit from a managed class  
```  
