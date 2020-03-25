---
title: Yeni başvuru, gcnew (C++/CLI ve C++/CX)
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
ms.openlocfilehash: f7269a62d7899df4eb89f6dd9487310c0fda0b4d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181817"
---
# <a name="ref-new-gcnew--ccli-and-ccx"></a>Yeni başvuru, gcnew (C++/CLI ve C++/CX)

**Ref New** Aggregate anahtar sözcüğü, nesnenin erişilemez hale geldiği ve ayrılan nesneye bir tanıtıcı ([^](handle-to-object-operator-hat-cpp-component-extensions.md)) döndüren bir türün bir örneğini ayırır.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

**Ref New** tarafından ayrılan bir türün örneği için bellek otomatik olarak serbest bırakılır.

Bir **başvuru yeni** işlem, bellek ayıramadığında `OutOfMemoryException` oluşturur.

Yerel C++ türlerin belleğinin nasıl ayrıldığı ve serbest bırakıldığı hakkında daha fazla bilgi için, bkz. [New ve delete işleçleri](../cpp/new-and-delete-operators.md).

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

Yaşam sürelerini otomatik olarak yönetmek istediğiniz Windows Çalışma Zamanı nesneler için bellek ayırmak üzere **Yeni başvuru** kullanın. Başvuru sayısı sıfır olduğunda nesne otomatik olarak serbest bırakılır. Bu, başvurunun son kopyası kapsam dışına çıktığında oluşur. Daha fazla bilgi için bkz. [başvuru sınıfları ve yapıları](../cppcx/ref-classes-and-structs-c-cx.md).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

Yönetilen bir tür için bellek (başvuru veya değer türü), **gcnew**tarafından ayrılır ve çöp toplama kullanılarak serbest bırakılır.

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

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)
