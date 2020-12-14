---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: C++/CLı üzerinde numaralandırmaları tanımlama ve kullanma'
title: 'Nasıl yapılır: C++/CLI üzerinde sabit listelerini tanımlama ve kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- enum class, specifying underlying types
ms.assetid: df8f2b91-b9d2-4fab-9be4-b1d58b8bc570
ms.openlocfilehash: 26b3c886ca34235f0567fc0f8e9d7df6bfe46814
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258349"
---
# <a name="how-to-define-and-consume-enums-in-ccli"></a>Nasıl yapılır: C++/CLI üzerinde sabit listelerini tanımlama ve kullanma

Bu konuda, C++/CLI'TEKI numaralandırmalar açıklanmaktadır.

## <a name="specifying-the-underlying-type-of-an-enum"></a>Bir sabit listesinin temel alınan türünü belirtme

Varsayılan olarak, bir numaralandırmanın temel alınan türü **`int`** .  Ancak,,,, veya imzasız biçimleri için türü belirtebilirsiniz **`int`** **`short`** **`long`** **`__int32`** **`__int64`** .  ' İ de kullanabilirsiniz **`char`** .

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

**Çıktı**

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

**Çıktı**

```Output
a and day2 are the same
```

## <a name="operators-and-enums"></a>İşleçler ve numaralandırmalar

Aşağıdaki işleçler C++/CLı ' daki Numaralandırmalar için geçerlidir:

|Operatör|
|--------------|
|== != \< >\<= >=|
|+ -|
|&#124; ^ & ~|
|++ --|
|sizeof|

İşleci &#124; ^ & ~ + +--yalnızca integral tabanlı türler içeren Numaralandırmalar için tanımlanır, bool dahil değildir.  Her iki işlenen de sabit listesi türünde olmalıdır.

Derleyici, bir numaralandırma işleminin sonucunun statik veya dinamik bir denetimini yapmaz; bir işlem, numaralandırmanın geçerli numaralandırıcıların aralığında bulunmayan bir değere neden olabilir.

> [!NOTE]
> C++ 11, C++/cliende yönetilen enum sınıflarından önemli ölçüde farklı olan yönetilmeyen koddaki enum sınıf türlerini tanıtır. Özellikle, C++ 11 sabit listesi sınıf türü, C++/CLı ' da yönetilen sabit listesi sınıfı türü ile aynı işleçleri desteklemez ve C++/CLı kaynak kodu, yönetilmeyen (C++ 11) sabit listesi sınıfı bildirimlerinden ayırt edilebilmesi için yönetilen enum sınıfı bildirimlerinde bir erişilebilirlik belirticisi sağlamalıdır. C++/CLı, C++/CX ve C++ 11 ' deki numaralandırma sınıfları hakkında daha fazla bilgi için bkz. [enum class](../extensions/enum-class-cpp-component-extensions.md).

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

**Çıktı**

```Output
4
1
True
```

## <a name="see-also"></a>Ayrıca bkz.

[sabit listesi sınıfı](../extensions/enum-class-cpp-component-extensions.md)
