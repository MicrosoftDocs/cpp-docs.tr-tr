---
title: 'Nasıl yapılır: interior_ptr Anahtar Sözcüğü ile Değer Türleri Bildirme (C++/CLI)'
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- _ptr keyword
- value types, declaring
ms.assetid: 49eea66e-eeba-49bd-95b0-ba297be436e3
ms.openlocfilehash: 22c0fe4424e4df81ebb0355dfac2168af725b971
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80172288"
---
# <a name="how-to-declare-value-types-with-the-interior_ptr-keyword-ccli"></a>Nasıl yapılır: interior_ptr Anahtar Sözcüğü ile Değer Türleri Bildirme (C++/CLI)

Bir **interior_ptr** , bir değer türü ile kullanılabilir.

> [!IMPORTANT]
> Bu dil özelliği `/clr` derleyici seçeneği tarafından desteklenir, ancak `/ZW` derleyici seçeneği tarafından desteklenmez.

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki C++/CLI örneği, bir **interior_ptr** değer türüyle nasıl kullanacağınızı gösterir.

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

Değer türünde, **Bu** işaretçi bir interior_ptr değerlendirir.

Değer türü `V`statik olmayan bir üye işlevi gövdesinde, **Bu** , değeri işlevin çağrıldığı nesnenin adresi olan `interior_ptr<V>` türünde bir ifadedir.

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

Aşağıdaki örnek, statik üyelerle adres işlecinin nasıl kullanılacağını göstermektedir.

Statik görsel C++ türü üyesinin adresi yerel bir işaretçi verir.  Değer türü üyesi çalışma zamanı yığınına ayrıldığından ve çöp toplayıcı tarafından taşınabildiğinden, statik değer türü üyesinin adresi yönetilen bir işaretçidir.

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
