---
title: Derleyici Uyarısı (düzey 4) C4571
description: Microsoft C++ derleyicisi uyarı C4571 belgelerini belgeler.
ms.date: 08/24/2020
f1_keywords:
- C4571
helpviewer_keywords:
- C4571
ms.assetid: 07aa17bd-b15c-4266-824c-57cc445e8edd
ms.openlocfilehash: 35f2b30a8ab7cfcc27ed7aae3aedd9bc81efacc8
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898558"
---
# <a name="compiler-warning-level-4-c4571"></a>Derleyici Uyarısı (düzey 4) C4571

> Bilgilendirici: `catch(...)` Visual C++ 7,1 ' den bu yana sözdizimi değişti; yapılandırılmış özel durumlar (SEH) artık yakalanmıyor

`catch(...)`Derleyici seçeneğini belirttiğinizde her blok için C4571 oluşturulur **`/EHs`** .

## <a name="remarks"></a>Açıklamalar

**`/EHs`** Derleyici seçeneğini belirttiğinizde, `catch(...)` bloklar yapılandırılmış özel durumları yakalayamaz. (Örneğin, sıfıra bölme veya null işaretçi özel durumları.) Bir `catch(...)` blok yalnızca açıkça oluşturulan C++ özel durumlarını yakalar. Daha fazla bilgi için bkz. [özel durum işleme](../../cpp/exception-handling-in-visual-cpp.md).

Bu uyarı varsayılan olarak kapalıdır.  Bloklarınız ile derleme yaptığınızda **`/EHs`** `catch (...)` yapılandırılmış özel durumları yakalamayın emin olmak için bu uyarıyı açın. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

Aşağıdaki yollarla C4571 ' yi çözebilirsiniz:

- **`/EHa`** Hala `catch(...)` bloklarınızın yapılandırılmış özel durumları yakalenmesini istiyorsanız ile derleyin.

- `catch(...)`Bloklarınızın yapılandırılmış özel durumları yakalemelerini Istemiyorsanız C4571 etkinleştirmeyin, ancak hala blokları kullanmak istiyorsanız `catch(...)` .  Yapılandırılmış özel durum işleme anahtar sözcüklerini ( **`__try`** , **`__except`** , ve) kullanarak yine de yapılandırılmış özel durumları yakalayabilirsiniz **`__finally`** .  Ancak, kullanılarak derlendikten sonra, bir **`/EHs`** SEH özel durumu oluştuğunda değil, yalnızca C++ özel durumu oluşturulduğunda yok ediciler çağrılır.

- `catch(...)`Blokları belirli c++ özel durumları için catch bloklarıyla değiştirin ve isteğe bağlı olarak, C++ özel durum işleme ( **`__try`** , **`__except`** , ve) çevresine yapılandırılmış özel durum işleme ekleyin **`__finally`** .   daha fazla bilgi için bkz. [yapılandırılmış özel durum işleme (C/C++)](../../cpp/structured-exception-handling-c-cpp.md) ve [ `/EH` (özel durum işleme modeli)](../../build/reference/eh-exception-handling-model.md).

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
