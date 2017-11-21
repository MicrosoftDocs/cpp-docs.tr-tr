---
title: "Derleyici Hatası C3121 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3121
dev_langs: C++
helpviewer_keywords: C3121
ms.assetid: 1d3c7be4-d42d-4def-8d53-182c0c5cc237
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 56e97505119f16cf81fdc216527af39eaa837dba
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3121"></a>Derleyici Hatası C3121
GUID sınıfı 'class_name' değiştirilemiyor  
  
 Sınıf kimliği ile değiştirme girişiminde [__declspec(uuid)](../../cpp/uuid-cpp.md).  
  
 Örneğin, aşağıdaki kod C3121 oluşturur:  
  
```  
// C3121.cpp  
[emitidl];  
[module(name="MyLibrary")];  
  
[coclass, uuid="00000000-0000-0000-0000-111111111111"]  
class __declspec(uuid("00000000-0000-0000-0000-111111111112")) A   // C3121  
{  
};  
int main()  
{  
}  
```