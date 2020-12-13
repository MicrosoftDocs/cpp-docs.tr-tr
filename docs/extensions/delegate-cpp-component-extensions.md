---
description: 'Daha fazla bilgi edinin: Temsilci (C++/CLı ve C++/CX)'
title: delegate (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- delegate_cpp
- delegate
helpviewer_keywords:
- delegate keyword [C++]
ms.assetid: 03caf23d-7873-4a23-9b34-becf42aaf429
ms.openlocfilehash: 92cd46980775a340e6bf0d6857ace91645d65a7d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333729"
---
# <a name="delegate--ccli-and-ccx"></a>delegate (C++/CLI ve C++/CX)

Bir işlev işaretçisini temsil eden bir tür bildirir.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

Hem Windows Çalışma Zamanı hem de ortak dil çalışma zamanı temsilcileri destekler.

### <a name="remarks"></a>Açıklamalar

**temsilci** , bağlama duyarlı bir anahtar sözcüktür. Daha fazla bilgi için bkz. [bağlama duyarlı anahtar sözcükler](context-sensitive-keywords-cpp-component-extensions.md).

Tür bir temsilciyise, derleme zamanında algılamak için `__is_delegate()` nitelik türünü kullanın. Daha fazla bilgi için bkz. [tür nitelikleri Için derleyici desteği](compiler-support-for-type-traits-cpp-component-extensions.md).

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

C++/CX, aşağıdaki söz dizimine sahip temsilcileri destekler.

### <a name="syntax"></a>Sözdizimi

```cpp
access
delegate
return-type
delegate-type-identifier
(
[ parameters ]
)
```

### <a name="parameters"></a>Parametreler

*erişmesini*<br/>
seçim Temsilcinin erişilebilirliği **`public`** (varsayılan) veya olabilir **`private`** . İşlev prototipi **`const`** veya anahtar sözcükleriyle de nitelenebilir **`volatile`** .

*dönüş türü*<br/>
İşlev prototipinin dönüş türü.

*temsilci türü tanımlayıcı*<br/>
Belirtilen temsilci türünün adı.

*parametrelere*<br/>
Seçim İşlev prototipinin türleri ve tanımlayıcıları.

### <a name="remarks"></a>Açıklamalar

Temsilci ile aynı prototipi içeren bir olay bildirmek için *Delegate-Type-Identifier* kullanın. Daha fazla bilgi için bkz. [Temsilciler (C++/CX)](../cppcx/delegates-c-cx.md).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

Ortak dil çalışma zamanı, aşağıdaki söz dizimine sahip temsilcileri destekler.

### <a name="syntax"></a>Sözdizimi

```cpp
access
delegate
function_declaration
```

### <a name="parameters"></a>Parametreler

*erişmesini*<br/>
seçim Temsilcinin dışındaki temsilci erişilebilirliği herkese açık veya özel olabilir.  Varsayılan değer özeldir.  Bir sınıfın içinde, bir temsilcinin herhangi bir erişilebilirliği olabilir.

*function_declaration*<br/>
Temsilciye bağlanabilen işlevin imzası. Bir temsilcinin dönüş türü herhangi bir yönetilen tür olabilir. Birlikte çalışabilirlik nedenleriyle, bir temsilcinin dönüş türünün CLS türü olması önerilir.

İlişkisiz bir temsilci tanımlamak için *function_declaration* ilk parametresi **`this`** nesne işaretçisinin türü olmalıdır.

### <a name="remarks"></a>Açıklamalar

Temsilciler çok noktaya yayın: "işlev işaretçisi" yönetilen bir sınıf içindeki bir veya daha fazla yönteme bağlanabilir. **Delegate** anahtar sözcüğü, belirli bir yöntem imzasıyla bir çok noktaya yayın temsilci türünü tanımlar.

Bir temsilci, statik bir yöntem gibi bir değer sınıfının bir yöntemine de bağlanabilir.

Bir temsilci aşağıdaki özelliklere sahiptir:

- Öğesinden devralır `System::MulticastDelegate` .

- İki bağımsız değişken alan bir oluşturucuya sahiptir: yönetilen sınıfa veya NULL 'a (statik bir metoda bağlama durumunda) ve belirtilen türdeki tam bir yönteme yönelik bir işaretçi.

- `Invoke`İmzası, temsilcinin belirtilen imzasıyla eşleşen adlı bir yöntemi vardır.

Bir temsilci çağrıldığında, bu işlevin işlevleri eklendiği sırada çağırılır.

Temsilcinin dönüş değeri, son ekli üye işlevinin dönüş değeridir.

Temsilciler aşırı yüklenemez.

Temsilciler bağlanabilir veya ilişkisiz olabilir.

Bir bağlantılı temsilciyi örneklediğinizde, ilk bağımsız değişken bir nesne başvurusu olacaktır. Bir temsilci örneklemesinin ikinci bağımsız değişkeni, yönetilen sınıf nesnesinin bir yönteminin adresi ya da bir değer türü yöntemine yönelik bir işaretçi olacaktır. Bir temsilci örneklemesinin ikinci bağımsız değişkeni, yöntemi tam sınıf kapsamı sözdizimiyle ve adres işlecini uygulayacak şekilde vermelidir.

İlişkisiz bir temsilciyi örneklediğinizde, ilk bağımsız değişken yönetilen sınıf nesnesinin bir yönteminin adresi ya da bir değer türü yöntemine yönelik bir işaretçi olacaktır. Bağımsız değişkeni, tam sınıf kapsamı söz dizimine sahip yöntemi vermelidir ve adres işlecini uygular.

Statik veya genel işleve bir temsilci oluştururken, yalnızca bir parametre gereklidir: işlev (isteğe bağlı olarak, işlevin adresi).

Temsilciler hakkında daha fazla bilgi için bkz.

- [Nasıl yapılır: Temsilcileri Tanımlama ve Kullanma (C++/CLI)](../dotnet/how-to-define-and-use-delegates-cpp-cli.md)

- [Genel Temsilciler (C++/CLI)](generic-delegates-visual-cpp.md)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki örnek, temsilcilerin nasıl bildirilemeyeceğini, başlatılacağını ve çağıralınacağını gösterir.

```cpp
// mcppv2_delegate.cpp
// compile with: /clr
using namespace System;

// declare a delegate
public delegate void MyDel(int i);

ref class A {
public:
   void func1(int i) {
      Console::WriteLine("in func1 {0}", i);
   }

   void func2(int i) {
      Console::WriteLine("in func2 {0}", i);
   }

   static void func3(int i) {
      Console::WriteLine("in static func3 {0}", i);
   }
};

int main () {
   A ^ a = gcnew A;

   // declare a delegate instance
   MyDel^ DelInst;

   // test if delegate is initialized
   if (DelInst)
      DelInst(7);

   // assigning to delegate
   DelInst = gcnew MyDel(a, &A::func1);

   // invoke delegate
   if (DelInst)
      DelInst(8);

   // add a function
   DelInst += gcnew MyDel(a, &A::func2);

   DelInst(9);

   // remove a function
   DelInst -= gcnew MyDel(a, &A::func1);

   // invoke delegate with Invoke
   DelInst->Invoke(10);

   // make delegate to static function
   MyDel ^ StaticDelInst = gcnew MyDel(&A::func3);
   StaticDelInst(11);
}
```

```Output
in func1 8

in func1 9

in func2 9

in func2 10

in static func3 11
```

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP için bileşen uzantıları](component-extensions-for-runtime-platforms.md)
