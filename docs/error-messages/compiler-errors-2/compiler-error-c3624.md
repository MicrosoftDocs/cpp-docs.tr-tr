---
title: Derleyici Hatası C3624 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3624
dev_langs:
- C++
helpviewer_keywords:
- C3624
ms.assetid: eaac6a4f-eb11-4e4d-ab12-124ba995c5cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f38aece68d3ca3adff03ec0512cb78afc2e5ffa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030046"
---
# <a name="compiler-error-c3624"></a>Derleyici Hatası C3624

'type': Bu tür, derleme 'derlemesi' başvurusu gerektirir

Kodunuzu derlemek için gereken bir derleme (başvuru) belirtilmedi; derlemeye geçirmek [#using](../../preprocessor/hash-using-directive-cpp.md) yönergesi.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3624 oluşturur:

```
// C3624.cpp
// compile with: /clr /c
#using <System.Windows.Forms.dll>

// Uncomment the following 2 lines to resolve.
// #using <System.dll>
// #using <System.Drawing.dll>

using namespace System;

public ref class MyForm : public Windows::Forms::Form {};   // C3624
```
