---
title: Özellik (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- property keyword [C++]
ms.assetid: cc79d2b2-f013-4d81-8252-eece97a18704
ms.openlocfilehash: b961a93628752b11cd1d147268a4947acf29f67a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80171982"
---
# <a name="property--ccli-and-ccx"></a>Özellik (C++/CLI ve C++/CX)

Bir veri üyesi veya dizi öğesi gibi davranan ve erişilen bir üye işlev olan bir *özellik*bildirir.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

Aşağıdaki özellik türlerinden birini bildirebilirsiniz.

*Simple özelliği*<br/>
Varsayılan olarak, özellik değerini atayan bir *set erişimcisi* , özellik değerini alan bir *get erişimcisi* ve özellik değerini içeren derleyicinin ürettiği özel veri üyesi oluşturur.

*özellik bloğu*<br/>
Kullanıcı tanımlı get ve/veya set erişimcileri oluşturmak için bunu kullanın. Get ve set erişimcileri tanımlanmazsa ve yalnızca set erişimcisi tanımlanmışsa salt yazılır olduğunda, özelliği okuma/yazma işlemi yapılır.

Özellik değerini içeren bir veri üyesini açıkça bildirmeniz gerekir.

*dizinli özellik*<br/>
Bir veya daha fazla dizin tarafından belirtilen bir özellik değerini almak ve ayarlamak için kullanabileceğiniz bir özellik bloğu.

Kullanıcı tanımlı özellik adı veya *varsayılan* Özellik adı olan dizinli bir özellik oluşturabilirsiniz. Varsayılan dizin özelliğinin adı, özelliğin tanımlandığı sınıfın adıdır. Varsayılan bir özellik bildirmek için, özellik adı yerine **varsayılan** anahtar sözcüğü belirtin.

Özellik değerini içeren bir veri üyesini açıkça bildirmeniz gerekir. Dizinli bir özellik için, veri üyesi genellikle bir dizi veya koleksiyondur.

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
Özellik değerinin veri türü ve sonuç olarak özelliği.

*property_name*<br/>
Özelliğin adı.

*erişim-değiştirici*<br/>
Erişim niteleyicisi. Geçerli niteleyiciler **statik** ve **sanal**.

Get veya set erişimcileri **sanal** niteleyiciyi kabul etmemelidir, ancak **statik** niteleyiciyi kabul etmelidir.

*devralma-Değiştirici*<br/>
Devralma niteleyicisi. Geçerli niteleyiciler **abstract** ve **Sealed**.

*index_list*<br/>
Bir veya daha fazla dizinin virgülle ayrılmış listesi. Her dizin bir dizin türünden ve özellik yöntemi gövdesinde kullanılabilecek bir isteğe bağlı tanımlayıcıyla oluşur.

*value*<br/>
Bir küme işleminde özelliğe atanacak değer veya alma işlemini alma.

*property_body*<br/>
Set veya Get erişimcisinin özellik yöntemi gövdesi. *Property_body* , temel özellik veri üyesine erişmek için *index_list* veya Kullanıcı tanımlı işlemede parametreler olarak kullanabilir.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

Daha fazla bilgi için bkz. [ÖzelliklerC++(/CX)](../cppcx/properties-c-cx.md).

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

*icisi*<br/>
Bir özellik bildiriminde veya get/set erişimci yönteminde kullanılabilen bir değiştirici. Olası değerler **statiktir** ve **sanal**.

*type*<br/>
Özelliği tarafından temsil edilen değerin türü.

*property_name*<br/>
Raise yöntemi için parametreler; temsilcinin imzasıyla aynı olmalıdır.

*index_list*<br/>
Köşeli ayraçlar içinde belirtilen bir veya daha fazla dizinin virgülle ayrılmış listesi (alt simge işleci ([])). Her dizin için, bir tür ve isteğe bağlı olarak özellik yöntemi gövdesinde kullanılabilecek bir tanımlayıcı belirtin.

### <a name="remarks"></a>Açıklamalar

İlk sözdizimi örneği, hem `set` hem de `get` yöntemini dolaylı olarak bildiren *basit bir özelliği*gösterir. Derleyici, özelliğin değerini depolamak için otomatik olarak bir özel alan oluşturur.

İkinci sözdizimi örneği, hem `set` hem de `get` yöntemini açıkça bildiren bir *özellik bloğunu*gösterir.

Üçüncü sözdizimi örneği, müşteri tarafından tanımlanan bir *Dizin özelliğini*gösterir. Dizin özelliği, ayarlanacak veya alınacak değere ek olarak parametreleri alır. Özellik için bir ad belirtmeniz gerekir. Basit bir özelliğin aksine, bir dizin özelliğinin `set` ve/veya `get` yöntemleri açıkça tanımlanmalıdır ve özellik için bir ad belirtmeniz gerekir.

Dördüncü sözdizimi örneği, tür örneğine dizi benzeri erişim sağlayan *varsayılan* bir özelliği gösterir. **Varsayılan**anahtar sözcüğü, yalnızca varsayılan bir özellik belirtmek için hizmet verir. Varsayılan özelliğin adı, özelliğin tanımlandığı türün adıdır.

**Property** anahtar sözcüğü bir sınıf, arabirim veya değer türünde görünebilir. Bir özellik Get işlevine (salt okunurdur), set işlevine (salt yazılır) veya her ikisine (okuma-yazma) sahip olabilir.

Özellik adı, kendisini içeren yönetilen sınıfın adıyla eşleşemez. Alıcı işlevinin dönüş türü, karşılık gelen bir ayarlayıcı işlevinin son parametresinin türüyle aynı olmalıdır.

İstemci kodunda, bir özellik sıradan bir veri üyesinin görünümüne sahiptir ve veri üyesiyle aynı söz dizimini kullanarak üzerine yazılabilir veya buradan okunabilir.

Get ve set yöntemlerinin **sanal** değiştiricide kabul olmaması gerekir.

Get ve set yönteminin erişilebilirliği farklı olabilir.

Bir özellik yönteminin tanımı, sıradan bir yöntem gibi sınıf gövdesinin dışında yer alabilir.

Bir özelliğin get ve set yöntemi **statik** değiştiricide anlaşacaktır.

Get ve set yöntemleri aşağıdaki açıklamaya sığması halinde bir özellik skaler olur:

- Get yönteminin parametresi yok ve dönüş türü `T`.

- Set yöntemi `T`türünde bir parametreye sahiptir ve dönüş türü **void**.

Aynı tanımlayıcıya sahip bir kapsamda belirtilen yalnızca bir skaler özellik olacaktır. Skaler Özellikler aşırı yüklenemez.

Bir özellik veri üyesi bildirildiğinde, derleyici bir veri üyesini çıkartır (bazen "yedekleme deposu" olarak adlandırılır). Ancak, veri üyesinin adı, kaynak içindeki üyeye, kapsayan sınıfın gerçek bir veri üyesi gibi başvurulamıyor gibi bir form olur. Türü için meta verileri görüntülemek üzere ıldadsm. exe ' yi kullanın ve özelliğin yedekleme deposu için derleyicinin ürettiği adı görüntüleyin.

Özellik bloğundaki erişimci yöntemlerinde farklı erişilebilirliğe izin verilir.  Diğer bir deyişle, set yöntemi genel olabilir ve get yöntemi özel olabilir.  Ancak, bir erişimci yönteminin, özelliğin bildiriminde bulunandan daha az kısıtlayıcı bir erişilebilirliği olması hatadır.

**özellik** , bağlama duyarlı bir anahtar sözcüktür.  Daha fazla bilgi için bkz. [bağlama duyarlı anahtar sözcükler](context-sensitive-keywords-cpp-component-extensions.md).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki örnek, bir özellik veri üyesi ve bir özellik bloğunun bildirimini ve kullanımını gösterir.  Ayrıca, bir özellik erişimcisinin sınıf dışında tanımlanabilir olduğunu gösterir.

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
