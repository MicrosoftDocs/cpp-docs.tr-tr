---
title: Diziler (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- cli::array
- details::array
- lang::array
helpviewer_keywords:
- array keyword [C++]
- arrays [C++], multidimensional
- multidimensional arrays
- arrays [C++]
ms.assetid: 49445812-d775-4db1-a231-869598dbb955
ms.openlocfilehash: 814be57caafed117a1403105d46326ac53682578
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91500895"
---
# <a name="arrays-ccli-and-ccx"></a>Diziler (C++/CLI ve C++/CX)

`Platform::Array<T>`C++/cx içindeki tür veya c++/CLI içindeki **Array** anahtar sözcüğü, belirtilen bir tür ve başlangıç değerinin dizisini bildirir.

## <a name="all-platforms"></a>Tüm Platformlar

Dizi, bildirimde kapanış açılı ayracından (>) sonra,-Object (^) değiştiricisi kullanılarak bildirilmelidir.
Dizinin öğe sayısı türün bir parçası değil. Bir dizi değişkeni, farklı boyutlardaki dizilere başvurabilir.

Standart C++ ' dan farklı olarak, alt simge, işaretçi aritmetiği için bir eş anlamlı değildir ve ilgili değildir.

Diziler hakkında daha fazla bilgi için bkz.

- [Nasıl yapılır: C++/CLı ' da dizileri kullanma](../dotnet/how-to-use-arrays-in-cpp-cli.md)

- [Değişken Bağımsız Değişken Listeleri (...) (C++/CLI)](variable-argument-lists-dot-dot-dot-cpp-cli.md)

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

Diziler `Platform` ad alanının üyeleridir. Diziler yalnızca bir boyutlu olabilir.

### <a name="syntax"></a>Sözdizimi

Sözdiziminin ilk örneği, dizi ayırmak için **ref New** Aggregate anahtar sözcüğünü kullanır. İkinci örnek bir yerel dizi bildirir.

```cpp
[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier =
    ref new[Platform::]Array<initialization-type> [{initialization-list [,...]}]

[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier =
    {initialization-list [,...]}
```

*ilerini*<br/>
Seçim Bu depolama sınıfı Belirticilerinin bir veya daha fazlası: [kesilebilir](../cpp/mutable-data-members-cpp.md), [volatile](../cpp/volatile-cpp.md), [const](../cpp/const-cpp.md), [extern](../cpp/extern-cpp.md), [static](../cpp/static-members-cpp.md).

*dizi türü*<br/>
Dizi değişkeninin türü. Geçerli türler Windows Çalışma Zamanı sınıflar ve temel türler, başvuru sınıfları ve yapılar, değer sınıfları ve yapılar ve yerel işaretçiler ( `type*` ).

*sırası*<br/>
Seçim Dizinin boyut sayısı. 1 olmalıdır.

*Tanımlayıcısını*<br/>
Dizi değişkeninin adı.

*başlatma türü*<br/>
Diziyi başlatacak değerlerin türü. Genellikle, *dizi türü* ve *başlatma türü* aynı türdür. Ancak, *başlatma türünden* *dizi türüne*dönüştürme varsa türler farklı olabilir; Örneğin, *başlatma türü* *dizi türünden*türetildiyse.

*başlatma-listeleme*<br/>
Seçim Dizi öğelerini başlatacak küme ayraçları içindeki bir virgülle ayrılmış değerler listesi. Örneğin, tek boyutlu 3 öğe dizisi bildiren *sıralama boyutu-listesi* ise `(3)` , *başlatma listesi* olabilir `{1,2,3}` .

### <a name="remarks"></a>Açıklamalar

Bir türün ile başvuru sayılı bir dizi olup olmadığını derleme zamanında tespit edebilirsiniz `__is_ref_array(type)` . Daha fazla bilgi için bkz. [tür nitelikleri Için derleyici desteği](compiler-support-for-type-traits-cpp-component-extensions.md).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

### <a name="examples"></a>Örnekler

Aşağıdaki örnek 100 öğelerine sahip tek boyutlu bir dizi oluşturur.

```cpp
// cwr_array.cpp
// compile with: /ZW
using namespace Platform;
ref class MyClass {};
int main() {
   // one-dimensional array
   Array<MyClass^>^ My1DArray = ref new Array<MyClass^>(100);
   My1DArray[99] = ref new MyClass();
}
```

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

### <a name="syntax"></a>Sözdizimi

Sözdiziminin ilk örneği bir dizi ayırmak için **gcnew** anahtar sözcüğünü kullanır. İkinci örnek bir yerel dizi bildirir.

```cpp
[qualifiers] [cli::]array<[qualifiers] array-type [,rank]>^ identifier =
    gcnew [cli::]array<initialization-type[,rank]>(rank-size-list[,...]) [{initialization-list [,...]}]

[qualifiers] [cli::]array<[qualifiers] array-type [,rank]>^ identifier =
    {initialization-list [,...]}
```

*ilerini*<br/>
Seçim Bu depolama sınıfı Belirticilerinin bir veya daha fazlası: [kesilebilir](../cpp/mutable-data-members-cpp.md), [volatile](../cpp/volatile-cpp.md), [const](../cpp/const-cpp.md), [extern](../cpp/extern-cpp.md), [static](../cpp/static-members-cpp.md).

*dizi türü*<br/>
Dizi değişkeninin türü. Geçerli türler Windows Çalışma Zamanı sınıflar ve temel türler, başvuru sınıfları ve yapılar, değer sınıfları ve yapılar, yerel işaretçiler ( `type*` ) ve yerel Pod (düz eski veriler) türleridir.

*sırası*<br/>
Seçim Dizinin boyut sayısı. Varsayılan değer 1 ' dir; maksimum değer 32 ' dir. Dizinin her boyutu bir dizidir.

*Tanımlayıcısını*<br/>
Dizi değişkeninin adı.

*başlatma türü*<br/>
Diziyi başlatacak değerlerin türü. Genellikle, *dizi türü* ve *başlatma türü* aynı türdür. Ancak, *başlatma türünden* *dizi türüne*dönüştürme varsa türler farklı olabilir; Örneğin, *başlatma türü* *dizi türünden*türetildiyse.

*sıralama-boyut-liste*<br/>
Dizideki her boyutun boyutunun virgülle ayrılmış bir listesi. Alternatif olarak, *başlatma listesi* parametresi belirtilirse, derleyici her boyutun boyutunu verebilir ve *sıralama boyutu listesi* atlanabilir.

*başlatma-listeleme*<br/>
Seçim Dizi öğelerini başlatacak küme ayraçları içindeki bir virgülle ayrılmış değerler listesi. Ya da birden çok boyutlu bir dizide öğeleri başlatacak olan iç içe *başlatma* listesi öğelerinin virgülle ayrılmış listesi.

Örneğin, tek boyutlu 3 öğe dizisi bildiren *sıralama boyutu-listesi* ise `(3)` , *başlatma listesi* olabilir `{1,2,3}` . İlk boyutta 3 öğeden oluşan üç boyutlu bir dizi bildiren, *sıralama-boyut-liste* ise, `(3,2,4)` ikincinin 2 öğesi ve üçüncü, *başlatma listesindeki* 4 öğe olabilir `{{1,2,3},{0,0},{-5,10,-21,99}}` .)

### <a name="remarks"></a>Açıklamalar

**dizi** [Platform, Default ve CLI namespaces](platform-default-and-cli-namespaces-cpp-component-extensions.md) ad alanıdır.

Standart C++ gibi, bir dizinin dizinleri sıfır tabanlıdır ve köşeli ayraçlar ([]) kullanılarak bir dizi alt simge olur. Standart C++ ' dan farklı olarak, çok boyutlu bir dizinin dizinleri her boyut için bir dizi köşeli ayraç ([]) işleci yerine her boyut için bir dizin listesinde belirtilir. Örneğin *, tanımlayıcı [**index1*] [ *index2*] *yerine [**index1*, *index2*].

Tüm yönetilen diziler öğesinden devralınır `System::Array` . Herhangi bir yöntemi veya özelliği `System::Array` doğrudan dizi değişkenine uygulanabilir.

Öğe türü bir yönetilen sınıfa işaretçi olan bir dizi ayırdığınızda, öğeler 0 ' dan başlatılır.

Öğe türü bir değer türü olan bir dizi ayırdığınızda `V` , için varsayılan Oluşturucu `V` her dizi öğesine uygulanır. Daha fazla bilgi için bkz. [C++ yerel türlerine .NET Framework eşdeğerleri (c++/CLI)](../dotnet/managed-types-cpp-cli.md#dotnet).

Derleme zamanında, bir türün ile ortak dil çalışma zamanı (CLR) dizisi olup olmadığını tespit edebilirsiniz `__is_ref_array(type)` . Daha fazla bilgi için bkz. [tür nitelikleri Için derleyici desteği](compiler-support-for-type-traits-cpp-component-extensions.md).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki örnek, 100 öğelerine sahip tek boyutlu bir dizi ve ilk boyutta 3 öğe, ikincisi ise 5 öğe ve üçüncü 6 öğe içeren üç boyutlu bir dizi oluşturur.

```cpp
// clr_array.cpp
// compile with: /clr
ref class MyClass {};
int main() {
   // one-dimensional array
   array<MyClass ^> ^ My1DArray = gcnew array<MyClass ^>(100);
   My1DArray[99] = gcnew MyClass();

   // three-dimensional array
   array<MyClass ^, 3> ^ My3DArray = gcnew array<MyClass ^, 3>(3, 5, 6);
   My3DArray[0,0,0] = gcnew MyClass();
}
```

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP için bileşen uzantıları](component-extensions-for-runtime-platforms.md)
