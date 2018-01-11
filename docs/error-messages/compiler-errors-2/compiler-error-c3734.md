---
title: "Derleyici Hatası C3734 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3734
dev_langs: C++
helpviewer_keywords: C3734
ms.assetid: 4e2afdcc-7da9-45a1-9c96-85f25e2986e8
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: df4b894be813b3b9db641bb7a247bc0c98d8cf22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3734"></a>Derleyici Hatası C3734
'class': yönetilen veya WinRT sınıfı bir coclass'ı olamaz  
  
 [Coclass](../../windows/coclass.md) özniteliği ile kullanılamaz yönetilen veya WinRT sınıfları.  
  
 Aşağıdaki örnek C3734 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C3734.cpp  
// compile with: /clr /c  
[module(name="x")];  
  
[coclass]  
ref class CMyClass {   // C3734 remove the ref keyword to resolve  
};  
```  
