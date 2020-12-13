---
description: 'Daha fazla bilgi edinin: ref New, gcnew (C++/CLı ve C++/CX)'
title: ref new, gcnew (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- gcnew
- ref new
- gcnew_cpp
helpviewer_keywords:
- ref new keyword (C++)
- gcnew keyword [C++]
ms.assetid: 388a62da-c2df-4a94-a9a2-205b53e577da
ms.openlocfilehash: bfe93d9d3966f8796c0fc0ab2cdf7b80115b3d33
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341067"
---
# <a name="ref-new-gcnew--ccli-and-ccx"></a>ref new, gcnew (C++/CLI ve C++/CX)

**Ref New** Aggregate anahtar sözcüğü, nesne erişilemez hale geldiğinde ve ayrılan nesneye bir tanıtıcı () döndüren atık olarak toplanan bir türün bir örneğini ayırır [^](handle-to-object-operator-hat-cpp-component-extensions.md) .

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

**Ref New** tarafından ayrılan bir türün örneği için bellek otomatik olarak serbest bırakılır.

Bir **başvuru yeni** bir işlem `OutOfMemoryException` , bellek ayıramadığında atar.

Yerel C++ türleri için bellek ayırma ve serbest bırakma hakkında daha fazla bilgi için, bkz. [New ve delete işleçleri](../cpp/new-and-delete-operators.md).

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

Yaşam sürelerini otomatik olarak yönetmek istediğiniz Windows Çalışma Zamanı nesneler için bellek ayırmak üzere **Yeni başvuru** kullanın. Başvuru sayısı sıfır olduğunda nesne otomatik olarak serbest bırakılır. Bu, başvurunun son kopyası kapsam dışına çıktığında oluşur. Daha fazla bilgi için bkz. [başvuru sınıfları ve yapıları](../cppcx/ref-classes-and-structs-c-cx.md).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

Yönetilen bir tür için bellek (başvuru veya değer türü), **gcnew** tarafından ayrılır ve çöp toplama kullanılarak serbest bırakılır.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki örnek, bir Ileti nesnesi ayırmak için **gcnew** kullanır.

```cpp
// mcppv2_gcnew_1.cpp
// compile with: /clr
ref struct Message {
   System::String^ sender;
   System::String^ receiver;
   System::String^ data;
};

int main() {
   Message^ h_Message  = gcnew Message;
  //...
}
```

Aşağıdaki örnek, bir başvuru türü gibi kullanım için paketlenmiş bir değer türü oluşturmak için **gcnew** kullanır.

```cpp
// example2.cpp : main project file.
// compile with /clr
using namespace System;
value class Boxed {
    public:
        int i;
};
int main()
{
    Boxed^ y = gcnew Boxed;
    y->i = 32;
    Console::WriteLine(y->i);
    return 0;
}
```

```Output
32
```

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP için bileşen uzantıları](component-extensions-for-runtime-platforms.md)
