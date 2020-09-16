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
ms.openlocfilehash: 829f11c9f0c3935f9a415cae381cfc12d88df18a
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686762"
---
# <a name="constraints-on-generic-type-parameters-ccli"></a>Genel Tür Parametrelerindeki Kısıtlamalar (C++/CLI)

Genel tür veya yöntem bildirimlerinde, bir tür parametresini kısıtlamalarla niteleyebilirsiniz. Kısıtlama, tür bağımsız değişkenleri olarak kullanılan türlerin karşılaması gereken gereksinimdir. Örneğin, bir kısıtlama, tür bağımsız değişkeninin belirli bir arabirimi uygulaması veya belirli bir sınıftan devralması olması olabilir.

Kısıtlamalar isteğe bağlıdır; bir parametre üzerinde kısıtlama belirtilmemelidir, bu parametreyi ile kısıtlayan ile eşdeğerdir <xref:System.Object> .

## <a name="syntax"></a>Söz dizimi

```cpp
where type-parameter: constraint list
```

### <a name="parameters"></a>Parametreler

*tür parametresi*<br/>
Kısıtlanmış olacak tür parametrelerinden biri.

*kısıtlama listesi*<br/>
*kısıtlama listesi* , kısıtlama belirtimlerinin virgülle ayrılmış listesidir. Listede tür parametresi tarafından uygulanacak arabirimler bulunabilir.

Liste ayrıca bir sınıf içerebilir. Bir temel sınıf kısıtlamasını karşılamak için tür bağımsız değişkeninin, kısıtlamayla aynı sınıf olması veya kısıtlamadan türetmeniz gerekir.

Ayrıca, tür bağımsız değişkeninin Ortak parametresiz oluşturucuya sahip olması gerektiğini belirtmek için **gcnew ()** belirtebilirsiniz; ya da tür bağımsız değişkenini belirten başvuru **sınıfı** , herhangi bir sınıf, arabirim, temsilci veya dizi türü dahil olmak üzere bir başvuru türü olmalıdır; ya da tür bağımsız değişkenini belirten **değer sınıfı** bir değer türü olmalıdır. Nullable dışında herhangi bir değer türü \<T> belirtilebilir.

Ayrıca, kısıtlama olarak genel bir parametre belirtebilirsiniz. Kısıtlayan tür için sağlanan tür bağımsız değişkeni, kısıtlama türünden olmalı veya türetilmelidir. Bu, naked tür kısıtlaması olarak adlandırılır.

## <a name="remarks"></a>Açıklamalar

Kısıtlama yan tümcesi, tür parametresindeki kısıtlamanın yapısını belirten bir tür parametresi, iki nokta üst üste (**:**) ve kısıtlama olan **WHERE** işaretinden oluşur. **, bağlama** duyarlı bir anahtar sözcüktür; daha fazla bilgi için bkz. [bağlama duyarlı anahtar sözcükler](context-sensitive-keywords-cpp-component-extensions.md) . Birden çok **WHERE** yan tümcesini bir boşluk ile ayırın.

Kısıtlamalar, genel bir tür veya yöntem için bağımsız değişken olarak kullanılabilecek türlere sınırlamalar yerleştirmek için tür parametrelerine uygulanır.

Sınıf ve arabirim kısıtlamaları bağımsız değişken türlerinin belirtilen bir sınıftan olması veya bu sınıftan devralması veya belirtilen bir arabirimi uygulaması gerektiğini belirtir.

Kısıtlamaların genel bir tür veya yönteme uygulanması, kısıtlanmış türlerin bilinen özelliklerinden yararlanmak için bu tür veya yöntemdeki kodun kullanılmasına izin verir. Örneğin, türü parametresi arabirimini uygulayan genel bir sınıf bildirebilirsiniz `IComparable<T>` :

```cpp
// generics_constraints_1.cpp
// compile with: /c /clr
using namespace System;
generic <typename T>
where T : IComparable<T>
ref class List {};
```

Bu kısıtlama, için kullanılan bir tür bağımsız değişkeninin `T` `IComparable<T>` derleme zamanında kullanılmasını gerektirir. Ayrıca, gibi arabirim yöntemlerine de izin verir `CompareTo` . Arabirim yöntemlerini çağırmak için tür parametresinin bir örneğinde atama gerekmez.

Tür bağımsız değişkeninin sınıfındaki statik yöntemler tür parametresi aracılığıyla çağrılamaz; Bunlar yalnızca gerçek adlandırılmış tür aracılığıyla çağrılabilir.

Kısıtlama, veya gibi yerleşik türler dahil olmak üzere bir değer türü olamaz **`int`** **`double`** . Değer türlerinin türetilmiş sınıfları olmadığından, kısıtlamayı yalnızca bir sınıf karşılayamaz. Bu durumda, genel olarak tür parametresi, belirli değer türü ile değiştirilmiş olabilir.

Bir yöntem, bilinmeyen türün yöntemleri veya arabirimleri desteklediğini belirtmediği takdirde, bazı durumlarda derleyici yöntemlerin veya bilinmeyen bir türün diğer özelliklerinin kullanılmasına izin vermediğinden, bu kısıtlamalar gereklidir.

Aynı tür parametresi için birden çok kısıtlama, virgülle ayrılmış bir listede belirtilebilir

```cpp
// generics_constraints_2.cpp
// compile with: /c /clr
using namespace System;
using namespace System::Collections::Generic;
generic <typename T>
where T : List<T>, IComparable<T>
ref class List {};
```

Birden çok tür parametresiyle, her tür parametresi için bir **WHERE** yan tümcesi kullanın. Örneğin:

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

Özetlemek gerekirse, aşağıdaki kurallara göre kodunuzda kısıtlamalar kullanın:

- Birden çok kısıtlama listeleniyorsa, kısıtlamalar herhangi bir sırada listelenebilir.

- Kısıtlamalar, soyut temel sınıflar gibi sınıf türleri de olabilir. Ancak, kısıtlamalar değer türleri veya mühürlü sınıflar olamaz.

- Kısıtlamalar tür parametreleri olamaz, ancak tür parametrelerini açık oluşturulmuş bir tür içinde içerebilir. Örneğin:

    ```cpp
    // generics_constraints_4.cpp
    // compile with: /c /clr
    generic <typename T>
    ref class G1 {};

    generic <typename Type1, typename Type2>
    where Type1 : G1<Type2>   // OK, G1 takes one type parameter
    ref class G2{};
    ```

## <a name="examples"></a>Örnekler

Aşağıdaki örnek, tür parametrelerinde örnek yöntemleri çağırmak için kısıtlamaları kullanmayı gösterir.

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

Bir genel tür parametresi kısıtlama olarak kullanıldığında, naked tür kısıtlaması olarak adlandırılır. Çıplak tür kısıtlamaları, kendi tür parametresine sahip bir üye işlevin bu parametreyi kapsayan türün tür parametresiyle kısıtması gerektiğinde faydalıdır.

Aşağıdaki örnekte, `T` yöntemi bağlamında çıplak bir tür kısıtlamadır `Add` .

Naked tür kısıtlamaları, genel sınıf tanımlarında da kullanılabilir. Derleyici, genel sınıflarla çıplak tür kısıtlamalarının kullanışlılığı sınırlıdır, çünkü derleyici bir çıplak tür kısıtlaması hakkında, öğesinden türetilmediği hariç hiçbir şey kabul edebilir <xref:System.Object> . İki tür parametresi arasında bir devralma ilişkisi uygulamak istediğiniz senaryolarda genel sınıflarda çıplak tür kısıtlamalarını kullanın.

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

## <a name="see-also"></a>Ayrıca bkz.

[Genel Türler](generics-cpp-component-extensions.md)
