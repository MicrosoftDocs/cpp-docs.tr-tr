---
title: "Derleyici Hatası C3077 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3077
dev_langs: C++
helpviewer_keywords: C3077
ms.assetid: d9f3c619-d1e2-4656-81a5-a35a9586a7d4
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 33f7a751881843a76c4a1ce8aaf4495948b125fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3077"></a>Derleyici Hatası C3077
'sonlandırıcıyı': bir sonlandırıcı yalnızca bir başvuru türü üyesi olabilir  
  
 Yerel bir Sonlandırıcısı veya değer türü bildiremezsiniz.  
  
 Daha fazla bilgi için bkz: [yok ediciler ve sonlandırıcılar nasıl yapılır: sınıfları ve yapıları tanımlama ve kullanma (C + +/ CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3077 oluşturur.  
  
```  
// C3077.cpp  
// compile with: /clr /c  
value struct vs {  
   !vs(){}   // C3077  
};  
  
ref struct rs {  
protected:  
   !rs(){}   // OK  
};  
```