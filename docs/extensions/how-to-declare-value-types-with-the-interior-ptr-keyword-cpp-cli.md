---
title: 'Nasıl yapılır: İnterior_ptr anahtar sözcüğü ile değer türleri bildirme (C + +/ CLI)'
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- _ptr keyword
- value types, declaring
ms.assetid: 49eea66e-eeba-49bd-95b0-ba297be436e3
ms.openlocfilehash: 45a268ce4ff062205accb65de1baa98a218310a7
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787071"
---
# <a name="how-to-declare-value-types-with-the-interiorptr-keyword-ccli"></a>Nasıl yapılır: İnterior_ptr anahtar sözcüğü ile değer türleri bildirme (C + +/ CLI)

Bir **interior_ptr** bir değer türü ile kullanılabilir.

> [!IMPORTANT]
> Bu dil özelliği tarafından desteklenen `/clr` derleyici seçeneği, ancak tarafından `/ZW` derleyici seçeneği.

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki C + +/ CLI örnek nasıl kullanılacağını gösteren bir **interior_ptr anahtar** bir değer türü.

### <a name="code"></a>Kod

```cpp
// interior_ptr_value_types.cpp
// compile with: /clr
value struct V {
   V(int i) : data(i){}
   int data;
};

int main() {
   V v(1);
   System::Console::WriteLine(v.data);

   // pointing to a value type
   interior_ptr<V> pv = &v;
   pv->data = 2;

   System::Console::WriteLine(v.data);
   System::Console::WriteLine(pv->data);

   // pointing into a value type
   interior_ptr<int> pi = &v.data;
   *pi = 3;
   System::Console::WriteLine(*pi);
   System::Console::WriteLine(v.data);
   System::Console::WriteLine(pv->data);
}
```

```Output
1
2
2
3
3
3
```

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Bir değer türünde **bu** işaretçi interior_ptr için değerlendirir.

Statik olmayan üye işlevi bir değer türü gövdesinde `V`, **bu** türündeki bir ifade `interior_ptr<V>` değeri işlevin çağrıldığı nesneye adresidir.

### <a name="code"></a>Kod

```cpp
// interior_ptr_value_types_this.cpp
// compile with: /clr /LD
value struct V {
   int data;
   void f() {
      interior_ptr<V> pv1 = this;
      // V* pv2 = this;   error
   }
};
```

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki örnek, statik üyelerle address-of işlecini kullanmayı gösterir.

Yerel bir işaretçi bir statik Visual C++ tür üyesinin adresini verir.  Değer türü üyesine çalışma zamanı yığınına ayrılmış ve çöp toplayıcısı tarafından taşınabilir olduğundan statik değer türü üyesine adresi yönetilen bir işaretçisidir.

### <a name="code"></a>Kod

```cpp
// interior_ptr_value_static.cpp
// compile with: /clr
using namespace System;
value struct V { int i; };

ref struct G {
   static V v = {22};
   static int i = 23;
   static String^ pS = "hello";
};

int main() {
   interior_ptr<int> p1 = &G::v.i;
   Console::WriteLine(*p1);

   interior_ptr<int> p2 = &G::i;
   Console::WriteLine(*p2);

   interior_ptr<String^> p3 = &G::pS;
   Console::WriteLine(*p3);
}
```

```Output
22
23
hello
```

## <a name="see-also"></a>Ayrıca Bkz.

[interior_ptr (C++/CLI)](interior-ptr-cpp-cli.md)