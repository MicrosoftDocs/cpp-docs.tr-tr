---
title: "Derleyici Hatası C3809 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3809
dev_langs: C++
helpviewer_keywords: C3809
ms.assetid: 37eca584-c20c-464e-8e45-a987214b7ce4
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 22b4406676ced6c2a96241eb15a4329d8933b777
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3809"></a>Derleyici Hatası C3809
'class': yönetilen veya WinRT türü arkadaş işlevleri/sınıfları/arabirimlerden sahip olamaz  
  
 Yönetilen türler ve Windows çalışma zamanı türleri arkadaşlarına izin vermez. Bu hatayı düzeltmek değil bildirmek için arkadaş içinde yönetilen ya da Windows çalışma zamanı türleri.  
  
 Aşağıdaki örnek C3809 oluşturur:  
  
```  
// C3809a.cpp  
// compile with: /clr  
ref class A {};  
  
ref class B  
{  
public:  
   friend ref class A;   // C3809  
};  
  
int main()  
{  
}  
```