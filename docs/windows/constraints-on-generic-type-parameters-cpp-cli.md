---
title: Tür parametrelerindeki genel kısıtlamalar (C + +/ CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- where
dev_langs:
- C++
helpviewer_keywords:
- where keyword [C++]
- constraints, C++
ms.assetid: eb828cc9-684f-48a3-a898-b327700c0a63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c9787eb87ab701d067762a436d92b2fba3fabcbb
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="constraints-on-generic-type-parameters-ccli"></a>Genel Tür Parametrelerindeki Kısıtlamalar (C++/CLI)
Genel tür veya yöntem bildirimleri, tür parametresi kısıtlamaları olan uygun bulabilirsiniz. Bir kısıtlama tür bağımsız değişkenleri kullanılan türleri getirmelidir bir gereksinimdir. Örneğin, bir kısıtlama tür bağımsız değişkeni bir belirli arabirimini uygulaması gerekir veya belirli bir sınıftan olabilir.  
  
 Kısıtlamalar isteğe bağlıdır; bir kısıtlama bir parametre belirtmeden bu parametreye sınırlama için eşdeğer <xref:System.Object>.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
where type-parameter: constraint list  
```  
  
#### <a name="parameters"></a>Parametreler  
 *tür parametresi*  
 Kısıtlanacak tür parametreleri biri.  
  
 *sınırlama listesi*  
 *sınırlama listesi* kısıtlaması belirtimleri virgülle ayrılmış listesi. Liste türü parametresi tarafından uygulanacak arabirim içerebilir.  
  
 Listeden bir sınıf de içerir. Bir temel sınıf kısıtlamasını tür bağımsız değişkeni için kısıtlaması türetilen veya kısıtlaması ile aynı sınıfta olması gerekir.  
  
 Ayrıca belirtebilirsiniz `gcnew()` tür bağımsız değişkeni bir public parametresiz oluşturucu; olmalıdır belirtmek için veya `ref class` tür bağımsız değişkeni, sınıf, arabirim, temsilci veya dizi türü; dahil olmak üzere bir başvuru türü olmalıdır belirtmek için veya `value class` için tür bağımsız değişkeni bir değer türü olmalıdır gösterir. Herhangi bir değer türü null atanabilir dışında\<T > belirtilebilir.  
  
 Ayrıca bir kısıtlama olarak genel parametresini belirtebilirsiniz. Sınırlama türü için sağlanan tür bağımsız değişkeni olması veya kısıtlama türünden türemesi gerekir. Bu, çıplak tür sınırlaması olarak adlandırılır.  
  
## <a name="remarks"></a>Açıklamalar  
 Kısıtlama yan tümcesi oluşan **nerede** tür parametresi tarafından bir iki nokta üst üste ve ardından (**:**), tür parametresi kısıtlama yapısını belirtir kısıtlama. **Burada** bağlama duyarlı bir anahtar sözcüktür; bkz [Context-Sensitive anahtar sözcükleri](../windows/context-sensitive-keywords-cpp-component-extensions.md) daha fazla bilgi için. Birden çok ayrı **burada** yan tümceleri bir alana sahip.  
  
 Tür kısıtlamaları genel türü veya yöntemi için bağımsız değişken olarak kullanılan türleri yerleştirmek için parametreleri kısıtlamalar uygulanır.  
  
 Sınıf ve arabirim kısıtlamaları bağımsız değişken türleri gerekir olabilir veya belirtilen sınıftan veya belirtilen arabirimini uygulayan olduğunu belirtin.  
  
 Uygulamaya kısıtlamaları genel türü veya yöntemi türü veya yöntemi kısıtlanmış türdeki bilinen özelliklerden yararlanmak için kod sağlar. Örneğin, tür parametresi uygular, genel bir sınıf bildirebilir **IComparable\<T >** arabirimi:  
  
```  
// generics_constraints_1.cpp  
// compile with: /c /clr  
using namespace System;  
generic <typename T>  
where T : IComparable<T>  
ref class List {};  
```  
  
 Tür bağımsız değişkeni için kullanılan bu kısıtlamayı gerektirir `T` uygulayan `IComparable<T>` derleme zamanında. Arabirim yöntemleri de gibi sağlar **CompareTo**, çağrılabilir. Tür atama yok tür parametresi örneğini arabirim yöntemleri çağırmak için gereklidir.  
  
 Tür bağımsız değişkeninin sınıftaki statik yöntemler tür parametresi üzerinden çağrılamaz; yalnızca gerçek adlandırılmış türü ile çağrılamaz.  
  
 Bir kısıtlama gibi yerleşik türleri dahil olmak üzere bir değer türü olamaz `int` veya **çift**. Türetilmiş sınıflar değer türleri olamaz olduğundan, yalnızca bir sınıf herhangi bir zamanda kısıtlamasını mümkün olacaktır. Bu durumda, belirli bir değerin türü tarafından değiştirilen tür parametresi ile genel yazılabilir.  
  
 Bilinmeyen tür yöntemleri veya arabirimlerini desteklediğini kısıtlamaları kapsıyor sürece derleyici yöntemlerinin kullanımını veya diğer özellikler bilinmeyen bir türde izin vermez beri kısıtlamaları bazı durumlarda gereklidir.  
  
 Virgülle ayrılmış bir listede aynı tür parametresi için birden çok kısıtlama belirtilebilir.  
  
```  
// generics_constraints_2.cpp  
// compile with: /c /clr  
using namespace System;  
using namespace System::Collections::Generic;  
generic <typename T>  
where T : List<T>, IComparable<T>  
ref class List {};  
```  
  
 Birden çok tür parametreleri ile kullanmayı **burada** yan tümcesi için her tür parametresi. Örneğin:  
  
```  
// generics_constraints_3.cpp  
// compile with: /c /clr  
using namespace System;  
using namespace System::Collections::Generic;  
  
generic <typename K, typename V>  
   where K: IComparable<K>  
   where V: IComparable<K>  
ref class Dictionary {};  
```  
  
 Özetlemek için aşağıdaki kurallara göre kodunuzda kısıtlamaları kullanın:  
  
-   Birden çok kısıtlama listelenmiyorsa, kısıtlamalar herhangi bir sırada listelenebilir.  
  
-   Kısıtlamaları soyut taban sınıfları gibi sınıf türleri de olabilir. Ancak, sınırlamalar değer türleri veya sealed sınıfları olamaz.  
  
-   Kısıtlamaları kendilerini tür parametreleri olamaz, ancak bir açık oluşturulan türü tür parametrelerinde içerebilir. Örneğin:  
  
    ```  
    // generics_constraints_4.cpp  
    // compile with: /c /clr  
    generic <typename T>  
    ref class G1 {};  
  
    generic <typename Type1, typename Type2>  
    where Type1 : G1<Type2>   // OK, G1 takes one type parameter  
    ref class G2{};  
    ```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, tür parametreleri örnek yöntemleri çağırmak için kısıtlamaları kullanma gösterilmektedir.  
  
```  
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
 Genel tür parametresi bir kısıtlama olarak kullanıldığında, çıplak türü kısıtlaması adı verilir. Naked türü kısıtlamaları içeren türde tür parametresi bu parametreye sınırlamak kendi tür parametresi üye işleviyle ihtiyacı olduğunda faydalıdır.  
  
 Aşağıdaki örnekte, T, ekleme yöntemi bağlamında bir çıplak türü sınırlamadır.  
  
 Naked türü kısıtlamaları da genel bir sınıf tanımlarında kullanılabilir. Genel sınıflar ile çıplak türü kısıtlamaları yararlılığı den türemesi dışında derleyici naked tür sınırlaması hakkında hiçbir şey kabul edilebilir olduğundan sınırlıdır <xref:System.Object>. Genel sınıflar naked türü kısıtlamalar, iki tür parametreleri arasında bir devralma ilişkisi uygulamak istediğiniz senaryolarda kullanın.  
  
```  
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