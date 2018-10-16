---
title: Yeni başvuru, gcnew (C + +/ CLI ve C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- gcnew
- ref new
- gcnew_cpp
dev_langs:
- C++
helpviewer_keywords:
- ref new keyword (C++)
- gcnew keyword [C++]
ms.assetid: 388a62da-c2df-4a94-a9a2-205b53e577da
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f5a10278957e6a89b52e744f8f0dd78b475f7730
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2018
ms.locfileid: "49328317"
---
# <a name="ref-new-gcnew--ccli-and-ccx"></a>Yeni başvuru, gcnew (C + +/ CLI ve C + +/ CX)

**Yeni başvuru** toplama anahtar sözcüğü ayırır nesne erişilemez duruma gelir ve bir tanıtıcı döndürür atık bir türün örneğini ([^](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)) ayrılmış nesneyi.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

Tarafından ayrılan bir türün bir örneği için bellek **yeni başvuru** otomatik olarak serbest bırakılır.

A **yeni başvuru** işlemi oluşturur `OutOfMemoryException` bellek ayıramıyor ise.

Yerel C++ türler için bellek tahsis ve serbest hakkında daha fazla bilgi için bkz. [yeni ve delete işleçleri](../cpp/new-and-delete-operators.md).

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

Kullanım **yeni başvuru** ömrü otomatik olarak yönetmek istediğiniz Windows çalışma zamanı nesneler için bellek ayrılamadı. Nesne, başvuru sayısı başvuru son kopyasını kapsam dışına geçti sonra oluşan sıfıra gittiğinde otomatik olarak serbest bırakıldı. Daha fazla bilgi için [başvuru sınıfları ve yapıları](../cppcx/ref-classes-and-structs-c-cx.md).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

Tarafından yönetilen bir türe (başvuru veya değer türü) için bellek ayrıldığını **gcnew**ve çöp toplama kullanarak serbest bırakıldı.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki örnekte **gcnew** ileti nesne ayrılamadı.

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

Aşağıdaki örnekte **gcnew** gibi bir başvuru türü kullanmak için bir kutulanmış değer türü oluşturmak için.

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

## <a name="see-also"></a>Ayrıca Bkz.

[.NET ve UWP için bileşen uzantıları](../windows/component-extensions-for-runtime-platforms.md)