---
title: Derleyici Hatası C3384
ms.date: 11/04/2016
f1_keywords:
- C3384
helpviewer_keywords:
- C3384
ms.assetid: c9f92c6a-62a9-4333-b2b1-bc55c7f288b6
ms.openlocfilehash: d1b7e1a69035df358cf84ad791f611928dab8b5a
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58773638"
---
# <a name="compiler-error-c3384"></a>Derleyici Hatası C3384

'type_parameter': değer kısıtlaması ile ref birbirini dışlar.

Her iki genel bir tür katlarıyla sınırlamak `value class` ve `ref class`.

Bkz: [genel tür parametrelerindeki kısıtlamalar (C + +/ CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3384 oluşturur.

```
// C3384.cpp
// compile with: /c /clr
generic <typename T>
where T : ref class
where T : value class   // C3384
ref class List {};
```