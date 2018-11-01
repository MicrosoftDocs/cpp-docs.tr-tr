---
title: 'Nasıl yapılır: İç İşaretçiler ve Yönetilen Diziler Bildirme ve Kullanma (C++/CLI)'
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- pointers, interior
- arrays [C++], managed
ms.assetid: e61a2c09-a7d0-4867-91ea-6b8788a01079
ms.openlocfilehash: 98f198812654706792ea18024bb8654803d27970
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598269"
---
# <a name="how-to-declare-and-use-interior-pointers-and-managed-arrays-ccli"></a>Nasıl yapılır: İç İşaretçiler ve Yönetilen Diziler Bildirme ve Kullanma (C++/CLI)

Aşağıdaki C + +/ CLI örneği bildirme ve bir dizi iç işaretçiye kullanmak nasıl gösterir.

> [!IMPORTANT]
> Bu dil özelliği tarafından desteklenen `/clr` derleyici seçeneği, ancak tarafından `/ZW` derleyici seçeneği.

## <a name="example"></a>Örnek

### <a name="code"></a>Kod

```cpp
// interior_ptr_arrays.cpp
// compile with: /clr
#define SIZE 10

int main() {
   // declare the array
   array<int>^ arr = gcnew array<int>(SIZE);

   // initialize the array
   for (int i = 0 ; i < SIZE ; i++)
      arr[i] = i + 1;

   // create an interior pointer into the array
   interior_ptr<int> ipi = &arr[0];

   System::Console::WriteLine("1st element in arr holds: {0}", arr[0]);
   System::Console::WriteLine("ipi points to memory address whose value is: {0}", *ipi);

   ipi++;
   System::Console::WriteLine("after incrementing ipi, it points to memory address whose value is: {0}", *ipi);
}
```

```Output
1st element in arr holds: 1
ipi points to memory address whose value is: 1
after incrementing ipi, it points to memory address whose value is: 2
```

## <a name="see-also"></a>Ayrıca Bkz.

[interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)