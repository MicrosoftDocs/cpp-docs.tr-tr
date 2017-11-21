---
title: "Derleyici Hatası C2384 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2384
dev_langs: C++
helpviewer_keywords: C2384
ms.assetid: 8145f7ad-31b1-406d-ac43-0d557feab635
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0d87769a2e02e6214e474dab2b74859e85a6880b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2384"></a>Derleyici Hatası C2384
'member': __declspec(thread) yönetilen üyesi ya da WinRT sınıfı uygulayamazsınız  
  
 [İş parçacığı](../../cpp/thread.md) `__declspec` değiştiricisi yönetilen üyesi ya da Windows çalışma zamanı sınıfı üzerinde kullanılamaz.  
  
 Statik iş parçacığı yerel depolama yönetilen kodda yalnızca kullanılabilir için statik olarak yüklenen DLL'ler — işlemi başladığında DLL statik olarak yüklenmesi gerekir. Windows çalışma zamanı iş parçacığı yerel depolaması desteklemez.  
  
 Aşağıdaki satırı C2384 oluşturur ve C + düzeltmek nasıl gösterir +/ CLI kod:  
  
```  
// C2384.cpp  
// compile with: /clr /c  
public ref class B {  
public:  
   __declspec( thread ) static int tls_i = 1;   // C2384  
  
   // OK - declare with attribute instead  
   [System::ThreadStaticAttribute]  
   static int tls_j;  
};  
```