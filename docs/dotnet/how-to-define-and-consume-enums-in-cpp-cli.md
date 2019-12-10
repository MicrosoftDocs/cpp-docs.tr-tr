---
title: 'Nasıl yapılır: C++/CLI üzerinde numaralandırmaları tanımlama ve kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- enum class, specifying underlying types
ms.assetid: df8f2b91-b9d2-4fab-9be4-b1d58b8bc570
ms.openlocfilehash: 68f8e113f6199d3b320bc6d241ee3396d2b70a1a
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988225"
---
# <a name="how-to-define-and-consume-enums-in-ccli"></a>Nasıl yapılır: C++/CLI üzerinde numaralandırmaları tanımlama ve kullanma

Bu konu başlığı altında, C++/cli'teki numaralandırmalar açıklanmaktadır.

## <a name="specifying-the-underlying-type-of-an-enum"></a>Bir sabit listesinin temel alınan türünü belirtme

Varsayılan olarak, bir numaralandırmanın temel alınan türü `int`.  Ancak, `int`, `short`, `long`, `__int32`veya `__int64`imzalı veya imzasız biçimleri için türü belirtebilirsiniz.  `char`de kullanabilirsiniz.

```cpp
// mcppv2_enum_3.cpp
// compile with: /clr
public enum class day_char : char {sun, mon, tue, wed, thu, fri, sat};

int main() {
   // fully qualified names, enumerator not injected into scope
   day_char d = day_char::sun, e = day_char::mon;
   System::Console::WriteLine(d);
   char f = (char)d;
   System::Console::WriteLine(f);
   f = (char)e;
   System::Console::WriteLine(f);
   e = day_char::tue;
   f = (char)e;
   System::Console::WriteLine(f);
}
```

**Output**

```Output
sun
0
1
2
```

## <a name="how-to-convert-between-managed-and-standard-enumerations"></a>Yönetilen ve standart numaralandırmalar arasında dönüştürme

Enum ve integral türü arasında standart dönüştürme yoktur; bir atama gereklidir.

```cpp
// mcppv2_enum_4.cpp
// compile with: /clr
enum class day {sun, mon, tue, wed, thu, fri, sat};
enum {sun, mon, tue, wed, thu, fri, sat} day2; // unnamed std enum

int main() {
   day a = day::sun;
   day2 = sun;
   if ((int)a == day2)
   // or...
   // if (a == (day)day2)
      System::Console::WriteLine("a and day2 are the same");
   else
      System::Console::WriteLine("a and day2 are not the same");
}
```

**Output**

```Output
a and day2 are the same
```

## <a name="operators-and-enums"></a>İşleçler ve numaralandırmalar

Aşağıdaki işleçler/CLI içindeki C++Numaralandırmalar için geçerlidir:

|İşleç|
|--------------|
|== != \< > \<= >=|
|+ -|
|&#124; ^ & ~|
|++ --|
|sizeof|

^ &#124; & ~ + +--İşleçleri, bool dahil değil yalnızca integral tabanlı türler içeren Numaralandırmalar için tanımlanmıştır.  Her iki işlenen de sabit listesi türünde olmalıdır.

Derleyici, bir numaralandırma işleminin sonucunun statik veya dinamik bir denetimini yapmaz; bir işlem, numaralandırmanın geçerli numaralandırıcıların aralığında bulunmayan bir değere neden olabilir.

> [!NOTE]
>  C++ 11,/Clide C++yönetilen enum sınıflarından önemli ölçüde farklı olan yönetilmeyen koddaki enum sınıf türlerini tanıtır. Özellikle, C++ 11 sabit listesi sınıf türü,/CLI içindeki C++yönetilen numaralandırma sınıfı türü ile aynı işleçleri desteklemez ve C++/CLI kaynak kodu, yönetilmeyen (c++ 11) sabit listesi sınıfı bildirimlerinden ayırt edilebilmesi için yönetilen enum sınıfı bildirimlerinde bir erişilebilirlik belirticisi sağlamalıdır. /CLI, C++/CX ve c++ 11 ' C++deki numaralandırma sınıfları hakkında daha fazla bilgi için bkz. [enum class](../extensions/enum-class-cpp-component-extensions.md).

```cpp
// mcppv2_enum_5.cpp
// compile with: /clr
private enum class E { a, b } e, mask;
int main() {
   if ( e & mask )   // C2451 no E->bool conversion
      ;

   if ( ( e & mask ) != 0 )   // C3063 no operator!= (E, int)
      ;

   if ( ( e & mask ) != E() )   // OK
      ;
}
```

```cpp
// mcppv2_enum_6.cpp
// compile with: /clr
private enum class day : int {sun, mon};
enum : bool {sun = true, mon = false} day2;

int main() {
   day a = day::sun, b = day::mon;
   day2 = sun;

   System::Console::WriteLine(sizeof(a));
   System::Console::WriteLine(sizeof(day2));
   a++;
   System::Console::WriteLine(a == b);
}
```

**Output**

```Output
4
1
True
```

## <a name="see-also"></a>Ayrıca bkz.

[sabit listesi sınıfı](../extensions/enum-class-cpp-component-extensions.md)
