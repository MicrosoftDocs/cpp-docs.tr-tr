---
title: Derleyici Hatası C3218 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3218
dev_langs:
- C++
helpviewer_keywords:
- C3218
ms.assetid: 0eea19e0-503e-4e07-ae8b-2cb2e95922cd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6938768211a78ca2a72c78ebb03a8972e0a86a74
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33248277"
---
# <a name="compiler-error-c3218"></a>Derleyici Hatası C3218
'type': türü bir kısıtlama olarak izin verilmiyor  
  
 Bir kısıtlaması olmasını türü için bir değer türü veya bir yönetilen sınıf veya arabirim başvurusu olmalıdır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3218 oluşturur.  
  
```  
// C3218.cpp  
// compile with: /clr /c  
class A {};  
ref class B {};  
  
// Delete the following 3 lines to resolve.  
generic <class T>  
where T : A   // C3218  
ref class C {};  
  
// OK  
generic <class T>  
where  T : B  
ref class D {};  
```