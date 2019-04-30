---
title: özellik (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- property_cpp
- property
helpviewer_keywords:
- property keyword [C++]
ms.assetid: cc79d2b2-f013-4d81-8252-eece97a18704
ms.openlocfilehash: 8ec76db37cffb1b3d15447165300bedf1a8771c9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374203"
---
# <a name="property--ccli-and-ccx"></a>özellik (C++/CLI ve C++/CX)

Bildiren bir *özelliği*, görür ve bir veri üyesi veya bir dizi öğesine gibi erişilen bir üye işlev olduğu.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

Özellikleri aşağıdaki türlerden biri bildirebilirsiniz.

*Basit özellik*<br/>
Varsayılan olarak, oluşturur bir *set erişimcisine* özellik değeri atar bir *get erişimcisine* özellik değeri ve özellik değerini içeren bir derleyicinin ürettiği özel veri üyesi alır.

*özelliği bloğu*<br/>
Kullanıcı tanımlı get oluşturun ve/veya set erişimcileri için bunu kullanın. Her iki okuma/yazma özelliği olan get ve set erişimcileri, tanımlanmış, salt okunur yalnızca get erişimcisine tanımlanır ve salt yazılır yalnızca set erişimcisine tanımlanır.

Ayrıca, özellik değerini içeren bir veri üyesi açıkça belirtmesi gerekir.

*Dizinlenmiş özellik*<br/>
Bir özellik değerini ayarlamak ve almak için kullanabileceğiniz bir özelliği bloğu tarafından bir veya daha fazla dizin belirtildi.

Bir kullanıcı tarafından tanımlanan bir özellik adı ya da olan bir dizini oluşturulmuş özelliğe oluşturabilirsiniz veya *varsayılan* özellik adı. Özellik tanımlandığı sınıfın adı varsayılan bir dizin özelliği adıdır. Varsayılan özellik bildirmek için belirtin **varsayılan** anahtar sözcüğü yerine bir özellik adı.

Ayrıca, özellik değerini içeren bir veri üyesi açıkça belirtmesi gerekir. Dizinlenmiş bir özelliği, veri üyesi genellikle bir dizi veya koleksiyon hesaplanır.

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

*type*<br/>
Özellik değeri ve bu nedenle özelliği veri türü.

*property_name*<br/>
Özelliğin adı.

*erişim değiştiricisi*<br/>
Bir erişim niteleyicisi. Geçerli niteleyicileri olan **statik** ve **sanal**.

Get veya set erişimcisine üzerinde kabul **sanal** niteleyicisi ancak gerekir üzerinde kabul **statik** niteleyicisi.

*Devralma değiştiricisi*<br/>
Bir devralma niteleyicisi. Geçerli niteleyicileri olan **soyut** ve **korumalı**.

*index_list*<br/>
Bir veya daha fazla dizin virgülle ayrılmış listesi. Her dizin, dizin türü ve özellik yöntem gövdesinde kullanılan isteğe bağlı bir tanımlayıcı oluşur.

*value*<br/>
Ayarlama işleminin özelliğine atayın veya bir get işlemi almak için değer.

*property_body*<br/>
Özellik yöntemi kümesi veya get erişimcisinin gövdesi. *Property_body* kullanabilirsiniz *index_list* temel özellik veri üyesine erişmek için veya kullanıcı tanımlı işleme parametre olarak.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

Daha fazla bilgi için [özellikleri (C++/CX)](https://msdn.microsoft.com/library/windows/apps/hh755807.aspx).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

### <a name="syntax"></a>Sözdizimi

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

### <a name="parameters"></a>Parametreler

*Değiştiricisi*<br/>
Özellik bildiriminde ya da bir get/set erişimcisine yöntemi kullanılabilir değiştiricisi. Olası değerler **statik** ve **sanal**.

*type*<br/>
Özelliği tarafından temsil edilen değerin türü.

*property_name*<br/>
Raise yöntemi çağrıldı; temsilcisinin imzasıyla eşleşmelidir.

*index_list*<br/>
Belirtilen köşeli ayraç (alt simge işleci, ([])), bir veya daha fazla dizinleri virgülle ayrılmış listesi. Her dizin için özellik yöntem gövdesinde bir tür ve isteğe bağlı olarak kullanılabilecek bir tanımlayıcı belirtin.

### <a name="remarks"></a>Açıklamalar

İlk söz dizimi örnekte gösterildiği bir *basit özellik*, hangi örtük olarak bildiriyor hem de bir `set` ve `get` yöntemi. Derleyici, özellik değerini depolamak için özel bir alan otomatik olarak oluşturur.

İkinci sözdizimi örnekte gösterildiği bir *özelliği bloğu*, hangi açıkça bildirir hem de bir `set` ve `get` yöntemi.

Üçüncü sözdizimi örneği, müşteri tanımlı gösterir *dizin özelliği*. Dizin özelliğini ayarlama veya alınan değerin yanı sıra parametreleri alır. Özellik için bir ad belirtmeniz gerekir. Basit bir özelliğin aksine `set` ve/veya `get` dizin özelliğini yöntemlerinin açıkça tanımlanmalıdır ve özellik için bir ad belirtmeniz gerekir.

Dördüncü söz dizimi örnekte gösterildiği bir *varsayılan* türün bir örneğini dizi benzeri erişim sağlayan bir özellik. Anahtar sözcüğü **varsayılan**, yalnızca varsayılan bir özellik belirtmek için kullanılır. Varsayılan özelliğin adını özelliği tanımlandığı tür adıdır.

**Özelliği** anahtar sözcüğü bir sınıf, arabirim veya değer türü görünebilir. Özellik get işlevi (salt okunur), bir set işlevine (salt okunur) veya her iki (okuma ve yazma) sahip olabilir.

Bir özellik adı, onu içeren yönetilen sınıfın adı aynı olamaz. Alıcı işlevin dönüş türü, karşılık gelen bir ayarlayıcı işlevine son parametresi türüyle eşleşmesi gerekir.

İstemci kodu için bir özellik görünümü bir sıradan veri üyesi olan ve yazılan veya bir veri üyesi aynı sözdizimini kullanarak okuyabilir.

Get ve set yöntemleri üzerinde kabul **sanal** değiştiricisi.

Erişilebilirlik get ve set yöntemi gösterebileceğini.

Bir özellik yöntemi tanımı, sıradan bir yöntem gibi sınıf gövdesinin dışında görünebilir.

Üzerinde get ve set yöntemi bir özellik için kabul **statik** değiştiricisi.

Skaler bir özellik varsa, get ve set yöntemleri aşağıdaki Açıklama:

- Get yöntemi hiç parametresi yok ve dönüş türüne sahip `T`.

- Set yöntemi türünde bir parametreye sahip `T`ve dönüş türü **void**.

Olmalıdır yalnızca bir skaler özellik aynı tanımlayıcıya sahip bir kapsamda bildirilmiş. Skaler özellikler aşırı yüklenemez.

Bir özellik veri üyesi bildirildiğinde, derleyici veri üyesi eklediği — bazen "yedekleme deposu" da adlandırılır — sınıfında. İçerilen sınıfının bir gerçek veri üyesi değilmiş gibi kaynak üye başvuramaz, ancak veri üyesinin adı bir biçimidir. İldasm.exe türünüz için meta verilerini görüntüleyin ve özelliğin yedekleme deposu için derleyici tarafından oluşturulan ad görmek için kullanın.

Farklı erişilebilirlik erişimci metotlarını bir özellik bloğunda izin verilir.  Diğer bir deyişle, küme yöntemini genel olabilir ve get yöntemini özel olabilir.  Ancak, özellik bildiriminde nedir değerinden daha az kısıtlayıcı bir erişilebilirlik sağlamak bir erişimci metot için bir hata olur.

**özellik** bağlama duyarlı bir anahtar sözcüktür.  Daha fazla bilgi için [Context-Sensitive Keywords](context-sensitive-keywords-cpp-component-extensions.md).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki örnek, bildirim ve özellik veri üyesi ve özelliği bloğu kullanımını gösterir.  Ayrıca, bir özellik erişimcisi sınıf dışında tanımlanabilir gösterir.

```cpp
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

```Output
test

21
```

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)