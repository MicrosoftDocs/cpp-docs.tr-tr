---
title: finally
ms.date: 11/04/2016
helpviewer_keywords:
- finally keyword [C++]
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
ms.openlocfilehash: 2574ba5a10bbf5eddc68d6e0265d5dfc99c6d8fc
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988338"
---
# <a name="finally"></a>finally

`try` ve `catch` yan tümcelerinin yanı sıra, CLR özel durum işleme bir `finally` yan tümcesini destekler. Sözdizimi, yapılandırılmış özel durum işleme (SEH) içindeki `__finally` bloğunun aynısıdır. `__finally` bloğu, bir `try` veya `catch` bloğunu izleyebilir.

## <a name="remarks"></a>Açıklamalar

`finally` bloğunun amacı, özel durum oluşduktan sonra kalan kaynakları temizleyelim. Hiçbir özel durum atılmasa bile `finally` bloğunun her zaman yürütüldüğünü unutmayın. `catch` bloğu yalnızca, ilişkili `try` bloğunda yönetilen bir özel durum oluşturulursa yürütülür.

`finally`, bağlama duyarlı bir anahtar sözcüktür; daha fazla bilgi için bkz. [bağlama duyarlı anahtar sözcükler](../extensions/context-sensitive-keywords-cpp-component-extensions.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek, basit bir `finally` bloğunu göstermektedir:

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
