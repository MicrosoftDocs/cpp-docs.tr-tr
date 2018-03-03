---
title: "Derleyici Hatası C3893 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3893
dev_langs:
- C++
helpviewer_keywords:
- C3893
ms.assetid: 90d52eae-6ef2-4db1-b7ad-92f9e8b140fb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4fee017305c90d9da69f5432815c0005eb84352c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3893"></a>Derleyici Hatası C3893
'var': 'type_name' sınıfının bir örneği oluşturucuda initonly veri üyesi l-değeri kullanımına izin yalnızca  
  
 Statik [initonly](../../dotnet/initonly-cpp-cli.md) veri üyeleri yalnızca statik bir oluşturucu gerçekleştirilecek kendi adresi olabilir.  
  
 Örnek (statik olmayan) initonly veri üyeleri yalnızca adresleri örneği (statik olmayan) kurucularda alınmış olabilir.  
  
 Aşağıdaki örnek C3893 oluşturur:  
  
```  
// C3893.cpp  
// compile with: /clr  
ref struct Y1 {  
   Y1() : data_var(0) {  
      int% i = data_var;   // OK  
   }  
   initonly int data_var;  
};  
  
int main(){  
   Y1^ y= gcnew Y1;  
   int% i = y->data_var;   // C3893  
}  
```