---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: interior_ptr anahtar sözcüğü ile değer türleri bildirme (C++/CLı)'
title: 'Nasıl yapılır: interior_ptr Anahtar Sözcüğü ile Değer Türleri Bildirme (C++/CLI)'
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- _ptr keyword
- value types, declaring
ms.assetid: 49eea66e-eeba-49bd-95b0-ba297be436e3
ms.openlocfilehash: b8d5c554f212a9536b0ad063d67e044c08194015
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119180"
---
# <a name="how-to-declare-value-types-with-the-interior_ptr-keyword-ccli"></a>Nasıl yapılır: interior_ptr Anahtar Sözcüğü ile Değer Türleri Bildirme (C++/CLI)

Bir **interior_ptr** , bir değer türü ile kullanılabilir.

> [!IMPORTANT]
> Bu dil özelliği derleyici seçeneği tarafından desteklenir `/clr` , ancak `/ZW` derleyici seçeneği tarafından desteklenmez.

## <a name="example-interior_ptr-with-value-type"></a>Örnek: değer türü ile interior_ptr

### <a name="description"></a>Açıklama

Aşağıdaki C++/CLı örneği, bir **interior_ptr** değer türüyle nasıl kullanacağınızı gösterir.

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

## <a name="example-this-pointer"></a>Örnek: Bu işaretçi

### <a name="description"></a>Açıklama

Değer türünde, **`this`** işaretçi bir interior_ptr değerlendirir.

Bir değer türünün statik olmayan bir üye işlevinin gövdesinde `V` **`this`** değeri, `interior_ptr<V>` işlevin çağrıldığı nesnenin adresi olan türü bir ifadedir.

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

## <a name="example-address-of-operator"></a>Örnek: Address-of işleci

### <a name="description"></a>Açıklama

Aşağıdaki örnek, statik üyelerle adres işlecinin nasıl kullanılacağını göstermektedir.

Statik bir Visual C++ türü üyesinin adresi yerel bir işaretçi verir.  Değer türü üyesi çalışma zamanı yığınına ayrıldığından ve çöp toplayıcı tarafından taşınabildiğinden, statik değer türü üyesinin adresi yönetilen bir işaretçidir.

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

## <a name="see-also"></a>Ayrıca bkz.

[interior_ptr (C++/CLI)](interior-ptr-cpp-cli.md)
