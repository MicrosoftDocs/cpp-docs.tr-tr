---
title: Bağlayıcı araçları uyarısı LNK4247 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4247
dev_langs:
- C++
helpviewer_keywords:
- LNK4247
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6096bbfba9c60d8ed28aa660d078cd155f0316a3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4247"></a>Bağlayıcı Araçları Uyarısı LNK4247
Giriş Noktası 'decorated_function_name' zaten bir iş parçacığı özniteliği var; 'öznitelik yoksayıldı'  
  
 İle belirtilen bir giriş noktası [/Entry (giriş noktası simgesi)](../../build/reference/entry-entry-point-symbol.md), bir iş parçacığı özniteliği var ancak [/CLRTHREADATTRIBUTE (CLR iş parçacığı özniteliğini Ayarla)](../../build/reference/clrthreadattribute-set-clr-thread-attribute.md) Ayrıca, farklı bir iş parçacığı modeliyle belirtildi.  
  
 Bağlayıcı /CLRTHREADATTRIBUTE ile belirtilen değer yoksayılır.  
  
 Bu uyarıyı çözmek için:  
  
-   /CLRTHREADATTRIBUTE, derlemeden çıkarın.  
  
-   Öznitelik, kaynak kodu dosyanızdan kaldırın.  
  
-   Her iki öznitelik, derleme kaynak ve /CLRTHREADATTRIBUTE kaldırın ve varsayılan CLR iş parçacığı modelini kabul edin.  
  
-   Kaynak özniteliğiyle kabul şekilde /CLRTHREADATTRIBUTE için geçirilen değeri değiştirin.  
  
-   /CLRTHREADATTRIBUTE için geçirilen değer kabul sağlayacak şekilde, kaynak, özniteliğinde değiştirin.  
  
 Aşağıdaki örnek LNK4247 oluşturur  
  
```  
// LNK4247.cpp  
// compile with: /clr /c  
// post-build command: link /CLRTHREADATTRIBUTE:STA LNK4247.obj /entry:functionTitle /SUBSYSTEM:Console  
 [System::MTAThreadAttribute]  
void functionTitle (){}  
```