---
title: 'Nasıl yapılır: Sabitleme İşaretçileri ve Değer Türlerini Bildirme'
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- value types, declaring
- pinning pointers
ms.assetid: 57c5ec8a-f85a-48c4-ba8b-a81268bcede0
ms.openlocfilehash: 88ef7e82161703a272a571392fd66e6055371c61
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181973"
---
# <a name="how-to-declare-pinning-pointers-and-value-types"></a>Nasıl yapılır: Sabitleme İşaretçileri ve Değer Türlerini Bildirme

Değer türü örtük olarak kutulanabilir. Daha sonra değer türü nesnesine sabitleme işaretçisi bildirebilir ve kutulanmış değer türünde bir **pin_ptr** kullanabilirsiniz.

## <a name="example"></a>Örnek

### <a name="code"></a>Kod

```cpp
// pin_ptr_value.cpp
// compile with: /clr
value struct V {
   int i;
};

int main() {
   V ^ v = gcnew V;   // imnplicit boxing
   v->i=8;
   System::Console::WriteLine(v->i);
   pin_ptr<V> mv = &*v;
   mv->i = 7;
   System::Console::WriteLine(v->i);
   System::Console::WriteLine(mv->i);
}
```

```Output
8
7
7
```

## <a name="see-also"></a>Ayrıca bkz.

[pin_ptr (C++/CLI)](pin-ptr-cpp-cli.md)
