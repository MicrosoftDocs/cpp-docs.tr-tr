---
title: "Derleyici Hatası C2842 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2842
dev_langs: C++
helpviewer_keywords: C2842
ms.assetid: 8674f08d-9f50-46ad-9229-abc6b74fa0e5
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3998ff0b07ba78228ac51bccac047d8889ccf81b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
