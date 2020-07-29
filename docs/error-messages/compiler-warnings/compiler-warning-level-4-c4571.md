---
title: Derleyici Uyarısı (düzey 4) C4571
ms.date: 11/04/2016
f1_keywords:
- C4571
helpviewer_keywords:
- C4571
ms.assetid: 07aa17bd-b15c-4266-824c-57cc445e8edd
ms.openlocfilehash: 4fe99e12c5d2dfb725e1e4aa0ac2fb0b1ccb4f28
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219891"
---
# <a name="compiler-warning-level-4-c4571"></a>Derleyici Uyarısı (düzey 4) C4571

Bilgi: catch (...) semantiği Visual C++ 7,1 ' den sonra değişti; yapılandırılmış özel durumlar (SEH) artık yakalanmıyor

C4571, **/EHS**ile derlerken her catch (...) bloğu için oluşturulur.

**/EHS**ile derlerken, bir catch (...) bloğu yapılandırılmış bir özel durumu yakalayamaz (örneğin sıfıra bölme, null işaretçi); catch (...) bloğu yalnızca açıkça oluşturulan, C++ özel durumlarını yakalar.  Daha fazla bilgi için bkz. [özel durum işleme](../../cpp/exception-handling-in-visual-cpp.md).

Bu uyarı varsayılan olarak kapalıdır.  **/EHS** ile derleme yaparken, catch (...) bloklarınızın yapılandırılmış özel durumları yakalamayın emin olmak için bu uyarıyı açın.  Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Aşağıdaki yollarla C4571 ' yi çözebilirsiniz,

- Hala catch (...) bloklarınızın yapılandırılmış özel durumları yakalayabilmek istiyorsanız **/EHa** ile derleyin.

- Catch (...) bloklarınızın yapılandırılmış özel durumları yakalemelerini istemiyorsanız, ancak yine de catch (...) blokları kullanmak istiyorsanız C4571 ' ı etkinleştirmeyin.  Yapılandırılmış özel durum işleme anahtar sözcüklerini (**__try**, **`__except`** , ve) kullanarak yine de yapılandırılmış özel durumları yakalayabilirsiniz **`__finally`** .  Ancak, bir SEH özel durumu oluştuğunda değil, derlenmiş **/EHS** yıkıcıları yalnızca C++ özel durumu oluşturulduğunda çağrılacaktır.

- Catch (...) bloğunu belirli C++ özel durumları için catch bloklarıyla değiştirin ve isteğe bağlı olarak, C++ özel durum işleme (**__try**, ve) çevresine yapılandırılmış özel durum işleme ekleyin **`__except`** **`__finally`** .  Daha fazla bilgi için bkz. [yapılandırılmış özel durum işleme (C/C++)](../../cpp/structured-exception-handling-c-cpp.md) .

Daha fazla bilgi için bkz. [/Eh (özel durum Işleme modeli)](../../build/reference/eh-exception-handling-model.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C4571 oluşturur.

```cpp
// C4571.cpp
// compile with: /EHs /W4 /c
#pragma warning(default : 4571)
int main() {
   try {
      int i = 0, j = 1;
      j /= i;   // this will throw a SE (divide by zero)
   }
   catch(...) {}   // C4571 warning
}
```
