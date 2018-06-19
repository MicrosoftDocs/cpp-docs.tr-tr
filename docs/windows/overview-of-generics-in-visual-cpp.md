---
title: Visual C++'de genel türlere genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 19200e3c3c4ed67960905b697187dbb6b37a65e9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33881009"
---
# <a name="overview-of-generics-in-visual-c"></a>Visual C++'de Genel Türlere Genel Bakış
Genel türler, ortak dil çalışma zamanı tarafından desteklenen parametreli türleridir. Genel kullanıldığında, belirttiğiniz bir bilinmeyen tür parametresi ile tanımlanan bir türü bir parametreli türüdür.  
  
## <a name="why-generics"></a>Neden genel türler?  
 C++ şablonları ve her iki şablonları destekler ve genel türler yazılan koleksiyon sınıfları oluşturmak için parametreli türler destekler. Ancak, şablonları, derleme zamanı parametrelemeyi sağlar. Bir şablon tanımını içeren bir derleme başvurusu ve şablonun yeni özelleştirmeleri oluşturun. Derlenmiş sonra özel bir şablon herhangi diğer sınıf veya yöntemin gibi görünüyor. Buna karşılık, genel türler içinde MSIL parametreli bir tür olması için çalışma zamanı tarafından bilinen parametreli bir türü gösterilen; Genel bir tür içeren bir derlemenin başvurduğu kaynak kodu özelleştirmeleri genel türü oluşturabilirsiniz. Visual C++ şablonları ve genel türler karşılaştırması hakkında daha fazla bilgi için bkz: [genel türler ve temsilciler (Visual C++)](../windows/generics-and-templates-visual-cpp.md).  
  
## <a name="generic-functions-and-types"></a>Genel işlevler ve türleri  
 Yönetilen türler oldukları sürece sınıf türleri, genel olabilir. Bunun bir örneği olabilir bir `List` sınıfı. Listedeki bir nesne türü tür parametresi olacaktır. Gerekirse bir `List` birçok farklı türde kullanmış genel türler önce nesne için sınıf bir `List` alan **System::Object** öğe türü. Ancak (yanlış türde nesneler dahil) herhangi bir nesne, listeden kullanılacak olanak tanır. Böyle bir liste türü belirsiz koleksiyon sınıfı çağrılması. En iyi çalışma zamanında tür denetleyin ve bir özel durum. Veya, bir kez bütünleştirilmiş koda derlenmemiş genel kalitesini kaybeder bir şablon kullanmış olabilirsiniz. Derlemenizi tüketicileri kendi özelleştirmeleri şablonu oluşturulamadı. Genel türler yazılan koleksiyon sınıfları deyin oluşturmanıza izin `List<int>` ("İnt listesi olarak" okunur) ve `List<double>` ("listesi çift") koleksiyon türü almaya çalıştığında, derleme zamanı hatasıyla karşılaşırsınız yazılan kabul etmek için tasarlanmamış koleksiyonu. Buna ek olarak, bunlar derlenen sonra bu tür genel kalır.  
  
 Genel sınıflar sözdizimi açıklamasını bulunabilir [Genel sınıflar (C + +/ CLI)](../windows/generic-classes-cpp-cli.md) `.` yeni bir ad alanı <xref:System.Collections.Generic>, parametreli koleksiyon türleri dahil olmak üzere bir dizi tanıtır <xref:System.Collections.Generic.Dictionary%602>, <xref:System.Collections.Generic.List%601>ve <xref:System.Collections.Generic.LinkedList%601>.  
  
 Hem örneği ve statik sınıf üyesi işlevleri, temsilciler ve genel işlevler de genel olabilir. Genel işlevler işlev parametreleri bilinmeyen türde ise ya da işlevi ile genel türleri çalışması gereken gerekli olabilir. Çoğu durumda burada **System::Object** kullanılmış olan bir bilinmeyen nesne türü için bir parametre olarak geçmişte genel tür parametresi bunun yerine, daha fazla tür kullanımı uyumlu kod için kullanılabilir. İşlevi için tasarlanmamıştır bir türdeki geçirmek için her türlü girişim derleme zamanında hata olarak işaretlenmiş. Kullanarak **System::Object** yanlışlıkla geçirme işlevi parametre olarak bir nesnenin işlevi uğraşmanız hedeflenen değildi algılanmayacağı ve belirli bir tür bilinmeyen bir nesneye türe etmesi gerekir işlev gövdesi ve bir InvalidCastException olasılığını hesabı. İşlev gövdesi doğru türde olması garanti şekilde bir genel ile türü çakışma işlevi için bir nesne geçirme girişiminde kod neden olur.  
  
 Genel türler üzerinde yerleşik koleksiyon sınıfları için aynı avantajları uygulayın. Koleksiyon sınıfları geçmişte kullandığınız **System::Object** bir koleksiyondaki öğelerin depolamak için. Nesneleri bile eklendiği zaman nesne koleksiyonu için tasarlanmamıştır türü ekleme derleme zamanında ve genellikle işaretlenmez. Koleksiyonda erişildiğinde genellikle, bir nesnenin bazı diğer türe. Yalnızca dönüştürme başarısız olduğunda beklenmeyen türü algılandı. Genel türler bu sorunu çözer derleme zamanında değil eşleşen (veya örtük olarak dönüştürmek) bir türü ekler herhangi bir kod algılayarak genel koleksiyon tür parametresi.  
  
 Sözdizimi açıklaması için bkz: [genel işlevler (C + +/ CLI)](../windows/generic-functions-cpp-cli.md).  
  
## <a name="terminology-used-with-generics"></a>Genel türler ile kullanılan terminolojisi  
  
##### <a name="type-parameters"></a>Tür ParameTReleri  
 Bir veya daha fazla bilinmeyen tür olarak bilinen bir genel bildirimini içerir *tür parametrelerindeki*. Tür parametreleri genel bildirimi gövdesi içinde türünün temsil eden bir ad verilir. Tür parametresi genel bildirimi gövdesi içinde bir tür olarak kullanılır. Genel bildirimi listesi için < T\> t parametresi içerir  
  
##### <a name="type-arguments"></a>Tür bağımsız değişkenleri  
 *Tür bağımsız değişkeni* genel belirli bir türü veya türleri için özel tür parametresi yerine kullanılan gerçek türüdür. Örneğin, `int` türü değişkeninde `List<int>`. Değer türleri ve tanıtıcı türleri izin genel tür bağımsız değişkeni olarak yalnızca türleridir.  
  
##### <a name="constructed-type"></a>Oluşturulan türü  
 Genel bir türden oluşturulan bir türü olarak adlandırılır bir *oluşturulan türü*. Tam olarak gibi belirtilen bir türü `List<T>` olan bir *oluşturulan türünü açmak*; bir tam olarak gibi belirtilen tür `List<double>,` olan bir *oluşturulan türü kapalı* veya *özelleştirilmiş türü* . Açık oluşturulan türler diğer genel türleri veya yöntemleri tanımı içinde kullanılabilir ve genel kapsayan kendisini belirtilen olana kadar tam olarak belirtilemez. Örneğin, bir kullanıma açık oluşturulan türünün temel sınıf olarak genel verilmiştir:  
  
 `// generics_overview.cpp`  
  
 `// compile with: /clr /c`  
  
 `generic <typename T>`  
  
 `ref class List {};`  
  
 `generic <typename T>`  
  
 `ref class Queue : public List<T> {};`  
  
##### <a name="constraint"></a>Kısıtlama  
 Bir kısıtlaması, bir tür parametresi kullanılabilir türleri üzerinde bir kısıtlamadır. Örneğin, verilen genel bir sınıf yalnızca belirtilen sınıftan sınıfları kabul edin veya belirtilen arabirimi uygulamalıdır. Daha fazla bilgi için bkz: [genel tür parametrelerindeki kısıtlamalar (C + +/ CLI)](../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
## <a name="reference-types-and-value-types"></a>Başvuru türleri ve değer türleri  
 Tür bağımsız değişkenleri tanıtıcıları türleri ve değer türleri kullanılabilir. İçinde her iki türü kullanılabilir, genel tanımında sözdizimi referans tür olmasıdır. Örneğin, **->** işleci sonunda kullanılan türü bir başvuru türü ya da bir değer türü olup olmadığını tür parametresi türü üyelerine erişmek için kullanılır. Tür bağımsız değişkeni olarak bir değer türü kullanıldığında, çalışma zamanı doğrudan değer türleri kutulama olmadan değer türleri kullanan kodu oluşturur.  
  
 Genel tür bağımsız değişkeni olarak bir başvuru türü kullanırken, tanıtıcı sözdizimini kullanın. Genel tür bağımsız değişkeni olarak bir değer türü kullanırken, doğrudan türünün adını kullanın.  
  
 `// generics_overview_2.cpp`  
  
 `// compile with: /clr`  
  
 `generic <typename T>`  
  
 `ref class GenericType {};`  
  
 `ref class ReferenceType {};`  
  
 `value struct ValueType {};`  
  
 `int main() {`  
  
 `GenericType<ReferenceType^> x;`  
  
 `GenericType<ValueType> y;`  
  
 `}`  
  
## <a name="type-parameters"></a>Tür ParameTReleri  
 Genel bir sınıf tür parametrelerinde gibi diğer tanımlayıcıları kabul edilir. Ancak, türü bilinmediğinden kullanımlarını kısıtlamalar vardır. Örneğin, bu üyeler desteklemek için tür parametresi bilinen sürece üyeleri ve tür parametresi sınıfı yöntemlerinin kullanamazsınız. Diğer bir deyişle, üye türü parametresi üzerinden erişmek için üye türü parametrenin kısıtlama listesine içeren tür eklemeniz gerekir.  
  
 `// generics_overview_3.cpp`  
  
 `// compile with: /clr`  
  
```  
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
  
 Bu kısıtlamaları da işleçleri için geçerlidir. Kısıtlanmamış genel tür parametresi kullanmaz `==` ve `!=` türü bu operatörlerini desteklemez durumunda tür parametresi iki örneğini karşılaştırmak için işleçler. Bu denetimler, genel türler için gereklidir, ancak olmayan şablonlar için herhangi bir sınıf ile çalışma zamanında genel türler özelleştirilmiş çünkü kısıtlamaları karşılayan olduğu zaman çok geç için geçersiz üyeleri kullanımını denetlemek için.  
  
 Tür parametresi varsayılan örneği kullanarak oluşturulabilir `()` işleci. Örneğin:  
  
 `T t = T();`  
  
 Burada `T` türü parametresi genel bir sınıf veya yöntemin tanımı'nda, varsayılan değeri değişkenine başlatır. Varsa `T` null işaretçi; olacaktır ref sınıfı ise `T` değer sınıfı nesne sıfır olarak başlatılır. Bu adlı bir *Başlatıcı varsayılan*.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel Türler](../windows/generics-cpp-component-extensions.md)