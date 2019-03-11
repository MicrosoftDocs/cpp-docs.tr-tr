---
title: 'Nasıl yapılır: Tanımlama ve kullanma numaralandırmalar C + +/ CLI'
ms.date: 11/04/2016
helpviewer_keywords:
- enum class, specifying underlying types
ms.assetid: df8f2b91-b9d2-4fab-9be4-b1d58b8bc570
ms.openlocfilehash: 0252c4b64690f6a2fb0fd97b97841fe45fcce244
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57751459"
---
# <a name="how-to-define-and-consume-enums-in-ccli"></a>Nasıl yapılır: Tanımlama ve kullanma numaralandırmalar C + +/ CLI

Bu konuda ele alınmıştır numaralandırmalar C + +/ CLI.

## <a name="specifying-the-underlying-type-of-an-enum"></a>Bir sabit listesi türünü temel belirtme

Varsayılan olarak, temel alınan numaralandırma türünde `int`.  Ancak, imzalı veya imzasız biçimlerinin olmasını türünü belirtebilirsiniz `int`, `short`, `long`, `__int32`, veya `__int64`.  Ayrıca `char`.

```
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

Bir sabit listesi ve integral türünde arasında standart dönüştürme yok; bir tür dönüştürme gerekiyor.

```
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

Aşağıdaki işleçleri geçerli numaralandırmalar C + +/ CLI:

|İşleç|
|--------------|
|== != \< > \<= >=|
|+ -|
|&#124; ^ & ~|
|++ --|
|sizeof|

İşleçler &#124; ^ & ~ ++--temel türler, bool içermeden integral yalnızca sabit listeleri için tanımlanır.  Her iki işlenen de sabit listesi türünde olmalıdır.

Derleyici, hiçbir statik veya dinamik bir sabit listesi işlemin sonucu denetimi yapar; bir işlem değil geçerli sabit listesine numaralandırıcılar aralığında bir değer neden olabilir.

> [!NOTE]
>  C ++ 11, C + yönetilen enum sınıfları önemli ölçüde farklı enum sınıf türleri yönetilmeyen kodda tanıtır +/ CLI. Özellikle, C ++ 11 enum sınıfı türü yönetilen enum sınıfı türü olarak aynı işleçler C + desteklemiyor +/ CLI ve C + +/ CLI kaynak kodu sağlamalısınız bir yönetilen Numaralandırıcı erişilebilirlik belirticisini sınıf bildirimleri yönetilmeyen (C++'tan bunları ayırt etmek için 11) enum sınıf bildirimleri. C + enum sınıfları hakkında daha fazla bilgi için +/ CLI, C + +/ CX ve C ++ 11, [sabit listesi sınıfı](../windows/enum-class-cpp-component-extensions.md).

```
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

```
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

[sabit listesi sınıfı](../windows/enum-class-cpp-component-extensions.md)
