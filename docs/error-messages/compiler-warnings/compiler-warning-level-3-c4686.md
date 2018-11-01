---
title: Derleyici Uyarısı (Düzey 3) C4686
ms.date: 08/27/2018
f1_keywords:
- C4686
helpviewer_keywords:
- C4686
ms.assetid: 767c83c2-9e4b-4f9e-88c8-02128ba563f4
ms.openlocfilehash: 5e23e6aa69fe8a59e3dfd22af7e33780c223cdd3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50584528"
---
# <a name="compiler-warning-level-3-c4686"></a>Derleyici Uyarısı (Düzey 3) C4686

> '*kullanıcı tanımlı tür*': davranışta olası bir değişiklik, udt'de değişiklik iade çağırma kuralı

## <a name="remarks"></a>Açıklamalar

Bir sınıf şablonu uzmanlığı değildi, dönüş türü içinde kullanılan önce tanımlanır. Sınıfın örneğini oluşturur, hiçbir şey C4686 çözümler; bir örneği bildirme veya bir üyeye (C\<int >:: herhangi bir şey) de seçeneklerdir.

Varsayılan olarak bu uyarıyı kapalıdır. Bkz: [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdakileri deneyin:

```cpp
// C4686.cpp
// compile with: /W3
#pragma warning (default : 4686)
template <class T>
class C;

template <class T>
C<T> f(T);

template <class T>
class C {};

int main() {
   f(1);   // C4686
}

template <class T>
C<T> f(T) {
   return C<int>();
}
```