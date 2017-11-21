---
title: "Derleyici Hatası C3813 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3813
dev_langs: C++
helpviewer_keywords: C3813
ms.assetid: ffdbc489-71bf-4cd6-988c-f824c9ab3ceb
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cabe753691b3d72ede25f0c25404d73fb63ceba8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3813"></a>Derleyici Hatası C3813
özellik bildirimi yalnızca bir yönetilen tanımını veya WinRT türü içinde yer alabilir  
  
A [özelliği](../../dotnet/how-to-use-properties-in-cpp-cli.md) yalnızca yönetilen veya Windows çalışma zamanı içinde bildirilebilir türü. Yerel türler desteklemez `property` anahtar sözcüğü.  
  
## <a name="example"></a>Örnek  
Aşağıdaki örnek C3813 oluşturur ve düzeltmek gösterilmektedir:  
  
```cpp  
// C3813.cpp  
// compile by using: cl /c /clr C3813.cpp  
class A  
{  
   property int Int; // C3813  
};  
  
ref class B  
{  
   property int Int; // OK - declared within managed type  
};  
```