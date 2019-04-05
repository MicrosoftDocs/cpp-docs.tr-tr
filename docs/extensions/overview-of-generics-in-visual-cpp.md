---
title: Genel türlerin yararları C + +/ CLI
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
ms.openlocfilehash: 38d33faec3610495e8cc5e97db2e81bd74be8b8b
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59034705"
---
# <a name="overview-of-generics-in-ccli"></a>Genel türlerin yararları C + +/ CLI

Genel türler, ortak dil çalışma zamanı tarafından desteklenen parametreli türleridir. Parametreli bir tür genel kullanıldığında, belirttiğiniz bir bilinmeyen tür parametresi ile tanımlanan bir türdür.

## <a name="why-generics"></a>Neden genel türler?

C++ şablonları ve her iki şablonları destekler ve genel türler parametreli türler belirlenmiş koleksiyon sınıfları oluşturmak için destek. Ancak, derleme zamanı Parametreleştirme şablonları sağlar. Bir şablon tanımı içeren bir derleme başvurusu olamaz ve yeni şablon uzmanlıkları oluşturun. Derlenmiş sonra özel bir şablon hiçbir diğer sınıf veya yöntemi gibi görünüyor. Buna karşılık, genel türler, parametreli tür olacak şekilde çalışma zamanı tarafından bilinen parametreli bir tür MSIL'de gönderilir; genel tür içeren bir derlemeye başvuran kaynak kodu, genel tür uzmanlıklar oluşturabilirsiniz. Standart C++ şablonları ve genel türler karşılaştırma hakkında daha fazla bilgi için bkz. [genel türler ve temsilciler (C + +/ CLI)](generics-and-templates-visual-cpp.md).

## <a name="generic-functions-and-types"></a>Genel işlevler ve türleri

Yönetilen türler oldukları sürece genel sınıf türleri de olabilir. Bunun bir örneği olabilir bir `List` sınıfı. Listedeki bir nesnenin türü, tür parametresi olacaktır. Gerekirse, bir `List` birçok farklı türde kullandıysanız genel türler önce nesne için sınıf bir `List` alan `System::Object` öğe türü. Ancak, herhangi bir nesne (yanlış türde nesneler dahil) listede kullanılacak çalıştırmasına olanak tanır. Böyle bir liste yazılmamış koleksiyon sınıfı çağrılır. En iyi şekilde çalışma zamanında tür denetimi ve bir özel durum. Veya bir kez bütünleştirilmiş kod içine derlenmiş genel kalitesini kaybeder bir şablon kullanmış olabilirsiniz. Derlemenizin Tüketiciler, kendi şablon uzmanlıkları oluşturulamadı. Genel türler belirlenmiş koleksiyon sınıfları, örneğin oluşturmanıza izin `List<int>` ("İnt listesi olarak" olarak okunur) ve `List<double>` ("listesi çift") koleksiyonu olan bir tür put çalıştıysanız, bir derleme zamanı hatasıyla karşılaşırsınız yazılı kabul etmek için tasarlanmamış koleksiyonu. Ayrıca, bunlar derlendikten sonra bu tür genel kalır.

Genel sınıflar söz diziminin bir açıklama bulunabilir [Genel sınıflar (C + +/ CLI)](generic-classes-cpp-cli.md). Yeni bir ad alanı <xref:System.Collections.Generic>, parametreli koleksiyon türleri dahil olmak üzere bir dizi tanıtır <xref:System.Collections.Generic.Dictionary%602>, <xref:System.Collections.Generic.List%601> ve <xref:System.Collections.Generic.LinkedList%601>.

Hem örneği ve statik sınıf üyesi işlevleri, temsilciler ve genel işlevler ayrıca genel olabilir. İşlevin parametreleri bir bilinmeyen türde ise veya işlevin kendisi ile genel türleri çalışmanız gerekiyorsa, genel işlevler gerekli olabilir. Çoğu durumda burada `System::Object` kullanılmamış bir bilinmeyen nesne türü için bir parametre olarak geçmişte, genel tür parametresi bunun yerine, daha fazla tür kullanımı uyumlu kod için kullanılabilir. Her türlü girişim işlevi için tasarlanmamıştır bir türü geçirin derleme zamanında hata olarak işaretlenmiş. Kullanarak `System::Object` yanlışlıkla geçirme işlevi parametre olarak bir nesnenin işlev uğraşmanız hedeflenen değildi değil algılanır ve bilinmeyen nesne belirli bir türü işlev gövdesinde türüne ve hesabı olması gerekir bir InvalidCastException olasılığını. İşlev gövdesi doğru türde olması garanti edilir şekilde ile genel, bir nesne işlevine geçirebileceğimiz çalışılırken kod türü çakışma neden olur.

Genel türler üzerinde yerleşik koleksiyon sınıfları aynı avantajlar geçerlidir. Koleksiyon sınıfları geçmişte kullandığınız `System::Object` bir koleksiyondaki öğeleri depolamak için. Nesneleri bile eklendiği zaman ekleme nesne koleksiyonu için tasarlanmamıştır bir türü derleme zamanında ve genellikle işaretlenmez. Genellikle, koleksiyonda erişildiğinde bir nesne başka bir türe yayınlanması. Beklenmeyen tür cast yalnızca başarısız olduğunda algılanır. Genel türler bu sorunu çözer derleme zamanında değil aynı (veya örtük dönüştürme) bir tür ekler herhangi bir kod algılayarak genel koleksiyon tür parametresi.

Söz dizimi açıklaması için bkz: [genel işlevler (C + +/ CLI)](generic-functions-cpp-cli.md).

## <a name="terminology-used-with-generics"></a>Genel türler ile kullanılan terimler

### <a name="type-parameters"></a>Tür ParameTReleri

Bir veya daha fazla bilinmeyen türleri bilinen genel bir bildirimine içeren *tür parametrelerindeki*. Tür parametreleri türü genel bildirimi gövdesi içinden için temsil eden bir ad verilir. Tür parametresi, genel bildirimi gövdesi içinde bir tür olarak kullanılır. Genel bildirimi `List<T>` t türü parametresi içerir

### <a name="type-arguments"></a>Tür bağımsız değişkenleri

*Tür bağımsız değişkeni* genel belirli bir türü veya türleri için özel tür parametresi yerine kullanılan gerçek türüdür. Örneğin, **int** bağımsız değişken türü olarak `List<int>`. Değer türleri ve tanıtıcı türlerine izin bir genel tür bağımsız değişkeni yalnızca türleridir.

### <a name="constructed-type"></a>Oluşturulan tür

Genel bir türden oluşturulan bir tür olarak adlandırılır bir *oluşturulan türü*. Tamamen gibi belirtilen bir tür `List<T>` olduğu bir *oluşturulan tür açın*; tam olarak gibi belirtilen tür bir `List<double>,` olduğu bir *oluşturulan tür kapalı* veya *özelleştirilmiş türü* . Açık oluşturulan türler, diğer genel türleri veya yöntemleri tanımı içinde kullanılabilir ve genel kapsayan kendi belirtilen olana kadar tam olarak belirtilemez. Örneğin, aşağıdaki bir açık bir oluşturulmuş tür bir temel sınıf olarak genel amaçlıdır:

```cpp
// generics_overview.cpp
// compile with: /clr /c
generic <typename T>

ref class List {};

generic <typename T>

ref class Queue : public List<T> {};
```

### <a name="constraint"></a>Kısıtlama

Bir tür parametresi kullanılan türler bir kısıtlama sınırlamadır. Örneğin, belirli bir genel sınıfın, belirtilen bir sınıftan devralınan sınıflar kabul edin veya belirtilen bir arabirim. Daha fazla bilgi için [genel tür parametrelerindeki kısıtlamalar (C + +/ CLI)](constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="reference-types-and-value-types"></a>Başvuru türleri ve değer türleri

Tanıtıcıları türleri ve değer türleri, tür bağımsız değişkeni olarak kullanılabilir. İçinde her iki türü kullanılabilir, genel tanımında sözdizimi başvuru türlerinin olmasıdır. Örneğin, `->` işleci bir başvuru türü veya değer türü sonunda kullanılan türü olup olmadığını tür parametresi tür üyelerine erişmek için kullanılır. Tür bağımsız değişkeni bir değer türü kullanıldığında, çalışma zamanı doğrudan değer türleri kutulama olmayan değer türleri kullanan kodu oluşturur.

Bir genel tür bağımsız değişkeni bir başvuru türü kullanarak, tanıtıcı söz dizimi kullanın. Bir genel tür bağımsız değişkeni bir değer türü kullanarak, doğrudan türünün adını kullanın.

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

Genel bir sınıf türü parametreleri gibi diğer tanımlayıcılar kabul edilir. Ancak, türü bilinmediğinden, bunların kullanılması kısıtlamalar vardır. Örneğin, bu üyeleri desteklemek için tür parametresi bilinen sürece üyeleri ve tür parametresi sınıfının yöntemlerini kullanamazsınız. Diğer bir deyişle, tür parametresi aracılığıyla bir üyesine erişmek için tür parametre kısıtlaması listeye üye içeren tür eklemeniz gerekir.

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

Bu kısıtlama işleçleri de uygulanır. Sınırlandırılmamış genel tür parametresi kullanamaz `==` ve `!=` türü bu işleçleri desteklemez durumunda iki tür parametresi örneklerini karşılaştırmak için işleçler. Bu denetimler, genel türler için gereklidir, ancak genel türler, herhangi bir sınıf ile çalışma zamanında özel çünkü değil şablonları için kısıtlamalar karşılayan olduğunda çok geç için geçersiz üye kullanımını denetlemek için.

Tür parametresinin varsayılan bir örnek kullanılarak oluşturulabilir. `()` işleci. Örneğin:

`T t = T();`

Burada `T` genel bir sınıf veya yöntemin tanımındaki bir tür parametresi olduğundan, varsayılan değerine değişkenini ayarlar. Varsa `T` ise bir başvuru sınıfının bir null işaretçi; olacaktır `T` bir değer sınıfı, nesne sıfır olarak başlatılır. Bu adlı bir *Başlatıcı varsayılan*.

## <a name="see-also"></a>Ayrıca bkz.

[Genel Türler](generics-cpp-component-extensions.md)