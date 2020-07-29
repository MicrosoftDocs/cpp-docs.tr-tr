---
title: Derleyici hatası C3495
ms.date: 11/04/2016
f1_keywords:
- C3495
helpviewer_keywords:
- C3495
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
ms.openlocfilehash: a67d4d859e3a9dd2241f14a476492df0fd3e6b8d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223427"
---
# <a name="compiler-error-c3495"></a>Derleyici hatası C3495

' var ': bir lambda yakalamanın otomatik depolama süresi olmalıdır

Ya da olarak işaretlenen bir değişken gibi otomatik depolama süresine sahip olmayan bir değişken yakalayamazsınız **`static`** **`extern`** .

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- **`static`** **`extern`** Lambda ifadesinin yakalama listesine bir veya değişkeni iletmeyin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3495 üretir çünkü **`static`** değişken `n` bir lambda ifadesinin yakalama listesinde görünür:

```cpp
// C3495.cpp

int main()
{
   static int n = 66;
   [&n]() { return n; }(); // C3495
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda Ifadeleri](../../cpp/lambda-expressions-in-cpp.md)
