---
description: 'Daha fazla bilgi edinin: enum sınıfı (C++/CLı ve C++/CX)'
title: enum class (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
ms.assetid: 8010fa8c-bad6-45b4-8214-b4db64d7ffe1
ms.openlocfilehash: 309a1defa7288ec13ca058cc366d9cb8deac01ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220675"
---
# <a name="enum-class--ccli-and-ccx"></a>enum class (C++/CLI ve C++/CX)

Ad alanı kapsamında, Numaralandırıcılar adlı adlandırılmış sabitler kümesinden oluşan bir dizi Kullanıcı tanımlı tür olan bir sabit listesi bildirir.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

### <a name="remarks"></a>Açıklamalar

C++/CX ve C++/CLı, **Genel sabit** listesi sınıfını ve standart C++ **sabit listesi sınıfına** benzer ancak erişilebilirlik belirticisinin eklenmesiyle birlikte **özel sabit listesi sınıfını** destekler. **/Clr**' ın altında, c++ 11 **enum sınıf** türüne Izin verilir, ancak c++/CX ve C++/CLI türünü değil ISO numaralandırma türünü gerçekten istediğinizden emin olmak için uyarı C4472 oluşturur. ISO standart C++ anahtar sözcüğü hakkında daha fazla bilgi için **`enum`** bkz. [numaralandırmalar](../cpp/enumerations-cpp.md).

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="syntax"></a>Sözdizimi

```cpp
      access
      enum class
      enumeration-identifier
      [:underlying-type] { enumerator-list } [var];
accessenum structenumeration-identifier[:underlying-type] { enumerator-list } [var];
```

### <a name="parameters"></a>Parametreler

*erişmesini*<br/>
Ya da olabilen numaralandırmanın erişilebilirliği **`public`** **`private`** .

*Sabit Listesi-tanımlayıcı*<br/>
Sabit listesinin adı.

*temel alınan tür*<br/>
Seçim Sabit listesinin temel alınan türü.

Seçim. Yalnızca Windows çalışma zamanı),,,,,,,, veya olabilen numaralandırmanın temel alınan türü **`bool`** **`char`** `char16` `int16` `uint16` **`int`** `uint32` `int64` `uint64` .

*Numaralandırıcı-liste*<br/>
Numaralandırıcı adlarının virgülle ayrılmış listesi.

Her bir Numaralandırıcı değeri, derleyici tarafından örtük olarak tanımlanan veya açıkça gösterim, *Numaralandırıcı* `=` *sabit ifadesi* tarafından tanımlanan sabit bir ifadedir. Varsayılan olarak, ilk Numaralandırıcının değeri örtük olarak tanımlanmışsa sıfırdır. Her bir sonraki örtük tanımlanmış Numaralandırıcı değeri, önceki Numaralandırıcı + 1 değeridir.

*l*<br/>
Seçim Sabit listesi türü değişkeninin adı.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi ve örnekler için bkz. [enum](../cppcx/enums-c-cx.md).

Bir Numaralandırıcı değerini tanımlayan sabit ifade *temeldeki türle* temsil edilemez derleyici hata iletileri yayar.  Ancak derleyici, temel alınan tür için uygun olmayan bir değer için hata raporlamaz. Örneğin:

- *Temeldeki tür* sayısal ise ve bir Numaralandırıcı bu türün en büyük değerini belirtiyorsa, bir sonraki örtük olarak tanımlanmış numaralandırmanın değeri temsil edilemez.

- *Temel alınan tür* ise **`bool`** ve ikiden fazla numaralandırıcı örtük olarak tanımlanmışsa, ilk iki numaralandırıcıdan sonraki Numaralandırıcılar temsil edilemez.

- *Temeldeki tür* ise `char16` ve numaralandırma değeri 0Xd800 Ila 0xDFFF aralığında ise, değer temsil edilebilir. Ancak, değeri mantıksal olarak yanlış bir Unicode vekil çifti temsil ettiğinden ve yalıtımda görünmemelidir.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

### <a name="syntax"></a>Sözdizimi

```cpp
      access
      enum class
      name [:type] { enumerator-list } var;
accessenum structname [:type] { enumerator-list } var;
```

### <a name="parameters"></a>Parametreler

*erişmesini*<br/>
Sabit listesinin erişilebilirliği. Ya da olabilir **`public`** **`private`** .

*Numaralandırıcı-liste*<br/>
Numaralandırmadaki tanımlayıcıların (Numaralandırıcılar) virgülle ayrılmış listesi.

*ada*<br/>
Sabit listesinin adı. Anonim yönetilen numaralandırmalara izin verilmez.

*türüyle*<br/>
Seçim *Tanımlayıcıların* temel alınan türü. Bu, veya ' nin imzalı veya imzasız sürümleri gibi herhangi bir skalar tür **`int`** olabilir **`short`** **`long`** .  **`bool`** ya **`char`** da izin veriliyor.

*l*<br/>
Seçim Sabit listesi türü değişkeninin adı.

### <a name="remarks"></a>Açıklamalar

**enum sınıfı** ve **enum yapısı** eşdeğer bildirimlerdir.

İki tür numaralandırmalar vardır: yönetilen veya C++/CX ve standart.

Yönetilen veya C++/CX numaralandırması aşağıdaki şekilde tanımlanabilir.

```cpp
public enum class day {sun, mon };
```

ve anlamsal olarak eşdeğerdir:

```cpp
ref class day {
public:
   static const int sun = 0;
   static const int mon = 1;
};
```

Standart bir sabit listesi aşağıdaki gibi tanımlanabilir:

```cpp
enum day2 { sun, mon };
```

ve anlamsal olarak eşdeğerdir:

```cpp
static const int sun = 0;
static const int mon = 1;
```

Yönetilen Numaralandırıcı adları (*tanımlayıcılar*), numaralandırmanın tanımlandığı kapsama eklenmiş değildir; numaralandırıcılara yapılan tüm başvurular tam olarak nitelenmiş olmalıdır (*ad* `::` *tanımlayıcısı*).  Bu nedenle, anonim olarak yönetilen bir sabit listesi tanımlayamazsınız.

Standart bir sabit listesinin numaralandırıcıları kapsayan kapsama kesin bir şekilde eklenir.  Diğer bir deyişle, kapsayan kapsamda Numaralandırıcı ile aynı ada sahip başka bir sembol varsa, derleyici bir hata oluşturur.

Visual Studio 2002 ve Visual Studio 2003 ' de, Numaralandırıcılar zayıf olarak eklendi (aynı ada sahip başka bir tanımlayıcı olmadıkça kapsayan kapsamda görünür).

Standart bir C++ numaralandırması tanımlanmışsa ( **`class`** veya olmadan **`struct`** ), ile derleme, `/clr` numaralandırmanın yönetilen bir Enum olarak derlenmesine neden olur.  Numaralandırma yine de yönetilmeyen bir numaralandırmanın semantiklerine sahiptir.  Derleyicinin, bir `Microsoft::VisualC::NativeEnumAttribute` Programcının enum 'un doğal bir sabit listesi olması için amacını tanımlamak üzere bir özniteliği çıkarır.  Diğer derleyiciler yalnızca, standart sabit listesini yönetilen bir numaralandırma olarak görürler.

İle derlenen bir adlandırılmış, standart Enum, `/clr` yönetilen bir numaralandırma olarak derlemede görünür ve başka bir yönetilen derleyici tarafından tüketilebilir.   Ancak, adlandırılmamış standart enum derlemeden herkese açık olmayacaktır.

Visual Studio 2002 ve Visual Studio 2003 ' de, bir işlev parametresinde tür olarak kullanılan standart bir sabit listesi:

```cpp
// mcppv2_enum.cpp
// compile with: /clr
enum E { a, b };
void f(E) {System::Console::WriteLine("hi");}

int main() {
   E myi = b;
   f(myi);
}
```

işlev imzası için aşağıdaki işlemi MSIL 'de yayar:

```cpp
void f(int32);
```

Ancak, derleyicinin geçerli sürümlerinde standart Enum, işlev imzası için bir [Nativetrmattribute] ile yönetilen bir sabit listesi ve MSIL 'de aşağıdakiler olarak yayılır:

```cpp
void f(E)
```

Yerel Numaralandırmalar hakkında daha fazla bilgi için bkz. [C++ numaralandırma bildirimleri](../cpp/enumerations-cpp.md).

CLR numaralandırmaları hakkında daha fazla bilgi için bkz.

- [Sabit listesinin temel alınan türü](../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

```cpp
// mcppv2_enum_2.cpp
// compile with: /clr
// managed enum
public enum class m { a, b };

// standard enum
public enum n { c, d };

// unnamed, standard enum
public enum { e, f } o;

int main()
{
   // consume managed enum
   m mym = m::b;
   System::Console::WriteLine("no automatic conversion to int: {0}", mym);
   System::Console::WriteLine("convert to int: {0}", (int)mym);

   // consume standard enum
   n myn = d;
   System::Console::WriteLine(myn);

   // consume standard, unnamed enum
   o = f;
   System::Console::WriteLine(o);
}
```

```Output
no automatic conversion to int: b

convert to int: 1

1

1
```

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP için bileşen uzantıları](component-extensions-for-runtime-platforms.md)
