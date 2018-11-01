---
title: Derleyici Uyarısı (düzey 4) C4571
ms.date: 11/04/2016
f1_keywords:
- C4571
helpviewer_keywords:
- C4571
ms.assetid: 07aa17bd-b15c-4266-824c-57cc445e8edd
ms.openlocfilehash: 92164bf297a44871897b6c6150eb54f8c5ccf3cc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431063"
---
# <a name="compiler-warning-level-4-c4571"></a>Derleyici Uyarısı (düzey 4) C4571

Bilgi amaçlı: Visual C++ 7.1 sürümünden sonra değişti catch(...) semantiği; yapılandırılmış özel durumlar (SEH) artık yakalanmıyor

İle derlerken C4571 her gt;catch(...) bloğu için oluşturulan **EHS**.

İle derlerken **EHS**, gt;catch(...) blok yakalamaz yapılandırılmış özel durum (null bir işaretçiyse, örneğin sıfır ile bölme); açıkça oluşturulan bir gt;catch(...) blok olacak yalnızca catch, C++ özel durumlarını.  Daha fazla bilgi için [özel durum işleme](../../cpp/exception-handling-in-visual-cpp.md).

Varsayılan olarak bu uyarıyı kapalıdır.  Bu ile derleme yaparken emin olmak için uyarısını Kapat **EHS** yapılandırılmış özel durumları yakalamak, (...) catch blokları düşünmüyorsunuz.  Bkz: [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.

Aşağıdaki yollardan biriyle C4571 çözümleyebilir,

- Derleme **/eha** yapılandırılmış özel durumları yakalamak için gt;catch(...) blokları hala istiyorsanız.

- Yapılandırılmış özel durumları yakalamak için gt;catch(...) blokları istemiyorsanız, ancak yine de gt;catch(...) blokları kullanmak istediğiniz C4571 etkinleştirmeyin.  Yine de yapılandırılmış özel durum işleme anahtar sözcükleri kullanarak yapılandırılmış özel durumları yakalayabilir (**__try**, **__except**, ve **__finally**).  Ancak, derlendiğinde unutmayın **EHS** yok ediciler, yalnızca değil bir SEH özel durumu oluştuğunda C++ özel durum oluştuğunda çağrılır.

- Catch blokları için belirli C++ özel durumlarını gt;catch(...) blok değiştirin ve isteğe bağlı olarak, yapılandırılmış özel durum işlemeyi C++ özel durum işlemeyi geçici olarak ekleyin (**__try**, **__except**, ve **_ _finally**).  Bkz: [yapılandırılmış özel durum işleme (C/C++)](../../cpp/structured-exception-handling-c-cpp.md) daha fazla bilgi için.

Bkz: [/EH (özel durum işleme modeli)](../../build/reference/eh-exception-handling-model.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4571 oluşturur.

```
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