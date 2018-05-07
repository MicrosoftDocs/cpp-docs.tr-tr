---
title: Derleyici Hatası C3839 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3839
dev_langs:
- C++
helpviewer_keywords:
- C3839
ms.assetid: 0957faff-1e9f-439b-876b-85bd8d2c578d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cbb5541e07d168df36bae83f81b7b8a8a7273665
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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