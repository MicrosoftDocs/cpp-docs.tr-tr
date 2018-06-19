---
title: Derleyici Hatası C3809 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3809
dev_langs:
- C++
helpviewer_keywords:
- C3809
ms.assetid: 37eca584-c20c-464e-8e45-a987214b7ce4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4b9fabec4da63bfe881e0020e99cd5c49a51789
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33273046"
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