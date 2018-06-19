---
title: Derleyici Hatası C3813 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3813
dev_langs:
- C++
helpviewer_keywords:
- C3813
ms.assetid: ffdbc489-71bf-4cd6-988c-f824c9ab3ceb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e947b281c90c4d2ace83971f1de972c29bde72ac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33273113"
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