---
title: Derleyici Hatası C3381 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3381
dev_langs:
- C++
helpviewer_keywords:
- C3381
ms.assetid: d276c89f-8377-4cb6-a8d4-7770885f06c4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a27961694bc5fad4080d8aceaf2f1cb65404319c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3381"></a>Derleyici Hatası C3381
'assembly': derleme erişim tanımlayıcıları kullanılabilir yalnızca/CLR seçeneğiyle derlenmiş kod  
  
 Yerel türü dışında derleme görünebilir, ancak yalnızca içindeki yerel türler için derleme erişimi belirtebilirsiniz bir **/CLR** derleme.  
  
 Daha fazla bilgi için bkz: [yazın görünürlük](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) ve [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3381 oluşturur.  
  
```  
// C3381.cpp  
// compile with: /c  
public class A {};   // C3381  
```