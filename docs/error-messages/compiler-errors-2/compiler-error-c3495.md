---
title: Derleyici hatası C3495
ms.date: 11/04/2016
f1_keywords:
- C3495
helpviewer_keywords:
- C3495
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
ms.openlocfilehash: 1a61d4f2472ef6da8aedcf8a8ef90b70de47d8af
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738277"
---
# <a name="compiler-error-c3495"></a>Derleyici hatası C3495

' var ': bir lambda yakalamanın otomatik depolama süresi olmalıdır

`static` veya `extern`olarak işaretlenen bir değişken gibi otomatik depolama süresine sahip olmayan bir değişken yakalayamazsınız.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Lambda ifadesinin yakalama listesine bir `static` veya `extern` değişkeni iletmeyin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir lambda ifadesinin yakalama listesinde `static` değişkeni `n` göründüğünden, C3495 oluşturur:

```cpp
// C3495.cpp

int main()
{
   static int n = 66;
   [&n]() { return n; }(); // C3495
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)

