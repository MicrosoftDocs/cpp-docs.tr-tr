---
title: Derleyici Hatası C2842 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2842
dev_langs:
- C++
helpviewer_keywords:
- C2842
ms.assetid: 8674f08d-9f50-46ad-9229-abc6b74fa0e5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fe0a95edfa484eb8606b914424e52483c4c1c52d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2842"></a>Derleyici Hatası C2842
'class': yönetilen WinRT türü kendi 'new işleci' tanımlayamaz veya 'delete işleci  
  
 Kendi tanımlayabilirsiniz ** işleci yeni veya **delete işleci** yerel yığında bellek ayırma yönetmek için. Ancak, yalnızca yönetilen yığında ayrılmış olduğundan başvuru sınıflar bu işleçlere tanımlayamazsınız.  

  
 Daha fazla bilgi için bkz: [kullanıcı tanımlı işleçler (C + +/ CLI)](../../dotnet/user-defined-operators-cpp-cli.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2842 oluşturur.  
  
```  
// C2842.cpp  
// compile with: /clr /c  
ref class G {  
   void* operator new( size_t nSize );   // C2842  
};  
```  
