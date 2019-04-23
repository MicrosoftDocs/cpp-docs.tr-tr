---
title: sabit listesi sınıfı (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
ms.assetid: 8010fa8c-bad6-45b4-8214-b4db64d7ffe1
ms.openlocfilehash: da9097a02de08fd1615f5401d08c438c5f64c139
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59037032"
---
# <a name="enum-class--ccli-and-ccx"></a>sabit listesi sınıfı (C++/CLI ve C++/CX)

Numaralandırıcı olarak adlandırılan sabitler kümesinden oluşan kullanıcı tanımlı türü olan ad alanı kapsamında bir sabit listesi bildirir.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

### <a name="remarks"></a>Açıklamalar

C++/CX ve C++/CLI desteği **genel sabit listesi sınıfı** ve **özel enum sınıfı** standart benzer olan C++ **sabit listesi sınıfı** ancak ek olarak Erişilebilirlik tanımlayıcısı. Altında **/CLR**, C ++ 11 **sabit listesi sınıfı** tür izin verilir, ancak gerçekten ISO sabit listesi türü istediğinizden emin olmak için tasarlanmıştır C4472 uyarısı oluşturur ve C++/CX ve C++/CLI türü. ISO Standard C++ hakkında daha fazla bilgi için **enum** anahtar sözcüğü, bkz: [numaralandırmalar](../cpp/enumerations-cpp.md).

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

*Erişim*<br/>
Erişilebilirlik olabilir numaralandırma **genel** veya **özel**.

*Numaralandırma tanımlayıcı*<br/>
Sabit listesinin adı.

*temel alınan türü*<br/>
(İsteğe bağlı) Sabit listesinin temel alınan türü.

(İsteğe bağlı. Yalnızca Windows Runtime) olabilir sabit listesi türünü temel **bool**, **char**, `char16`, `int16`, `uint16`, **int**, `uint32`, `int64`, veya `uint64`.

*Numaralandırıcı-listesi*<br/>
Numaralandırıcı adları virgülle ayrılmış listesi.

Her Numaralayıcı ya da örtük olarak derleyici tarafından veya açık olarak gösterimi tarafından tanımlanan sabit bir ifade değeri *Numaralandırıcı*`=`*sabit-ifade*. Örtük tanımlanırsa, varsayılan olarak, ilk Numaralandırıcı değeri sıfırdır. Örtük olarak tanımlı sonraki her Numaralandırıcı değerini, önceki numaralandırıcıların + 1 değerdir.

*var*<br/>
(İsteğe bağlı) Sabit listesi türünde bir değişken adı.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi ve örnekler için bkz. [numaralandırmalar](../cppcx/enums-c-cx.md).

Numaralayıcı değeri tanımlayan sabit ifade tarafından temsil edilemiyorsa derleyici bir hata iletilerini gösterir Not *temel alınan türü*.  Ancak, derleyici temel alınan türü için uygun olmayan bir değer için bir hata bildirmez. Örneğin:

- Varsa *temel alınan türü* sayısaldır ve maksimum değer türü için bir numaralandırıcı belirtir, sonraki örtük olarak tanımlanan enumeratoin değerini temsil edilemez.

- Varsa *temel alınan türü* olduğu **bool**, ve ikiden fazla numaralandırıcılar örtük olarak tanımlı, ilk iki gösterilemez sonra numaralandırıcıların.

- Varsa *temel alınan türü* olduğu `char16`ve sabit listesi değeri 0xD800 ile 0xDFFF aralıkları, değeri temsil edilebilir. Ancak, bir Unicode yarım temsil ettiğinden mantıksal olarak yanlış değer vekil çifti ve yalıtım modunda görünmemelidir.

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

*Erişim*<br/>
Sabit listesinin erişilebilirlik. Olabilir **genel** veya **özel**.

*Numaralandırıcı-listesi*<br/>
Sabit tanımlayıcıları (Numaralandırıcı) virgülle ayrılmış listesi.

*Adı*<br/>
Sabit listesinin adı. Anonim yönetilen numaralandırmalar izin verilmez.

*type*<br/>
(İsteğe bağlı) Temel alınan türü *tanımlayıcıları*. Bu imzalı veya imzasız sürümleri gibi herhangi bir skalar türü olabilir **int**, **kısa**, veya **uzun**.  **bool** veya **char** da izin verilir.

*var*<br/>
(İsteğe bağlı) Sabit listesi türünde bir değişken adı.

### <a name="remarks"></a>Açıklamalar

**sabit listesi sınıfı** ve **enum struct** eşdeğer bildirimlerdir.

Numaralandırmalar iki tür vardır: yönetilen veya C++/CX ve standart.

Yönetilen veya C++/CX sabit listesi aşağıdaki gibi tanımlanabilir

```cpp
public enum class day {sun, mon };
```

ve anlam olarak eşdeğerdir:

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

ve anlam olarak eşdeğerdir:

```cpp
static const int sun = 0;
static const int mon = 1;
```

Yönetilen Numaralandırıcı adları (*tanımlayıcıları*) burada numaralandırma tanımlanır; numaralandırıcıların tüm başvurularını tam olarak nitelenmiş olmalıdır kapsama eklenen değil (*adı* `::` *tanımlayıcı*).  Bu nedenle, anonim bir yönetilen Numaralandırıcı tanımlayamazsınız.

Standart numaralandırıcısının numaralandırıcıların türü kesin kapsayan kapsamın içine eklenmiş.  Diğer bir deyişle, bir numaralandırıcı kapsayan kapsamda aynı ada sahip başka bir simge varsa, derleyici bir hata oluşturur.

Visual Studio 2002 ve Visual Studio 2003'te numaralandırıcılar zayıf (görülebilir kapsayan kapsamda aynı ada sahip başka bir tanımlayıcı değilse) eklenmiş.

Standart bir C++ numaralandırma tanımlanmazsa (olmadan **sınıfı** veya **yapı**), derleme ile `/clr` numaralandırması yönetilen bir sabit derlenmesine neden olur.  Numaralandırma hala yönetilmeyen bir numaralandırma semantiği vardır.  Unutmayın, derleyicinin eklediği bir öznitelik `Microsoft::VisualC::NativeEnumAttribute` yerel bir numaralandırma olması sabit bir programcı hedefini belirlemek için.  Diğer derleyiciler, yalnızca standart sabit listesi yönetilen bir sabit listesi görürsünüz.

Adlı bir, standart sabit listesi ile derlenmiş `/clr` derlemedeki yönetilen bir sabit listesi olarak görünür ve diğer yönetilen derleyici tarafından tüketilebilir.   Ancak, adlandırılmamış bir standart enum derlemeden herkese görünür olmayacaktır.

Visual Studio 2002 ve Visual Studio 2003 ' türü bir işlev parametresi olarak kullanılan standart bir sabit listesi:

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

işlev imzası için MSIL aşağıdaki yayması:

```cpp
void f(int32);
```

Ancak, geçerli derleyici sürümlerinde, standart sabit listesi [NativeEnumAttribute] ve işlev imzası için MSIL aşağıdaki ile yönetilen bir sabit listesi olarak yayılır:

```cpp
void f(E)
```

Yerel numaralandırmalar hakkında daha fazla bilgi için bkz. [C++ numaralandırma bildirimleri](../cpp/enumerations-cpp.md).

CLR numaralandırmaları hakkında daha fazla bilgi için bkz:

- [Bir sabit listesinin temel alınan türü](../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md)

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

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)