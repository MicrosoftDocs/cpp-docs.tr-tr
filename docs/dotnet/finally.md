---
title: finally
ms.date: 11/04/2016
helpviewer_keywords:
- finally keyword [C++]
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
ms.openlocfilehash: f7db4320cf901412e3a9e3de682d0cfbcc9f23bc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223020"
---
# <a name="finally"></a>finally

Ek olarak `try` ve `catch` yan tümceleri, CLR özel durum işlemeyi destekleyen bir `finally` yan tümcesi. Semantiği özdeş `__finally` işleme (SEH) yapılandırılmış özel durum engelleyin. A `__finally` blok izleyebilirsiniz bir `try` veya `catch` blok.

## <a name="remarks"></a>Açıklamalar

Amacı `finally` bloğu özel durum oluştuktan sonra kalan tüm kaynakları temizlemek için. Unutmayın `finally` blok her zaman yürütülür, bile hiçbir özel durum oluştu. `catch` Yalnızca blokesi yönetilen bir özel durum oluşturulursa ilişkili içinde `try` blok.

`finally` bağlama duyarlı anahtar sözcük sınıflandırabilirsiniz. bkz: [Context-Sensitive Keywords](../extensions/context-sensitive-keywords-cpp-component-extensions.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, basit bir gösterir `finally` engelle:

```
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
