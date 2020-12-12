---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3495'
title: Derleyici hatası C3495
ms.date: 11/04/2016
f1_keywords:
- C3495
helpviewer_keywords:
- C3495
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
ms.openlocfilehash: 3c04c80182dad32b539e09224fd9e303b3325578
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113174"
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
