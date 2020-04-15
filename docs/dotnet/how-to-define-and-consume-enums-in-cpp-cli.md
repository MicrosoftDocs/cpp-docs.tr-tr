---
title: 'Nasıl yapılır: C++/CLI üzerinde numaralandırmaları tanımlama ve kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- enum class, specifying underlying types
ms.assetid: df8f2b91-b9d2-4fab-9be4-b1d58b8bc570
ms.openlocfilehash: cf3bb23069b2692c0ca4ce270a5b8060195becf7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370169"
---
# <a name="how-to-define-and-consume-enums-in-ccli"></a>Nasıl yapılır: C++/CLI üzerinde numaralandırmaları tanımlama ve kullanma

Bu konu C++/CLI'deki enumları tartışır.

## <a name="specifying-the-underlying-type-of-an-enum"></a>Bir enumun temel türünü belirtme

Varsayılan olarak, bir numaralandırma nın altında `int`yatan tür .  Ancak, imzalanacak veya imzalanmamış formlar , `int` `short`, `long` `__int32`, `__int64`veya .  Ayrıca kullanabilirsiniz. `char`

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

## <a name="how-to-convert-between-managed-and-standard-enumerations"></a>Yönetilen ve standart sayısallaştırmalar arasında dönüştürme

Bir enum ve integral türü arasında standart bir dönüşüm yoktur; bir döküm gereklidir.

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

## <a name="operators-and-enums"></a>Operatörler ve enumlar

Aşağıdaki işleçler C++/CLI'deki enumlarda geçerlidir:

|İşleç|
|--------------|
|== != \<  >  \<= >=|
|+ -|
|&#124; ^ & ~|
|++ --|
|sizeof|

^ & ~ ++ &#124; işleçler, bool hariç, yalnızca integral altta yatan türlere sahip sayısallamalar için tanımlanır.  Her iki operands numaralandırma türünde olmalıdır.

Derleyici, enum işleminin sonucunu statik veya dinamik olarak denetlemez; bir işlem, enum'un geçerli tümumcularının aralığında olmayan bir değere neden olabilir.

> [!NOTE]
> C++11, C++/CLI'deki yönetilen enum sınıflarından önemli ölçüde farklı olan enum sınıf türlerini yönetilmeyen kodda tanıtır. Özellikle, C++11 enum sınıfı türü, C++/CLI'deki yönetilen enum sınıfı türüyle aynı işleçleri desteklemez ve C++/CLI kaynak kodu, yönetilen enum sınıf bildirimlerinde yönetilmeyen (C++11) enum sınıfı bildirimlerinden ayırt etmek için erişilebilirlik belirteçleri sağlamalıdır. C++/CLI, C++/CX ve C++11'deki enum sınıfları hakkında daha fazla bilgi için [enum sınıfına](../extensions/enum-class-cpp-component-extensions.md)bakın.

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
