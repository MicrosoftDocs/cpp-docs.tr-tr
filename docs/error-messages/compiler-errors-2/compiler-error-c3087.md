---
title: Derleyici hatası C3087
ms.date: 11/04/2016
f1_keywords:
- C3087
helpviewer_keywords:
- C3087
ms.assetid: 4f5bdd52-a853-4f02-b160-6868e9190b9d
ms.openlocfilehash: 6b9ae71ebfbcfcd5936a2fc3ca666aa51e59bfb5
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751423"
---
# <a name="compiler-error-c3087"></a>Derleyici hatası C3087

' named_argument ': ' Attribute ' çağrısı bu üyeyi zaten başlatıyor

Aynı öznitelik bloğunda adlandırılmış bir bağımsız değişken, aynı değer için adlandırılmamış bir bağımsız değişkenle belirtildi. Yalnızca adlandırılmış veya adlandırılmamış bir bağımsız değişken belirtin.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3087 oluşturur.

```cpp
// C3087.cpp
// compile with: /c
[idl_quote("quote1", text="quote2")];   // C3087
[idl_quote(text="quote3")];   // OK
[idl_quote("quote4")];   // OK
```
