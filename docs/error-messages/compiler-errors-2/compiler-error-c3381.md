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
ms.openlocfilehash: 7bd6c1d641f7476d3c372939b948931a306e0f80
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080720"
---
# <a name="compiler-error-c3381"></a>Derleyici Hatası C3381

'derlemenin': derleme erişim belirticileri bulunan ve yalnızca/CLR seçeneğiyle derlenmiş kodda

Yerel türler derlemenin dışında görünür olabilir, ancak yalnızca derleme erişimi için yerel türlerde belirtebilirsiniz bir **/CLR** derleme.

Daha fazla bilgi için [türü görünürlük](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) ve [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3381 oluşturur.

```
// C3381.cpp
// compile with: /c
public class A {};   // C3381
```