---
title: Özellik ekleme
ms.date: 11/09/2018
f1_keywords:
- vc.codewiz.prop.overview
- vc.codewiz.prop.idlattributes
helpviewer_keywords:
- interfaces, adding properties
- properties [C++], adding to interfaces
- names, add property wizard
- IDL attributes, add property wizard
- stock properties, about stock properties
- stock properties
ms.assetid: 37bd4db7-efd3-4faa-87ad-64902ed16a36
ms.openlocfilehash: 79b05fde362a44453aac45aa8dc269c9689ea8fc
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751179"
---
# <a name="add-a-property"></a>Özellik ekleme

Projenizdeki arabirime yöntem eklemek için [özellik ekle sihirbazını](#names-add-property-wizard) kullanabilirsiniz.

**Nesnenize özellik eklemek için:**

1. [Sınıf](/visualstudio/ide/viewing-the-structure-of-code)Görünümü'nde, özelliği eklemek istediğiniz arabirimin adını sağ tıklatın.

   > [!NOTE]
   > Ayrıca, proje atfedilmedikçe kitaplık düğümü içinde iç içe olan dispinterfaces'e özellikler de ekleyebilirsiniz.

1. Kısayol menüsünden Ekle'yi ve ardından **Özellik Ekle'yi**seçin. **Add**

1. Özellik [ekle](#names-add-property-wizard)sihirbazında, özelliği oluşturmak için bilgileri sağlayın.

1. Sihirbazın [IDL öznitelikleri](#idl-attributes-add-property-wizard) sayfasında özellik için herhangi bir arabirim tanımı dili (IDL) ayarlarını belirtin.

1. Özelliği eklemek için **Bitiş'i** seçin.

`Get` Özelliğin `Put` ve yöntemleri, tanımlandığı arabirimin altında Sınıf Görünümü'nde iki simge olarak görüntülenir. .idl dosyasındaki özellik bildirimini görüntülemek için simgelerden birini çift tıklatabilirsiniz.

- ATL arabirimleri için `Get` `Put` .cpp dosyasına ve işlevler eklenir ve bu işlevlere yapılan başvurular .h dosyasına eklenir.

- MFC dispinterfaces için, uygulama türü olarak **Üye değişken** seçerseniz, bir yöntem ve bir değişken uygulayan sınıfa eklenir. Uygulama türü olarak **Getir/Ayarla yöntemlerini** seçerseniz, bunu uygulayan sınıfa iki yöntem eklenir.

## <a name="in-this-section"></a>Bu bölümde

- [Adlar, özellik sihirbazı ekle](#names-add-property-wizard)
- [IDL öznitelikleri, özellik sihirbazı ekleyin](#idl-attributes-add-property-wizard)
- [Stok özellikleri](#stock-properties)

## <a name="names-add-property-wizard"></a>Adlar, özellik sihirbazı ekle

Arabirime özellik eklemek için bu sihirbazı kullanın.

- **Özellik türü**

  Eklediğiniz özelliğin türünü ayarlar. MFC dispinterfaces için, kendi türünü sağlayın veya önceden tanımlanmış listeden seçin. Bir mülkün stok uygulamasını sağlarsanız, **Özellik türü** stok türüne ayarlanır ve değişiklik için kullanılamaz.

- **Özellik adı**

  Özelliğin adını ayarlar. ActiveX denetimleriyle ilişkili MFC dispinterfaces için, kendi adınızı verebilir veya önceden tanımlanmış listeden bir stok özelliği adı seçebilirsiniz. Kendi mülk adınızı sağlarsanız, **Stok** uygulama türü kullanılamaz. Listedeki özelliklerin açıklaması için [stok özelliklerine](#stock-properties) bakın.

  |Arayüz türü|Açıklama|
  |--------------------|-----------------|
  |ATL çift arabirim, özel arayüz ve yerel özel arayüz|Bir özellik adı sağlayın.|
  |MFC dispinterface, MFC ActiveX kontrol dispinterface|Bir mülk adı sağlayın veya listeden bir stok özelliği seçin. Listeden bir özellik seçerseniz, **Özellik türü** kutusunda uygun değer görüntülenir. **Uygulama türü**altında seçimbağlı olarak, bu türü değiştirebilirsiniz.|

- **Dönüş türü**

  Yalnızca ATL arabirimleri. Özellik için iade türünü ayarlar. Çift arabirimler `HRESULT` için, her zaman dönüş türüdür ve bu kutu kullanılamaz. Özel arabirimler için, listeden bir iade türü seçebilirsiniz. `HRESULT`hataları döndürmek için standart bir yol sağladığından, yine de önerilir.

- **Değişken adı**

  MFC yalnızca arabirimlerini salar. Yalnızca **Uygulama türü**altında **Üye değişkeni** belirtirseniz kullanılabilir. Özelliğin ilişkili olduğu üye değişkenin adını ayarlar. Varsayılan olarak, değişken adı `m_` *PropertyName*olarak ayarlanır. Bu adı edinebilirsiniz.

- **Bildirim işlevi**

  MFC yalnızca arabirimlerini salar. Yalnızca **Uygulama türü**altında **Üye değişkeni** belirtirseniz kullanılabilir. Özellik değişirse, bildirim işlevinin adını ayarlar. Varsayılan olarak, bildirim işlevinin adı `On` *PropertyName*`Changed`olarak ayarlanır. Bu adı edinebilirsiniz.

- **Get işlevi**

  MFC dispinterfaces için. Yalnızca **Uygulama türü**altında **Get/Set yöntemlerini** belirtirseniz kullanılabilir. Özelliği almak için işlevin adını ayarlar. Varsayılan olarak, `Get` işlevin adı `Get` *PropertyName*olarak ayarlanır. Bu adı edinebilirsiniz. Adı silerseniz, [GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported) işlevi arabirim gönderme haritasına eklenir. `Get` *PropertyName* işlevi özelliğin okunabilir olduğunu belirtir.

- **Fonksiyonu ayarlama**

  MFC yalnızca arabirimlerini salar. Yalnızca **Uygulama türü**altında **Get/Set yöntemlerini** belirtirseniz kullanılabilir. Özelliği ayarlamak için işlevin adını ayarlar. Varsayılan olarak, `Set` işlevin adı `Set` *PropertyName*olarak ayarlanır. Bu adı edinebilirsiniz. Adı silerseniz, [SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported) işlevi arabirim gönderme haritasına eklenir. `Set` *PropertyName* işlevi, özelliğin yazılabilir olduğunu belirtir.

- **Uygulama türü**

  MFC yalnızca arabirimlerini salar. Eklediğiniz özelliğin nasıl uygulanacağını belirtir.

  |Uygulama türü|Açıklama|
  |-------------------------|-----------------|
  |**Stok**|**Özellik adına**seçilen özellik için stok uygulamasını belirtir. Varsayılan. Daha fazla bilgi için [stok özelliklerine](#stock-properties)bakın.<br /><br /> **Stok**belirtirseniz, daha sonra **Özellik türü,** **Parametre türü**ve **Parametre adı** soluk.|
  |**Üye değişkeni**|Özellik bir üye değişken olarak eklenir belirtir. Üye değişkenler olarak özel özellikler veya çoğu stok özelliği ekleyebilirsiniz. **Üye değişkenini** `Caption`, , `hWnd`ve `Text` özellikleri için belirtemezsiniz.<br /><br /> **Değişken adı** ve **Bildirim işlevi**altında varsayılan adlar sağlar. Bu adı edinebilirsiniz.|
  |**Alma/Ayarlama yöntemleri**|Özellik, varsayılan olarak PropertyName `Get`ve `Set` *PropertyName* işlevleri olarak eklenir belirtir. *PropertyName* Bu adlar **Get işlevi** ve Set **işlevi**altında görünür.<br /><br /> Al işlevi için bir değer geçen varsayılan **Özellik türünü**değiştirebilirsiniz. Parametreleri `Get` ve `Set` işlevleri belirtebilirsiniz.|

- **Get işlevi**

  ATL arabirimleri için. Özelliği okunabilir olarak ayarlar; diğer bir şekilde, `Get` bu özelliği nesneden alma yöntemini oluşturur. **Get**, **Put**veya her ikisini seçin.

- **Put fonksiyonu**

  Yalnızca ATL arabirimleri. Özelliği yazılabilir ayarlar; diğer bir şekilde, `Put` nesnenin bu özelliğini ayarlama veya "koyma" yöntemini oluşturur. **Get**, **Put**veya her ikisini seçin. Bu seçeneği seçerseniz, yöntemi uygulamanın iki yolunu seçebilirsiniz:

  |Seçenek|Açıklama|
  |------------|-----------------|
  |**Propput**|[PropPut](../windows/propput.md) işlevi nesnenin bir kopyasını döndürür. Bu, özelliği yazılabilir hale getirmenin varsayılan ve en yaygın yoludur.|
  |**Propputref**|[PropPutRef](../windows/propputref.md) işlevi, nesnenin kopyasını döndürmek yerine nesneye bir başvuru döndürür. Büyük structs veya diziler gibi, başbaşlatma yükü olabilir nesneler için bu seçeneği kullanmayı düşünün.|

- **Parametre öznitelikleri**

  Yalnızca ATL arabirimleri. **Parametre adı ile** belirtilen parametrenin `in`, her `out`ikisi veya hiçbiri olup olmadığını ayarlar.

  |Seçenek|Açıklama|
  |------------|-----------------|
  |`in`|Parametrenin arama yordamından çağrılan yordama geçirildiğini gösterir.|
  |`out`|İşaretçi parametresinin çağrılan yordamdan çağrı prosedürüne (sunucudan istemciye) döndürüldünü gösterir.|

- **Parametre türü**

  Parametrenin veri türünü ayarlar. Listeden türü seçin.

- **Parametre adı**

  Özellik parametreleri varsa, özellik için eklediğiniz bir parametrenin adını ayarlar. **Ekle'yi**seçtikten sonra parametre adı **Parametre listesinde**görünür.

- **Parametre listesi**

  Özelliğe eklenecek özniteliklerlistesini görüntüler. Listedeki her öğe parametre adı, parametre türü ve özniteliklerden oluşur. Listeyi güncelleştirmek için **Ekle** ve **Kaldır'ı** kullanın.

- **Ekle**

  **Parametre adına** belirttiğiniz parametreyi ve **Parametre türünü** **Parametre listesine**ekler. Listeye parametre eklemek için **Ekle'yi** seçin.

- **Kaldır**

  **Parametre listesinde**seçtiğiniz parametreyi kaldırır.

- **Varsayılan özellik**

  Yalnızca MFC dispinterface. Bu özelliği arabirim için varsayılan olarak ayarlar. Bir arabirimin yalnızca bir varsayılan özelliği olabilir; varsayılan özelliği belirttikten sonra, arabirime eklediğiniz diğer özellikler için bu kutu kullanılamaz.

## <a name="idl-attributes-add-property-wizard"></a>IDL öznitelikleri, özellik sihirbazı ekleyin

Özellik için herhangi bir arabirim tanımı dili (IDL) ayarlarını belirtmek için Özellik Ekle Sihirbazı'nın bu sayfasını kullanın.

- `id`

  Özelliği tanımlayan sayısal kimliği ayarlar. Bu seçenek, özel arabirimlerin özellikleri için kullanılamaz. *MIDL Referans'taki* [id'ye](/windows/win32/Midl/id) bakın.

- `helpcontext`

  Kullanıcının Yardım dosyasında bu özellik hakkındaki bilgileri görüntülemesini sağlayan bir bağlam kimliği belirtir. *MIDL Başvurusu'ndaki* [yardım bağlamına](/windows/win32/Midl/helpcontext) bakın.

- `helpstring`

  Uygulandığı öğeyi açıklamak için kullanılan bir karakter dizesini belirtir. Varsayılan olarak, `property` &nbsp; *Özellik&nbsp;adına*ayarlanır. *MIDL Başvurusu'ndaki* [helpstring'e](/windows/win32/Midl/helpstring) bakın.

### <a name="other-options"></a>Diğer seçenekler

Tüm seçenekler tüm özellik türleri için kullanılamaz.

|Seçenek|Açıklama|
|------------|-----------------|
|`bindable`|Özelliğin veri bağlamayı desteklediğini gösterir. *MIDL Başvurusu'nda* [bağlanabilir](/windows/win32/Midl/bindable) bkz. Özelliğin hisse senedi uygulaması için bu seçenek varsayılan olarak ayarlanır ve değiştirilemez.|
|`defaultbind`|Bu tek, bağlanabilir özelliğin nesneyi en iyi temsil ettiğini gösterir. *MIDL Başvurusu'nda* [varsayılan binme'ye](/windows/win32/Midl/defaultbind) bakın.|
|`displaybind`|Bu özelliğin kullanıcıya bağlanabilir olarak gösterilmesi gerektiğini gösterir. *MIDL Başvurusu'nda* [displaybind'e](/windows/win32/Midl/displaybind) bakın.|
|`immediatebind`|Veriye bağlı bir nesnenin bu özelliğindeki tüm değişiklikler veritabanına hemen bildirilir. *MIDL Başvurusu'nda* [hemen bind](/windows/win32/Midl/immediatebind) bakın.|
|`defaultcollelem`|Özelliğin varsayılan koleksiyonun bir öğesi için bir erişimci işlev olduğunu gösterir. *MIDL Başvurusu'nda* [defaultcollelem'e](/windows/win32/Midl/defaultcollelem) bakın.|
|`nonbrowsable`|Özellikler tarayıcısında görüntülenmemesi gereken bir arabirim veya dispinterface üyesini etiketler. *MIDL Başvurusu'nda* [kaşsız](/windows/win32/Midl/nonbrowsable) görün.|
|`requestedit`|Özelliğin `OnRequestEdit` bildirimi desteklediğini gösterir. *MIDL Başvurusu'nda* [istenene](/windows/win32/Midl/requestedit) bakın. Özelliğin hisse senedi uygulaması için bu seçenek varsayılan olarak ayarlanır ve değiştirilemez.|
|`source`|Özelliğin bir üyesinin olayların kaynağı olduğunu gösterir. *MIDL Başvurusu'ndaki* [kaynağa](/windows/win32/Midl/source) bakın.|
|`hidden`|Özelliğin var olduğunu, ancak kullanıcı yönelimli bir tarayıcıda görüntülenmemesi gerektiğini gösterir. *MIDL Başvurusu'nda* [gizli](/windows/win32/Midl/hidden) bkz.|
|`restricted`|Özelliğin rasgele çağrılamayacağı belirtilir. *MIDL Başvurusu'nda* [sınırlı](/windows/win32/Midl/restricted) bkz.|
|`local`|MIDL derleyicisine özelliğin uzak olmadığını belirtir. *MIDL Başvurusu'nda* [yerel](/windows/win32/Midl/local) bkz.|

## <a name="stock-properties"></a>Stok özellikleri

[Özellik ekle sihirbazını](#idl-attributes-add-property-wizard)kullanarak Bir MFC dispinterface'e bir özellik ekliyorsanız, sihirbazın [Adlar](../ide/names-add-property-wizard.md) sayfasında **Kisa ad** listesinden bir stok özelliği seçebilirsiniz. Bu özellikler aşağıdaki gibidir:

|Özellik adı|Açıklama|
|-------------------|-----------------|
|`Appearance`|Denetimin görünümünü belirleyen bir değer verir veya ayarlar. Denetimin `Appearance` özelliği üç boyutlu ekran efektleri içerebilir veya atlayabilir. Bu özellik ortam okuma/yazma özelliğidir.|
|`BackColor`|Denetimin ortam `BackColor` özelliğini palet (RGB) rengine veya önceden tanımlanmış bir sistem rengine döndürür veya ayarlar. Varsayılan olarak, değeri denetim kapsayıcısının ön plan rengine karşılık gelir. Bu özellik ortam okuma/yazma özelliğidir.|
|`BorderStyle`|Denetim için kenarlık stilini döndürür veya ayarlar. Bu özellik bir okuma/yazma özelliğidir.|
|`Caption`|Denetimin `Caption` özelliğini döndürür veya ayarlar. Başlık pencerenin başlığıdır. `Caption`Üye **değişken** uygulama türü yoktur.|
|`Enabled`|Denetimin `Enabled` özelliğini döndürür veya ayarlar. Etkin leştirilmiş bir denetim, kullanıcı tarafından oluşturulan olaylara yanıt verebilir.|
|`Font`|Denetimin ortam yazı tipini döndürür veya ayarlar. Denetimin yazı tipi yoksa null.|
|`ForeColor`|Denetimin ortam `ForeColor` özelliğini döndürür veya ayarlar.|
|`hWnd`|Denetimin `hWnd` özelliğini döndürür veya ayarlar. `hWnd`Üye **değişken** uygulama türü yoktur.|
|`ReadyState`|Denetimin `ReadyState` özelliğini döndürür veya ayarlar. Denetim başharfe indirilmemiş, başharflere getirilmemiş, yüklenebilir, etkileşimli veya tamamlanabilir. Daha fazla bilgi için *Internet SDK'daki* [READYSTATE'e](/previous-versions/aa768362\(v=vs.85\)) bakın.|
|`Text`|Denetimde bulunan metni döndürür veya ayarlar. `Text`Üye **değişken** uygulama türü yoktur.|
