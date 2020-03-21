---
title: Derleyici hatası C3495
ms.date: 11/04/2016
f1_keywords:
- C3495
helpviewer_keywords:
- C3495
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
ms.openlocfilehash: 6fe4286142c90f341925d7e76ca8de6d3b7daa9f
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80075005"
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
