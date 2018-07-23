---
title: özellik (C++ bileşen uzantıları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- property_cpp
- property
dev_langs:
- C++
helpviewer_keywords:
- property keyword [C++]
ms.assetid: cc79d2b2-f013-4d81-8252-eece97a18704
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b763131fe91e2df2385f2c06bcba8bc759d695a1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33882712"
---
# <a name="property--c-component-extensions"></a>özellik (C++ Bileşen Uzantıları)
Bildiren bir *özelliği*, davranır ve bir veri üyesi veya bir dizi öğesine gibi erişilen üye işlevi değil.  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
 Aşağıdaki türlerden özelliklerinin bildirebilirsiniz.  
  
 *Basit özellik*  
 Varsayılan olarak, oluşturur bir *ayarlama erişimcisi* özellik değeri atar bir *get erişimcisi* özellik değeri ve özellik değerini içeren bir derleyicinin ürettiği özel veri üyesi alır.  
  
 *özelliği bloğu*  
 Kullanıcı tanımlı get oluşturma ve/veya erişimciler ayarlamak için bunu kullanın. Özelliği okuma/yazma hem ise get ve set erişimcileri, tanımlanmış, salt okunur get erişimcisine tanımlanan yalnızca ve yalnızca yazma yalnızca set erişimcisi tanımlanır.  
  
 Özellik değeri içeren bir veri üyesi açıkça bildirmeniz gerekir.  
  
 *Dizin oluşturulmuş özellik*  
 Almak ve bir özellik değeri ayarlamak için kullanabileceğiniz bir özellik blok, bir veya daha fazla dizinleri tarafından belirtilir.  
  
 Bir kullanıcı tanımlı özellik adı ya da sahip dizinlenmiş özelliğine oluşturabilirsiniz veya *varsayılan* özellik adı. Varsayılan dizin özelliği özelliği tanımlı sınıfın adını adıdır. Varsayılan bir özellik bildirmek için belirtmek `default` bir özellik adı yerine anahtar sözcük.  
  
 Özellik değeri içeren bir veri üyesi açıkça bildirmeniz gerekir. Dizinli bir özellik için veri genellikle bir dizi veya bir koleksiyon üyesidir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
property type property_name;

property type property_name { 
   access-modifier type get() inheritance-modifier {property_body}; 
   access-modifier void set(type value) inheritance-modifier {property_body};
} 

property type property_name[index_list] { 
   access-modifier type get(index_list) inheritance-modifier {property_body}; 
   access-modifier void set(index_list, value) inheritance-modifier {property_body};
} 

property type default[index_list] { 
   access-modifier type get(index_list) inheritance-modifier {property_body};
   access-modifier void set(index_list, value) inheritance-modifier {property_body};
}  
```  
  
### <a name="parameters"></a>Parametreler  
 `type`  
 Özellik değeri ve bu nedenle özelliği veri türü.  
  
 `property_name`  
 Özelliğin adı.  
  
 `access-modifier`  
 Bir erişim niteleyicisi. Geçerli niteleyicileri olan `static` ve `virtual`.  
  
 Get veya set erişimcileri olmayan üzerinde kabul `virtual` Niteleyici, ancak bunlar gerekir üzerinde kabul `static` niteleyicisi.  
  
 `inheritance-modifier`  
 Bir devralma niteleyicisi. Geçerli niteleyicileri olan `abstract` ve `sealed`.  
  
 `index_list`  
 Bir veya daha fazla dizinleri virgülle ayrılmış listesi. Bir dizin türünü ve özellik yöntemi gövdesinde kullanılan isteğe bağlı bir tanımlayıcı, her dizin oluşur.  
  
 `value`  
 Ayarlama işleminin özelliğinde atamak veya bir alma işlemi almak için değer.  
  
 `property_body`  
 Özellik yöntemi kümesi veya get erişimcisi gövdesi. `property_body` Kullanabilirsiniz `index_list` temel özelliği veri üyesi erişmek için veya kullanıcı tanımlı işleme parametre olarak.  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 Daha fazla bilgi için bkz: [özellikler (C + +/ CX)](http://msdn.microsoft.com/library/windows/apps/hh755807.aspx).  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı 
 **Sözdizimi**  
  
```cpp  
modifier property type property_name;

modifier property type property_name {
   modifier void set(type);
   modifier type get();
}
modifier property type property_name[index-list, value] {
   modifier void set(index-list, value);
   modifier type get(index-list);

modifier property type default[index];
}  
```  
  
 **Parametreler**  
  
 *Değiştirici*  
 Özellik bildirimi ya da bir get/set erişimcisi yöntemi kullanılabilir değiştiricisi. Olası değerler şunlardır: `static` ve `virtual`.  
  
 *Türü*  
 Özelliği tarafından temsil edilen değerin türü.  
  
 *property_name*  
 Artırma yöntemi için parametre; Temsilci imza eşleşmesi gerekir.  
  
 *index_list*  
 Belirtilen köşeli ayraç (alt simge işleci, ([])), bir veya daha fazla dizinleri virgülle ayrılmış listesi. Her dizin için özellik yöntemi gövdesinde bir türü ve isteğe bağlı olarak kullanılabilir bir tanımlayıcı belirtin.  
  
 **Açıklamalar**  
  
 İlk sözdizimi örnekte gösterildiği bir *basit özellik*, hangi örtük olarak bildirir hem de bir `set` ve `get` yöntemi. Derleyici özelliğinin değeri depolamak için özel bir alan otomatik olarak oluşturur.  
  
 İkinci sözdizimi örnekte gösterildiği bir *özelliği bloğu*, hangi açıkça bildiren hem de bir `set` ve `get` yöntemi.  
  
 Müşteri tanımlı üçüncü sözdizimi örneği gösterir *dizin özelliği*. Index özelliği parametre ek olarak ayarlayın veya alınan değeri alır. Özellik için bir ad belirtmeniz gerekir. Basit bir özellik aksine `set` ve/veya `get` dizin özelliğinin yöntemlerini açıkça tanımlanmalıdır ve özellik için bir ad belirtmeniz gerekir.  
  
 Dördüncü sözdizimi örnekte gösterildiği bir *varsayılan* türünün bir örneği için dizi benzeri erişim sağlayan bir özellik. Anahtar sözcüğü `default`, yalnızca varsayılan bir özellik belirtmek için kullanılır. Özellik tanımlandığı türünün adı varsayılan özelliği adıdır.  
  
 `property` Anahtar sözcüğü bir sınıf, arabirim veya değer türü görünebilir. Bir özellik bir get işlev (salt okunur), bir set işlevi (salt okunur) veya her iki (okuma-yazma) olabilir.  
  
 Bir özellik adı içerdiği yönetilen sınıf adı aynı olamaz. Alıcı işlevinin dönüş türü, karşılık gelen ayarlayıcı işlevinin son parametresi türü eşleşmelidir.  
  
 İstemci kodu için bir özellik bir sıradan veri üyesi görünümünü sahiptir ve yazılan veya veri üyesi olarak aynı sözdizimini kullanarak okuyabilir.  
  
 Alma ve ayarlama yöntemleri olmayan üzerinde kabul `virtual` değiştiricisi.  
  
 Get erişilebilirliğini ve ayarlama yöntemi farklılıklar.  
  
 Bir özellik yöntemini tanımı sınıf gövdesi, normal bir yöntem gibi dışında yer alabilir.  
  
 Get ve bir özellik kümesi yöntemi üzerinde kabul **statik** değiştiricisi.  
  
 Skaler bir özellik varsa, get ve ayarlama yöntemleri aşağıdaki Açıklama:  
  
-   Get yöntemini hiç parametre yok ve dönüş türüne sahip `T`.  
  
-   Set yöntemi türünde bir parametreye sahip `T`ve dönüş türü **void**.  
  
 Var olacaktır tek aynı tanımlayıcıyla bir kapsamda skaler özellik bildirilmedi. Skaler özellikler aşırı yüklenemez.  
  
 Bir özellik veri üyesi bildirilmişse derleyici veri üyesi yerleştirir — bazen "yedekleme deposu" olarak da adlandırılır — sınıfında. Sağlayacak şekilde kapsayan sınıfı gerçek veri üyesi değilmiş gibi kaynak üye başvuramaz. ancak, veri üyenin adını biçimidir. İldasm.exe türünüz için meta verileri görüntülemek ve özelliğin yedekleme deposu için derleyici tarafından üretilen ad görmek için kullanın.  
  
 Farklı erişilebilirlik özelliği bloğundaki erişimci yöntemleri için izin verilir.  Diğer bir deyişle, ayarlama yöntemi ortak olabilir ve get yöntemini özel olabilir.  Ancak, bir hata bildiriminde özellik nedir daha az kısıtlayıcı bir erişilebilirlik sağlamak bir erişimci yöntemi için gerekir.  
  
 `property` bağlama duyarlı bir anahtar sözcüktür.  Daha fazla bilgi için bkz: [Context-Sensitive anahtar sözcükleri](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
### <a name="examples"></a>Örnekler  
 Aşağıdaki örnek, bildirim ve bir özellik veri üyesi ve özellik blok kullanımını gösterir.  Ayrıca, bir özellik erişimcisini sınıfı dışında tanımlanabilir gösterir.  
  
```  
// mcppv2_property.cpp  
// compile with: /clr  
using namespace System;  
public ref class C {  
   int MyInt;  
public:  
  
   // property data member  
   property String ^ Simple_Property;  
  
   // property block  
   property int Property_Block {  
  
      int get();  
  
      void set(int value) {  
         MyInt = value;  
      }  
   }  
};  
  
int C::Property_Block::get() {  
   return MyInt;  
}  
  
int main() {  
   C ^ MyC = gcnew C();  
   MyC->Simple_Property = "test";  
   Console::WriteLine(MyC->Simple_Property);  
  
   MyC->Property_Block = 21;  
   Console::WriteLine(MyC->Property_Block);  
}  
```  
  
 **Output**  
  
```Output  
test  
  
21  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)