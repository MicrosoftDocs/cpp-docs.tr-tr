---
title: Genel Tür Parametrelerindeki Kısıtlamalar (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- where
helpviewer_keywords:
- where keyword [C++]
- constraints, C++
ms.assetid: eb828cc9-684f-48a3-a898-b327700c0a63
ms.openlocfilehash: c0ad5a22adec0d93019e9ea5c81cc8329d1607f8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533713"
---
# <a name="constraints-on-generic-type-parameters-ccli"></a>Genel Tür Parametrelerindeki Kısıtlamalar (C++/CLI)

Genel tür veya yöntem bildirimi bir tür parametresi kısıtlamalarına sahip kazanabilir. Kısıtlama türü bağımsız değişken olarak kullanılan türler karşılaması gereken bir gereksinimdir. Örneğin, bir kısıtlaması tür bağımsız değişkeni belirli bir arabirim gerekir veya belirli bir sınıftan olabilir.

İsteğe bağlı kısıtlamaları; bir kısıtlama bir parametre belirtmeden bu parametreye sınırlamak için eşdeğer <xref:System.Object>.

## <a name="syntax"></a>Sözdizimi

```cpp
where type-parameter: constraint list
```

### <a name="parameters"></a>Parametreler

*tür-parametresi*<br/>
Kısıtlı için tür parametrelerinden biri.

*sınırlama listesi*<br/>
*sınırlama listesi* kısıtlaması belirtimleri, virgülle ayrılmış listesidir. Liste türü parametresi tarafından uygulanacak arabirim içerebilir.

Listeden bir sınıf de içerebilir. Bir taban sınıfı kısıtlamasını karşılamak tür bağımsız değişkeni, kısıtlama aynı sınıfta olması veya kısıtlamasından türetilen olmalıdır.

Ayrıca belirtebileceğiniz **gcnew()** tür bağımsız değişkeni, genel bir parametresiz oluşturucusu; olmalıdır belirtmek için veya **başvuru sınıfı** tür bağımsız değişkeni, herhangi bir sınıf içeren bir başvuru türü olmalıdır belirtmek için arabirim, temsilci veya dizi türü; veya **değer sınıfının** türü belirtmek için bağımsız değişken bir değer türü olması gerekir. Herhangi bir değer türü boş değer dışında\<T > belirtilebilir.

Genel parametre kısıtlama olarak belirtebilirsiniz. Sınırlama türü için sağlanan tür bağımsız değişkeni olması veya kısıtlama türünden türetilmesi gerekir. Bu, bir çıplak tür kısıtlaması olarak adlandırılır.

## <a name="remarks"></a>Açıklamalar

Kısıtlama yan tümcesi oluşan **burada** bir tür parametresi ile bir iki nokta üst üste ve ardından (**:**) hem de kısıtlaması tür parametresi kısıtlaması yapısını belirtir. **Burada** bir bağlama duyarlı anahtar sözcük; bkz [Context-Sensitive Keywords](../windows/context-sensitive-keywords-cpp-component-extensions.md) daha fazla bilgi için. Birden çok ayrı **burada** yan tümceleri bir alana sahip.

Tür parametreleri sınırlamalar genel tür veya yöntem bağımsız değişkenleri olarak kullanılan türler yerleştirmek için kısıtlamalar uygulanır.

Bağımsız değişken türleri veya belirtilen bir sınıftan veya gereken belirtilen bir arabirim, sınıf ve arabirim kısıtlamalarını belirtin.

Bir genel tür veya yöntemin kısıtlamaları uygulamaya kodunda bu tür veya yöntem kısıtlanmış türdeki bilinen özelliklerden yararlanmak için sağlar. Örneğin, tür parametresi uygular, genel bir sınıf bildirebilirsiniz `IComparable<T>` arabirimi:

```cpp
// generics_constraints_1.cpp
// compile with: /c /clr
using namespace System;
generic <typename T>
where T : IComparable<T>
ref class List {};
```

Bu kısıtlama için kullanılan bir tür bağımsız değişkeni gerektirir `T` uygulayan `IComparable<T>` derleme zamanında. Ayrıca, arabirim yöntemleri gibi sağlar `CompareTo`, çağrılabilir. Atama türü parametresinin bir örneğinde arabirim yöntemleri çağırmak için gereklidir.

Tür bağımsız değişkenin sınıfında statik yöntemler tür parametresi ile çağrılamaz; yalnızca gerçek adlandırılmış tür çağrılabilir.

Bir kısıtlama gibi yerleşik türleri dahil olmak üzere bir değer türü olamaz **int** veya **çift**. Türetilmiş sınıflar değer türleri olamaz, yalnızca bir sınıf her zamankinden kısıtlamasını çalıştırılabilmesi. Bu durumda, belirli bir değer türü tarafından değiştirilen tür parametresi ile genel yazılabilir.

Bilinmeyen tür yöntemleri veya arabirimi desteklediğini kısıtlamaları yaptığından sürece derleyici yöntemlerden birini kullanın veya diğer özellikleri bilinmeyen bir türde izin vermez beri kısıtlamaları bazı durumlarda gereklidir.

Virgülle ayrılmış bir listede birden çok aynı tür parametresi kısıtlamaları belirtilebilir.

```cpp
// generics_constraints_2.cpp
// compile with: /c /clr
using namespace System;
using namespace System::Collections::Generic;
generic <typename T>
where T : List<T>, IComparable<T>
ref class List {};
```

Birden çok tür parametreleriyle kullanın **burada** her tür parametresi için yan tümcesi. Örneğin:

```cpp
// generics_constraints_3.cpp
// compile with: /c /clr
using namespace System;
using namespace System::Collections::Generic;

generic <typename K, typename V>
   where K: IComparable<K>
   where V: IComparable<K>
ref class Dictionary {};
```

Özetlemek gerekirse, aşağıdaki kurallara göre kodunuzda kısıtlamaları kullanın:

- Birden fazla kısıtlama listede yoksa, herhangi bir sırada kısıtlamaları listelenebilir.

- Kısıtlama da soyut temel sınıflar gibi sınıf türleri olabilir. Ancak, kısıtlamaları değer türleri veya sealed sınıfları olamaz.

- Tür parametrelerinin kendilerini kısıtlamaları olamaz, ancak bunlar açık bir oluşturulmuş tür tür parametrelerinde içerebilir. Örneğin:

    ```cpp
    // generics_constraints_4.cpp
    // compile with: /c /clr
    generic <typename T>
    ref class G1 {};

    generic <typename Type1, typename Type2>
    where Type1 : G1<Type2>   // OK, G1 takes one type parameter
    ref class G2{};
    ```

## <a name="example"></a>Örnek

Aşağıdaki örnek, tür parametrelerinde örnek yöntemleri çağırmak için kısıtlamalar kullanmayı gösterir.

```cpp
// generics_constraints_5.cpp
// compile with: /clr
using namespace System;

interface class IAge {
   int Age();
};

ref class MyClass {
public:
   generic <class ItemType> where ItemType : IAge
   bool isSenior(ItemType item) {
      // Because of the constraint,
      // the Age method can be called on ItemType.
      if (item->Age() >= 65)
         return true;
      else
         return false;
   }
};

ref class Senior : IAge {
public:
   virtual int Age() {
      return 70;
   }
};

ref class Adult: IAge {
public:
   virtual int Age() {
      return 30;
   }
};

int main() {
   MyClass^ ageGuess = gcnew MyClass();
   Adult^ parent = gcnew Adult();
   Senior^ grandfather = gcnew Senior();

   if (ageGuess->isSenior<Adult^>(parent))
      Console::WriteLine("\"parent\" is a senior");
   else
      Console::WriteLine("\"parent\" is not a senior");

   if (ageGuess->isSenior<Senior^>(grandfather))
      Console::WriteLine("\"grandfather\" is a senior");
   else
      Console::WriteLine("\"grandfather\" is not a senior");
}
```

```Output
"parent" is not a senior
"grandfather" is a senior
```

## <a name="example"></a>Örnek

Genel tür parametresi kısıtlaması olarak kullanıldığında, çıplak tür kısıtlaması olarak adlandırılır. Çıplak tür kısıtlamaları kendi tür parametresi olan bir üye işlev bu tür parametresi kapsayan tür parametresi sınırlamak gerektiğinde kullanışlıdır.

Aşağıdaki örnekte, `T` bağlamında bir çıplak tür kısıtlaması `Add` yöntemi.

Çıplak tür kısıtlamaları genel sınıfı tanımlarında da kullanılabilir. Öğesinden türetilen dışında derleyici bir çıplak tür kısıtlaması hakkında hiçbir şey kabul edilebilir olduğundan çıplak tür kısıtlamaları genel sınıflarla kullanışlılığını sınırlıdır <xref:System.Object>. Genel sınıflar çıplak tür kısıtlamaları, iki tür parametreleri arasında bir devralma ilişkisi uygulamak istediğiniz senaryolarda kullanın.

```cpp
// generics_constraints_6.cpp
// compile with: /clr /c
generic <class T>
ref struct List {
   generic <class U>
   where U : T
   void Add(List<U> items)  {}
};

generic <class A, class B, class C>
where A : C
ref struct SampleClass {};
```

## <a name="see-also"></a>Ayrıca Bkz.

[Genel Türler](../windows/generics-cpp-component-extensions.md)