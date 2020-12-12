---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3384'
title: Derleyici hatası C3384
ms.date: 11/04/2016
f1_keywords:
- C3384
helpviewer_keywords:
- C3384
ms.assetid: c9f92c6a-62a9-4333-b2b1-bc55c7f288b6
ms.openlocfilehash: 79d5aabf185702c3d85485744b14e714a32aa76b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285584"
---
# <a name="compiler-error-c3384"></a>Derleyici hatası C3384

' type_parameter ': değer kısıtlaması ve başvuru kısıtlaması birbirini dışlıyor

Genel bir türü **`value class`** ve ile kısıtlayabilirsiniz **`ref class`** .

Daha fazla bilgi için bkz. [genel tür parametrelerindeki kısıtlamalar (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C3384 oluşturur.

```cpp
// C3384.cpp
// compile with: /c /clr
generic <typename T>
where T : ref class
where T : value class   // C3384
ref class List {};
```
