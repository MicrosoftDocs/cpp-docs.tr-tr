---
title: Derleyici Hatası C3381
ms.date: 11/04/2016
f1_keywords:
- C3381
helpviewer_keywords:
- C3381
ms.assetid: d276c89f-8377-4cb6-a8d4-7770885f06c4
ms.openlocfilehash: ae416d68831d1964c89d938dfcddd364e521195c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328870"
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