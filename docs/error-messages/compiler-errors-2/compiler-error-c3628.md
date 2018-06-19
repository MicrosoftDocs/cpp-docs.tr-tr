---
title: Derleyici Hatası C3628 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3628
dev_langs:
- C++
helpviewer_keywords:
- C3628
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5210a9bb91b86c63f0cebabce8901c9af50ae896
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33266421"
---
# <a name="compiler-error-c3628"></a>Derleyici Hatası C3628
'temel sınıfı': yönetilen veya WinRTclasses yalnızca ortak devralma desteği  
  
Yönetilen veya WinRT kullanmak için bir girişimde bulunuldu olarak sınıf bir [özel](../../cpp/private-cpp.md) veya [korumalı](../../cpp/protected-cpp.md) temel sınıfı. Bir yönetilen veya WinRT sınıfı yalnızca kullanılabilir ile temel sınıf olarak [ortak](../../cpp/public-cpp.md) erişim.  
  
Aşağıdaki örnek C3628 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C3628a.cpp  
// compile with: /clr  
ref class B {  
};  
  
ref class D : private B {   // C3628  
  
// The following line resolves the error.  
// ref class D : public B {  
};  
  
int main() {  
}  
```  
