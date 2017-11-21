---
title: "Derleyici Hatası C3839 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3839
dev_langs: C++
helpviewer_keywords: C3839
ms.assetid: 0957faff-1e9f-439b-876b-85bd8d2c578d
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8a8c9fa9112128b86123693aea7443d68e8531d0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3839"></a>Derleyici Hatası C3839
yönetilen bir çizgide veya WinRT türü değiştirilemiyor  
  
 Değişkenleri hizalamasını yönetilen veya Windows çalışma zamanı türleri CLR veya Windows çalışma zamanı tarafından denetlenen ve ile değiştirilemez [Hizala](../../cpp/align-cpp.md).  
  
 Aşağıdaki örnek C3839 oluşturur:  
  
```  
// C3839a.cpp  
// compile with: /clr  
ref class C  
{  
public:  
   __declspec(align(32)) int m_j; // C3839  
};  
  
int main()  
{  
}  
```