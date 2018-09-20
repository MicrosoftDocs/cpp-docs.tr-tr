---
title: Son olarak | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- finally keyword [C++]
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 818ee6736d51303b047cb5a47aae02441557db29
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46447290"
---
# <a name="finally"></a>finally

Ek olarak `try` ve `catch` yan tümceleri, CLR özel durum işlemeyi destekleyen bir `finally` yan tümcesi. Semantiği özdeş `__finally` işleme (SEH) yapılandırılmış özel durum engelleyin. A `__finally` blok izleyebilirsiniz bir `try` veya `catch` blok.

## <a name="remarks"></a>Açıklamalar

Amacı `finally` bloğu özel durum oluştuktan sonra kalan tüm kaynakları temizlemek için. Unutmayın `finally` blok her zaman yürütülür, bile hiçbir özel durum oluştu. `catch` Yalnızca blokesi yönetilen bir özel durum oluşturulursa ilişkili içinde `try` blok.

`finally` bağlama duyarlı anahtar sözcük sınıflandırabilirsiniz. bkz: [Context-Sensitive Keywords](../windows/context-sensitive-keywords-cpp-component-extensions.md) daha fazla bilgi için.

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

## <a name="see-also"></a>Ayrıca Bkz.

[Özel Durum İşleme](../windows/exception-handling-cpp-component-extensions.md)