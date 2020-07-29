---
title: finally
ms.date: 11/04/2016
helpviewer_keywords:
- finally keyword [C++]
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
ms.openlocfilehash: b3331c17fc2313cbd6146db3beb015cd8d8c1eeb
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221464"
---
# <a name="finally"></a>finally

**`try`** Ve **`catch`** yan tümcelerinin yanı sıra CLR özel durum işleme bir **`finally`** yan tümceyi destekler. Anlambilim, **`__finally`** yapılandırılmış özel durum işleme (SEH) bloğu ile aynıdır. Bir **`__finally`** blok, **`try`** veya bloğunu izleyebilir **`catch`** .

## <a name="remarks"></a>Açıklamalar

Bloğun amacı, **`finally`** özel durum oluşduktan sonra kalan kaynakları temizleyelim. **`finally`** Hiçbir özel durum atılmasa bile bloğun her zaman yürütüldüğünü unutmayın. **`catch`** Blok yalnızca ilişkili blok içinde yönetilen bir özel durum oluşturulursa yürütülür **`try`** .

`finally`bağlama duyarlı bir anahtar sözcüktür; daha fazla bilgi için bkz. [bağlama duyarlı anahtar sözcükler](../extensions/context-sensitive-keywords-cpp-component-extensions.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnekte basit bir blok gösterilmektedir **`finally`** :

```cpp
// keyword__finally.cpp
// compile with: /clr
using namespace System;

ref class MyException: public System::Exception{};

void ThrowMyException() {
   throw gcnew MyException;
}

int main() {
   try {
      ThrowMyException();
   }
   catch ( MyException^ e ) {
      Console::WriteLine(  "in catch" );
      Console::WriteLine( e->GetType() );
   }
   finally {
      Console::WriteLine(  "in finally" );
   }
}
```

```Output
in catch
MyException
in finally
```

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](../extensions/exception-handling-cpp-component-extensions.md)
