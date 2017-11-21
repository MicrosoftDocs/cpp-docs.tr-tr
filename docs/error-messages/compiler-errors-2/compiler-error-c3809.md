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
ms.openlocfilehash: e68e6f3b1309a0135b439bfe8f3f067a0c90a6ac
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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