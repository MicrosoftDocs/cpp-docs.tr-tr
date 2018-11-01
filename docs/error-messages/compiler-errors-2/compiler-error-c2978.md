---
title: Derleyici Hatası C2978
ms.date: 11/04/2016
f1_keywords:
- C2978
helpviewer_keywords:
- C2978
ms.assetid: 5e7bee82-e266-4ccd-ad2e-ee89606ec5bf
ms.openlocfilehash: 25798e793bec7d09ea1f307ec1e2d9a63b9dbe27
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428112"
---
# <a name="compiler-error-c2978"></a>Derleyici Hatası C2978

sözdizimi hatası: beklenen 'keyword1' veya 'keyword2'; türü 'keyword3' bulundu genel türler tür olmayan parametreler desteklenmez.

Genel sınıf yanlış bildirildi. Bkz: [genel türler](../../windows/generics-cpp-component-extensions.md)daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2978 oluşturur.

```
// C2978.cpp
// compile with: /clr /c
generic <ref class T>   // C2978
// try the following line instead
// generic <typename T>   // OK
ref class Utils {
   static void sort(T elems, size_t size);
};

generic <int>
// try the following line instead
// generic <class T>
ref class Utils2 {
   static void sort(T elems, size_t size);
};
```