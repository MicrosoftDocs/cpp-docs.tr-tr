---
title: Genel İşlevler (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- functions [C++], generic
- generic methods
- generics [C++], functions
- methods [C++], generic
- generic functions
ms.assetid: 8e409364-58f9-4360-b486-e7d555e0c218
ms.openlocfilehash: 3d648a23176786985a7ca1e22165c7c5a695e601
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216017"
---
# <a name="generic-functions-ccli"></a>Genel İşlevler (C++/CLI)

Genel işlev, tür parametreleriyle belirtilen bir işlevdir. Çağrıldığında, tür parametreleri yerine gerçek türler kullanılır.

## <a name="all-platforms"></a>Tüm Platformlar

### <a name="remarks"></a>Açıklamalar

Bu özellik tüm platformlar için geçerlidir.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

Bu özellik Windows Çalışma Zamanı desteklenmez.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği:`/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

Genel işlev, tür parametreleriyle belirtilen bir işlevdir. Çağrıldığında, tür parametreleri yerine gerçek türler kullanılır.

### <a name="syntax"></a>Söz dizimi

```cpp
[attributes] [modifiers]
return-type identifier<type-parameter identifier(s)>
[type-parameter-constraints clauses]

([formal-parameters])
{function-body}
```

### <a name="parameters"></a>Parametreler

*özelliklerine*<br/>
Seçim Ek bildirime dayalı bilgiler. Öznitelikler ve öznitelik sınıfları hakkında daha fazla bilgi için bkz. öznitelikler.

*ilerine*<br/>
Seçim İşlev için statik gibi bir değiştirici.  **`virtual`** sanal yöntemler genel olmadığından izin verilmiyor.

*dönüş türü*<br/>
Yöntem tarafından döndürülen tür. Dönüş türü void ise, dönüş değeri gerekli değildir.

*Tanımlayıcısını*<br/>
İşlev adı.

*tür-parametre tanımlayıcıları*<br/>
Virgülle ayrılmış tanımlayıcılar listesi.

*biçimsel-parametreler*<br/>
Seçim Parametre listesi.

*tür-parametre-kısıtlamalar-yan tümceler*<br/>
Bu, tür bağımsız değişkenleri olarak kullanılabilecek türlerin kısıtlamalarını belirtir ve [genel tür parametrelerinde (C++/CLI) kısıtlamalar](constraints-on-generic-type-parameters-cpp-cli.md)halinde belirtilen formu alır.

*işlev gövdesi*<br/>
Yöntemin, tür parametresi tanımlayıcılarına başvurabilen gövdesi.

### <a name="remarks"></a>Açıklamalar

Genel işlevler, genel bir tür parametresiyle belirtilen işlevlerdir. Bunlar bir sınıf veya yapı veya tek başına işlevlerde Yöntemler olabilir. Tek bir genel bildirim örtülü olarak yalnızca genel tür parametresi için farklı bir gerçek tür değiştirme içinde farklılık gösteren bir işlev ailesini bildirir.

Bir sınıf veya yapı Oluşturucu, genel tür parametreleriyle bildirilemez.

Çağrıldığında, genel tür parametresi gerçek bir tür ile değiştirilmiştir. Gerçek tür, bir şablon işlev çağrısına benzer bir sözdizimi kullanılarak açılı ayraçlar içinde açıkça belirtilebilir. Tür parametreleri olmadan çağrılırsa, derleyici gerçek türü işlev çağrısında sağlanan parametrelerden yapmayı dener. Hedeflenen tür bağımsız değişkeni kullanılan parametrelerden çıkarılamadığı takdirde, derleyici bir hata bildirir.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği:`/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki kod örneği, genel bir işlevi göstermektedir.

```cpp
// generics_generic_function_1.cpp
// compile with: /clr
generic <typename ItemType>
void G(int i) {}

ref struct A {
   generic <typename ItemType>
   void G(ItemType) {}

   generic <typename ItemType>
   static void H(int i) {}
};

int main() {
   A myObject;

   // generic function call
   myObject.G<int>(10);

   // generic function call with type parameters deduced
   myObject.G(10);

   // static generic function call
   A::H<int>(10);

   // global generic function call
   G<int>(10);
}
```

Genel işlevler imzaya veya parametre sayısına bağlı olarak, bir işlevdeki tür parametrelerinin sayısına göre aşırı yüklenebilir. Ayrıca, işlevler bazı tür parametrelerinde farklılık gösterdiği sürece genel işlevler aynı ada sahip genel olmayan işlevlerle aşırı yüklenebilir. Örneğin, aşağıdaki işlevler aşırı yüklenebilir:

```cpp
// generics_generic_function_2.cpp
// compile with: /clr /c
ref struct MyClass {
   void MyMythod(int i) {}

   generic <class T>
   void MyMythod(int i) {}

   generic <class T, class V>
   void MyMythod(int i) {}
};
```

Aşağıdaki örnek bir dizideki ilk öğeyi bulmak için genel bir işlev kullanır. Bu, `MyClass` temel sınıftan devralan bildirir `MyBaseClass` . `MyClass``MyFunction`temel sınıf içindeki başka bir genel işlevi çağıran genel bir işlev içerir `MyBaseClassFunction` . İçinde, `main` genel işlevi, `MyFunction` farklı tür bağımsız değişkenleri kullanılarak çağrılır.

```cpp
// generics_generic_function_3.cpp
// compile with: /clr
using namespace System;

ref class MyBaseClass {
protected:
   generic <class ItemType>
   ItemType MyBaseClassFunction(ItemType item) {
      return item;
   }
};

ref class MyClass: public MyBaseClass {
public:
   generic <class ItemType>
   ItemType MyFunction(ItemType item) {
      return MyBaseClass::MyBaseClassFunction<ItemType>(item);
   }
};

int main() {
   MyClass^ myObj = gcnew MyClass();

   // Call MyFunction using an int.
   Console::WriteLine("My function returned an int: {0}",
                           myObj->MyFunction<int>(2003));

   // Call MyFunction using a string.
   Console::WriteLine("My function returned a string: {0}",
   myObj->MyFunction<String^>("Hello generic functions!"));
}
```

```Output
My function returned an int: 2003
My function returned a string: Hello generic functions!
```

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP için bileşen uzantıları](component-extensions-for-runtime-platforms.md)<br/>
[Genel Türler](generics-cpp-component-extensions.md)
