---
title: delegate (C + +/ CLI ve C + +/ CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- delegate_cpp
- delegate
helpviewer_keywords:
- delegate keyword [C++]
ms.assetid: 03caf23d-7873-4a23-9b34-becf42aaf429
ms.openlocfilehash: eedaf81a52fc28de4a640de7345ff3486c5f4a3a
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787718"
---
# <a name="delegate--ccli-and-ccx"></a>delegate (C + +/ CLI ve C + +/ CX)

Bir işlev işaretçisi temsil eden bir tür bildirir.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

Windows çalışma zamanı ve ortak dil çalışma zamanı temsilcileri destekler.

### <a name="remarks"></a>Açıklamalar

**Temsilci** bağlama duyarlı bir anahtar sözcüktür. Daha fazla bilgi için [Context-Sensitive Keywords](context-sensitive-keywords-cpp-component-extensions.md).

Bir tür bir delegate ise derleme zamanında algılamak için kullanmak `__is_delegate()` türü niteliğine. Daha fazla bilgi için [tür özellikleri için derleyici desteği](compiler-support-for-type-traits-cpp-component-extensions.md).

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

C + +/ CX temsilciler aşağıdaki sözdizimini destekler.

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

*Erişim*<br/>
(isteğe bağlı) Olabilir temsilci erişilebilirliğini **genel** (varsayılan) veya **özel**. İşlev prototipi ile de nitelendirilmesi **const** veya **geçici** anahtar sözcükleri.

*dönüş türü*<br/>
İşlev prototipi dönüş türü.

*temsilci türü tanımlayıcısı*<br/>
Bildirilen temsilci türünün adı.

*parametreler*<br/>
(İsteğe bağlı) Türleri ve işlev prototipi tanımlayıcıları.

### <a name="remarks"></a>Açıklamalar

Kullanım *temsilci türü tanımlayıcısı* temsilci olarak aynı prototipe sahip bir olay bildirmek için. Daha fazla bilgi için [temsilciler (C + +/ CX)](../cppcx/delegates-c-cx.md).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

Ortak dil çalışma zamanı, aşağıdaki sözdizimi ile temsilciler destekler.

### <a name="syntax"></a>Sözdizimi

```cpp
access
delegate
function_declaration
```

### <a name="parameters"></a>Parametreler

*Erişim*<br/>
(isteğe bağlı) Derlemenin dışında temsilci erişilebilirliğini genel veya özel olabilir.  Varsayılan büyük/küçük harf özeldir.  Bir sınıf içinde bir temsilci, herhangi bir erişilebilirlik sahip olabilir.

*function_declaration*<br/>
Temsilciye bağlanabilir işlev imzası. Bir temsilcinin dönüş türü, herhangi bir yönetilen türü olabilir. Birlikte çalışabilirlik nedeniyle, bir temsilcinin dönüş türü CLS türü olması önerilir.

Bağlanmamış bir temsilci, ilk parametreyi tanımlamak için *function_declaration* türünde olmalıdır **bu** nesne işaretçisi.

### <a name="remarks"></a>Açıklamalar

Çok noktaya yayın temsilcileri: "işlev işaretçisi" yönetilen bir sınıf içinde bir veya daha fazla yöntemlere bağlı olabilir. **Temsilci** anahtar sözcük belirli bir yöntem imzasını bir çok noktaya yayın temsilci türüyle tanımlar.

Bir temsilci için statik bir yöntemi gibi bir değer sınıfının bir yöntemi de bağlı olabilir.

Bir temsilci, aşağıdaki özelliklere sahiptir:

- Devraldığı `System::MulticastDelegate`.

- İki bağımsız değişken alan bir oluşturucu vardır: yönetilen bir sınıf veya NULL (durumunda, bağlama için bir statik yöntem) ve tam yöntemi belirtilen türe ait bir işaretçi.

- Adında bir yöntemi vardır `Invoke`, bildirilen metot temsilcisinin imzası imzası eşleşir.

Temsilci çağrıldığında, işlevlere bağlı sırayla denir.

Bir temsilcinin dönüş değeri, son eklenen üye işlevinin dönüş değeridir.

Temsilciler aşırı yüklenemez.

Temsilciler bağlı veya kesildi.

İlişkili bir temsilci, ilk bağımsız değişkeni bir nesne başvurusu olmalıdır. Bir temsilci örneğini oluşturmada ikinci bağımsız değişkeni ya da adresi bir yönetilen sınıf nesnesi veya bir işaretçi bir yöntemin bir yönteme bir değer türü olması gerekir. Bir temsilci örneğini oluşturmada ikinci bağımsız değişkeni, tam sınıf kapsamı sözdizimi ile yöntem adı ve address-of işlecini uygulayın.

Bağlanmamış bir temsilci örneğini oluştururken, ilk bağımsız değişken ya da bir yöntem bir yönetilen sınıf nesnesi veya bir yönteme bir değer türünün işaretçisi adresi olmalıdır. Bağımsız değişken, tam sınıf kapsamı sözdizimi ile yöntem adı ve address-of işlecini uygulayın.

Statik veya genel bir işlev bir temsilciye oluştururken, yalnızca bir parametresi gerekli değildir: ' % s'işlevi (isteğe bağlı olarak, bir işlevin adresi).

Temsilciler hakkında daha fazla bilgi için bkz.

- [Nasıl yapılır: Temsilcileri Tanımlama ve Kullanma (C++/CLI)](../dotnet/how-to-define-and-use-delegates-cpp-cli.md)

- [Genel Temsilciler (C++/CLI)](generic-delegates-visual-cpp.md)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki örnek, temsilciler çağırma bildirmek ve başlatmak gösterilmektedir.

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

## <a name="see-also"></a>Ayrıca Bkz.

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)