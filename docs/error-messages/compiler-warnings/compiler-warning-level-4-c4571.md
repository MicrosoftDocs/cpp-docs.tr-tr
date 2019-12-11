---
title: Derleyici Uyarısı (düzey 4) C4571
ms.date: 11/04/2016
f1_keywords:
- C4571
helpviewer_keywords:
- C4571
ms.assetid: 07aa17bd-b15c-4266-824c-57cc445e8edd
ms.openlocfilehash: 3a8f2093e90f8a681d171e19e2b8a066546f8684
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990665"
---
# <a name="compiler-warning-level-4-c4571"></a>Derleyici Uyarısı (düzey 4) C4571

Bilgilendirici: catch (...) semantiği, Visual C++ 7,1 sonrasında değişti; yapılandırılmış özel durumlar (SEH) artık yakalanmıyor

C4571, **/EHS**ile derlerken her catch (...) bloğu için oluşturulur.

**/EHS**ile derlerken, bir catch (...) bloğu yapılandırılmış bir özel durumu yakalayamaz (örneğin sıfıra bölme, null işaretçi); catch (...) bloğu yalnızca açıkça oluşturulan C++ özel durumları yakalar.  Daha fazla bilgi için bkz. [özel durum işleme](../../cpp/exception-handling-in-visual-cpp.md).

Bu uyarı varsayılan olarak kapalıdır.  **/EHS** ile derleme yaparken, catch (...) bloklarınızın yapılandırılmış özel durumları yakalamayın emin olmak için bu uyarıyı açın.  Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Aşağıdaki yollarla C4571 ' yi çözebilirsiniz,

- Hala catch (...) bloklarınızın yapılandırılmış özel durumları yakalayabilmek istiyorsanız **/EHa** ile derleyin.

- Catch (...) bloklarınızın yapılandırılmış özel durumları yakalemelerini istemiyorsanız, ancak yine de catch (...) blokları kullanmak istiyorsanız C4571 ' ı etkinleştirmeyin.  Yapılandırılmış özel durumları, yapılandırılmış özel durum işleme anahtar sözcüklerini ( **__try**, **__except**ve **__finally**) kullanarak yine de yakalayabilirsiniz.  Ancak, bir SEH özel durumu oluştuğunda değil, derlenmiş **/EHS** yıkıcıları C++ yalnızca bir özel durum oluşturulduğunda çağrılacaktır.

- Catch (... C++ ) bloğunu belirli özel durumlar için catch bloklarıyla değiştirin ve isteğe bağlı olarak C++ özel durum işleme ( **__try**, **__except**ve **__finally**) yapısal özel durum işleme ekleyin.  Daha fazla bilgi için bkz. [yapılandırılmışC++özel durum işleme (C/)](../../cpp/structured-exception-handling-c-cpp.md) .

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
