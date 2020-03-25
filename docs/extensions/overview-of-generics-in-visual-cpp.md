---
title: /CLI içindeki C++Genel türlere genel bakış
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- generics [C++], about generics
- default initializers [C++]
- type parameters [C++]
- constructed types
- type arguments [C++]
- constructed types, open [C++]
- open constructed types [C++]
- constructed types, closed [C++]
ms.assetid: 21f10637-0fce-4916-b925-6c86a126d3aa
ms.openlocfilehash: a1a66b6464bf952a530dbf1ea188bfd681d684d0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80172080"
---
# <a name="overview-of-generics-in-ccli"></a>/CLI içindeki C++Genel türlere genel bakış

Genel türler ortak dil çalışma zamanı tarafından desteklenen parametreli türlerdir. Parametreli tür, genel kullanıldığında belirtilen bilinmeyen bir tür parametresiyle tanımlanmış bir türdür.

## <a name="why-generics"></a>Neden genel türler?

C++, şablon ve genel türler türü belirlenmiş koleksiyon sınıfları oluşturmak için parametreli türleri destekler. Ancak, şablonlar derleme zamanı Parametreleştirme sağlar. Şablon tanımı içeren bir derlemeye başvuramaz ve şablonun yeni özelleştirmelerini oluşturabilirsiniz. Derlendikten sonra, özel bir şablon başka bir sınıf veya yöntem gibi görünür. Buna karşılık, genel türler, çalışma zamanı tarafından parametreli bir tür olarak bilinen parametreli bir tür olarak MSIL 'e yayılır; genel bir tür içeren bir derlemeye başvuruda bulunan kaynak kodu, genel türde özelleştirilmiş bir tür oluşturabilir. Standart C++ şablon ve genel türlerin karşılaştırması hakkında daha fazla bilgi için bkz. [Genel türler ve şablonlarC++(/CLI)](generics-and-templates-visual-cpp.md).

## <a name="generic-functions-and-types"></a>Genel Işlevler ve türler

Sınıf türleri, yönetilen türler oldukları sürece genel olabilir. Buna bir örnek `List` sınıf olabilir. Listedeki bir nesnenin türü tür parametresidir. Birçok farklı nesne türü için bir `List` sınıfı gerekliyse, genel türler öncesinde öğe türü olarak `System::Object` alan bir `List` kullanmış olabilirsiniz. Ancak bu, listede (yanlış türde nesneler dahil) bir nesnenin kullanılmasına izin verir. Böyle bir listeye türsüz bir koleksiyon sınıfı denir. En iyi yöntem, çalışma zamanında türü denetleyebilir ve bir özel durum oluşturabilir. Ya da, bir derlemeye derlendikten sonra genel kalitesini kaybedecek bir şablon kullanmış olabilirsiniz. Derlemelerinizin tüketicileri, şablonun kendi uzmanlarını oluşturamadı. Genel türler, bir derlemenin yazılı koleksiyona kabul etmek üzere tasarlanmadığı bir tür koymaya çalıştığınızda bir derleme zamanı hatası oluşturacak şekilde, türü belirtilmiş koleksiyon sınıfları oluşturmanıza, `List<int>` ("int listesi") ve `List<double>` ("Double listesi") oluşturmanızı sağlar. Ayrıca, bu türler derlendikten sonra genel kalır.

Genel sınıfların sözdizimi açıklaması [genel sınıflarda (C++/CLI)](generic-classes-cpp-cli.md)bulunabilir. <xref:System.Collections.Generic>yeni bir ad alanı, <xref:System.Collections.Generic.Dictionary%602>, <xref:System.Collections.Generic.List%601> ve <xref:System.Collections.Generic.LinkedList%601>dahil parametreli bir koleksiyon türleri kümesi sunar.

Hem örnek hem de statik sınıf üyesi işlevleri, temsilciler ve genel işlevler de genel olabilir. İşlevin parametreleri bilinmeyen bir türse veya işlevin kendisi genel türlerle çalışsa genel işlevler gerekli olabilir. `System::Object`, geçmişte bilinmeyen bir nesne türü için bir parametre olarak kullanılmış olabileceği birçok durumda, bunun yerine genel bir tür parametresi kullanılabilir ve daha fazla tür kullanımı uyumlu kod sağlar. İşlevin tasarlanmadığı bir tür, derleme zamanında bir hata olarak işaretlenir. İşlev parametresi olarak `System::Object` kullanarak, işlevin ilgilenmesi amaçlanmayan bir nesnenin yanlışlıkla geçirilmesiyle algılanmayabilir ve bilinmeyen nesne türünü işlev gövdesinde belirli bir türe ve bir InvalidCastException olasılığa karşı hesaba atamalısınız. Genel olarak, bir nesneyi işleve geçirmeye çalışan kod bir tür çakışmasına neden olur, bu nedenle işlev gövdesinin doğru türde olması garanti edilir.

Aynı avantajlar, genel türler üzerinde oluşturulmuş koleksiyon sınıfları için de geçerlidir. Geçmişte koleksiyon sınıfları, öğeleri bir koleksiyonda depolamak için `System::Object` kullanır. Koleksiyonun tasarlanmadığı bir türün nesne ekleme, derleme zamanında bayrak eklenmemiş ve genellikle nesneler eklendiğinde bile değil. Genellikle, bir nesne koleksiyonda erişildiği zaman başka bir türe de dönüşebilir. Yalnızca atama başarısız olduğunda beklenmeyen tür algılanır. Genel türler, Genel koleksiyonun tür parametresine eşleşmeyen (veya örtük olarak Dönüştürülmeyen) bir tür ekleyen kodu algılayarak derleme zamanında bu sorunu çözer.

Sözdiziminin açıklaması için bkz. [genel işlevler (C++/CLI)](generic-functions-cpp-cli.md).

## <a name="terminology-used-with-generics"></a>Genel türler Ile kullanılan terminoloji

### <a name="type-parameters"></a>Tür ParameTReleri

Genel bildirim, *tür parametreleri*olarak bilinen bir veya daha fazla bilinmeyen tür içeriyor. Tür parametrelerine, genel bildirimin gövdesinde türü temsil eden bir ad verilir. Tür parametresi, genel bildirimin gövdesinde bir tür olarak kullanılır. `List<T>` için genel bildirim T tür parametresini içerir.

### <a name="type-arguments"></a>Tür bağımsız değişkenleri

*Tür bağımsız değişkeni* , genel, belirli bir tür veya türler için özelleştirilse tür parametresi yerine kullanılan gerçek türdür. Örneğin, **int** `List<int>`tür bağımsız değişkenidir. Değer türleri ve tanıtıcı türleri, içinde genel tür bağımsız değişkeni olarak izin verilen tek türlerdir.

### <a name="constructed-type"></a>Oluşturulan tür

Genel bir türden oluşturulan bir türe, *oluşturulan tür*olarak başvurulur. `List<T>` gibi tam belirtilmemiş bir tür, *açık bir oluşturulmuş türdür*; `List<double>,` gibi tam olarak belirtilen bir tür, *Kapalı oluşturulmuş bir tür* veya *özel tür*olur. Açık oluşturulmuş türler diğer genel türlerin veya yöntemlerin tanımında kullanılabilir ve kapsayan genel belirtilmediği sürece tam olarak belirtilemez. Örneğin, bir genel için temel sınıf olarak açık oluşturulmuş bir türün kullanımı aşağıda verilmiştir:

```cpp
// generics_overview.cpp
// compile with: /clr /c
generic <typename T>

ref class List {};

generic <typename T>

ref class Queue : public List<T> {};
```

### <a name="constraint"></a>Kısıtlaması

Kısıtlama, tür parametresi olarak kullanılabilecek türler üzerinde bir kısıtlamadır. Örneğin, belirli bir genel sınıf yalnızca belirtilen sınıftan devraldığı veya belirtilen bir arabirimi uygulayan sınıfları kabul edebilir. Daha fazla bilgi için bkz. [genel tür parametrelerindeki kısıtlamalar (C++/CLI)](constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="reference-types-and-value-types"></a>Başvuru türleri ve değer türleri

Tanıtıcı türleri ve değer türleri, tür bağımsız değişkenleri olarak kullanılabilir. Her iki türün de kullanılabileceği genel tanımında, söz dizimi başvuru türlerinden oluşur. Örneğin, `->` işleci, sonunda kullanılan türün bir başvuru türü veya değer türü olup olmadığı, tür parametresinin üyelerine erişmek için kullanılır. Tür bağımsız değişkeni olarak bir değer türü kullanıldığında, çalışma zamanı değer türlerini kutulama olmadan doğrudan değer türlerini kullanan kodu oluşturur.

Bir başvuru türünü genel tür bağımsız değişkeni olarak kullanırken, tanıtıcı sözdizimini kullanın. Bir değer türünü genel tür bağımsız değişkeni olarak kullanırken, doğrudan türün adını kullanın.

```cpp
// generics_overview_2.cpp
// compile with: /clr
generic <typename T>

ref class GenericType {};
ref class ReferenceType {};

value struct ValueType {};

int main() {
    GenericType<ReferenceType^> x;
    GenericType<ValueType> y;
}
```

## <a name="type-parameters"></a>Tür ParameTReleri

Genel bir sınıftaki tür parametreleri diğer tanımlayıcılar gibi değerlendirilir. Ancak, tür bilinmiyorsa, kullanımları üzerinde kısıtlamalar vardır. Örneğin, tür parametresi bu üyeleri destekleyecek şekilde bilinmediği takdirde tür parametre sınıfının üyelerini ve yöntemlerini kullanamazsınız. Diğer bir deyişle, tür parametresi aracılığıyla bir üyeye erişmek için, üyeyi içeren türü tür parametresinin kısıtlama listesine eklemeniz gerekir.

```cpp
// generics_overview_3.cpp
// compile with: /clr
interface class I {
   void f1();
   void f2();
};

ref struct R : public I {
   virtual void f1() {}
   virtual void f2() {}
   virtual void f3() {}
};

generic <typename T>
where T : I
void f(T t) {
   t->f1();
   t->f2();
   safe_cast<R^>(t)->f3();
}

int main() {
   f(gcnew R());
}
```

Bu kısıtlamalar operatörler için de geçerlidir. Kısıtlanmış olmayan genel tür parametresi, türün bu işleçleri desteklemediği durumlarda tür parametresinin iki örneğini karşılaştırmak için `==` ve `!=` işleçlerini kullanamaz. Bu denetimler, genel türler için gereklidir, ancak şablonlar için değildir, çünkü genel türler, geçersiz üyelerin kullanımını denetlemek için çok geç olduğunda, kısıtlamaları karşılayan herhangi bir sınıfla çalışma zamanında özelleştirilebilir.

Tür parametresinin varsayılan bir örneği, `()` işleci kullanılarak oluşturulabilir. Örneğin:

`T t = T();`

`T`, genel bir sınıfta veya yöntem tanımında bir tür parametresidir, değişkeni varsayılan değerine başlatır. `T` bir başvuru sınıfınse, null bir işaretçi olacaktır; `T` bir değer sınıfındaysa, nesne sıfır olarak başlatılır. Bu, *varsayılan Başlatıcı*olarak adlandırılır.

## <a name="see-also"></a>Ayrıca bkz.

[Genel Türler](generics-cpp-component-extensions.md)
