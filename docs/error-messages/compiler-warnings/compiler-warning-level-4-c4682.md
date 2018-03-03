---
title: "Derleyici Uyarısı (düzey 4) C4682 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4682
dev_langs:
- C++
helpviewer_keywords:
- C4682
ms.assetid: 858ea157-1244-4a61-85df-97b3de43d418
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d367203113ea8fad20cd914d381b4c941856d6b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4682"></a>Derleyici Uyarısı (düzey 4) C4682
'parametresi': [in] varsayarak belirtilen yönlü parametre özniteliği yok  
  
 Bir parametre öznitelikli arabirimdeki bir yöntem tek yönlü özniteliklerinden biri yok: [içinde](../../windows/in-cpp.md) veya [çıkışı](../../windows/out-cpp.md). Parametre için içinde varsayılan olarak ayarlanır.  
  
 Varsayılan olarak bu uyarı kapalıdır. Bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.  
  
 Aşağıdaki örnek C4682 oluşturur:  
  
```  
// C4682.cpp  
// compile with: /W4  
#pragma warning(default : 4682)  
#include <windows.h>  
[module(name="MyModule")];  
  
[ library_block, object, uuid("c54ad59d-d516-41dd-9acd-afda17565c2b") ]  
__interface IMyIface : IUnknown  
{  
   HRESULT f1(int i, int *pi); // C4682  
   // try the following line  
   // HRESULT f1([in] int i, [in] int *pi);  
};  
  
int main()  
{  
}  
```