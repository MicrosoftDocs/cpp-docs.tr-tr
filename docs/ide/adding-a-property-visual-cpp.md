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
ms.openlocfilehash: 5c472b74fee690c0cf33f78eca9e2e8462930eb8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509522"
---
# <a name="add-a-property"></a>Özellik ekleme

Projenizdeki bir arabirime bir yöntem eklemek için [Özellik Ekleme Sihirbazı](#names-add-property-wizard) ' nı kullanabilirsiniz.

**Nesneniz için bir özellik eklemek için:**

1. [Sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code), özelliği eklemek istediğiniz arabirimin adına sağ tıklayın.

   > [!NOTE]
   > Ayrıca, proje ilişkilendirilemediği takdirde, kitaplık düğümü içinde iç içe yerleştirilmiş olan görüntüleme arabirimlerine özellikler ekleyebilirsiniz.

1. Kısayol menüsünde **Ekle**' yi ve ardından **Özellik Ekle**' yi seçin.

1. [Özellik Ekleme sihirbazında](#names-add-property-wizard), özelliği oluşturmak için bilgileri sağlayın.

1. Sihirbazın [IDL öznitelikleri](#idl-attributes-add-property-wizard) sayfasında özellik için herhangi bir arabirim tanım DILI (IDL) ayarı belirtin.

1. Özelliği eklemek için **son** ' u seçin.

Özelliğinin `Get` ve`Put` yöntemleri, sınıf görünümü tanımlandığı arabirim altında iki simge olarak görüntülenir. . IDL dosyasında özellik bildirimini görüntülemek için her iki simgeye de çift tıklayabilirsiniz.

- ATL arabirimleri `Get` için, ve `Put` işlevleri. cpp dosyasına eklenir ve bu işlevlere yapılan başvurular. h dosyasına eklenir.

- MFC dispınterfaces için, uygulama türü olarak **üye değişkeni** ' ni seçerseniz, bir yöntem ve bir değişken onu uygulayan sınıfa eklenir. Uygulama türü olarak **Get/Set yöntemlerini** seçerseniz, uygulayan sınıfa iki yöntem eklenir.

## <a name="in-this-section"></a>Bu bölümde

- [Adlar, Özellik Ekleme Sihirbazı](#names-add-property-wizard)
- [IDL öznitelikleri, Özellik Ekleme Sihirbazı](#idl-attributes-add-property-wizard)
- [Hisse senedi özellikleri](#stock-properties)

## <a name="names-add-property-wizard"></a>Adlar, Özellik Ekleme Sihirbazı

Bir arabirime özellik eklemek için bu sihirbazı kullanın.

- **Özellik türü**

  Eklemekte olduğunuz özelliğin türünü ayarlar. MFC dispınterfaces için kendi türünü sağlayın veya önceden tanımlanmış listeden seçin. Bir özelliğin hisse senedi uygulamasını sağlarsanız, **özellik türü** stok türüne ayarlanır ve değişiklik için kullanılamaz.

- **Özellik adı**

  Özelliğin adını ayarlar. ActiveX denetimleriyle ilişkili MFC dispınterfaces için kendi adınızı sağlayabilir veya önceden tanımlanmış listeden bir stok özelliği adı seçebilirsiniz. Kendi özellik adınızı sağlarsanız, **hisse senedi** uygulama türü kullanılamaz. Listedeki özelliklerin açıklaması için [hisse senedi özelliklerine](#stock-properties) bakın.

  |Arabirim türü|Açıklama|
  |--------------------|-----------------|
  |ATL Dual Interface, özel arabirim ve yerel özel arabirim|Bir özellik adı belirtin.|
  |MFC dispınterface, MFC ActiveX denetimi dispınterface|Bir özellik adı girin veya listeden bir stok özelliği seçin. Listeden bir özellik seçerseniz, **özellik türü** kutusunda uygun değer görüntülenir. Bu türü, **uygulama türü**altında seçiminize bağlı olarak değiştirebilirsiniz.|

- **Dönüş türü**

  Yalnızca ATL arabirimleri. Özellik için dönüş türünü ayarlar. Çift arabirimler `HRESULT` için her zaman dönüş türüdür ve bu kutu kullanılamaz. Özel arabirimler için listeden bir dönüş türü seçebilirsiniz. `HRESULT`Hala önerilir, çünkü hataları döndürmek için standart bir yol sağlar.

- **Değişken adı**

  Yalnızca MFC görüntüleme arabirimleri. Yalnızca **uygulama türü**altında **üye değişkeni** belirtirseniz kullanılabilir. Özelliğin ilişkilendirildiği üye değişkeninin adını ayarlar. Varsayılan olarak, değişken adı `m_` *PropertyName*olarak ayarlanır. Bu adı düzenleyebilirsiniz.

- **Notification işlevi**

  Yalnızca MFC görüntüleme arabirimleri. Yalnızca **uygulama türü**altında **üye değişkeni** belirtirseniz kullanılabilir. Özellik değişirse çağrılan bildirim işlevinin adını ayarlar. Varsayılan olarak, bildirim işlevinin adı `On` *PropertyName*`Changed`olarak ayarlanır. Bu adı düzenleyebilirsiniz.

- **Get işlevi**

  MFC görüntüleme arabirimleri için. Yalnızca **uygulama türü**altında **Get/Set yöntemlerini** belirtirseniz kullanılabilir. Özelliği almak için işlevin adını ayarlar. Varsayılan olarak, `Get` işlevin adı *PropertyName*olarak `Get`ayarlanır. Bu adı düzenleyebilirsiniz. Adı silerseniz, [GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported) işlevi arabirim gönderme eşlemesine eklenir. PropertyName işlevi, özelliğin okunabilir olduğunu belirtir. `Get`

- **Set işlevi**

  Yalnızca MFC görüntüleme arabirimleri. Yalnızca **uygulama türü**altında **Get/Set yöntemlerini** belirtirseniz kullanılabilir. Özelliği ayarlamak için işlevin adını ayarlar. Varsayılan olarak, `Set` işlevin adı *PropertyName*olarak `Set`ayarlanır. Bu adı düzenleyebilirsiniz. Adı silerseniz, [SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported) işlevi arabirim gönderme eşlemesine eklenir. PropertyName işlevi, özelliğin yazılabilir olduğunu belirtir. `Set`

- **Uygulama türü**

  Yalnızca MFC görüntüleme arabirimleri. Eklemekte olduğunuz özelliğin nasıl uygulanacağını belirtir.

  |Uygulama türü|Açıklama|
  |-------------------------|-----------------|
  |**Stok**|**Özellik adı**'nda seçilen özellik için bir stok uygulamasını belirtir. Varsayılan. Daha fazla bilgi için bkz. [Stok özellikleri](#stock-properties).<br /><br /> **Stok**belirtirseniz, **özellik türü**, **parametre türü**ve **parametre adı** soluk kalır.|
  |**Üye değişkeni**|Özelliğin üye değişkeni olarak eklendiğini belirtir. Üye değişkenleri olarak özel özellikler veya çoğu hisse senedi özelliği ekleyebilirsiniz. `Caption`, ,Ve`Text` özellikleri için **üye değişkeni** belirtemezsiniz. `hWnd`<br /><br /> **Değişken adı** ve **bildirim işlevi**altında varsayılan adlar sağlar. Bu adı düzenleyebilirsiniz.|
  |**Get/set yöntemleri**|Özelliğin `Get` *PropertyName* ve`Set` *PropertyName* işlevleri olarak eklendiğini varsayılan olarak belirtir. Bu adlar, **get işlevi** ve **set işlevi**altında görünür.<br /><br /> GET işlevi için bir değer geçiren varsayılan **özellik türünü**değiştirebilirsiniz. `Get` Ve`Set` işlevleri için parametreler belirtebilirsiniz.|

- **Get işlevi**

  ATL arabirimleri için. Özelliği okunabilir olarak ayarlar; diğer bir deyişle, nesnesinden bu `Get` özelliği almak için yöntemini oluşturur. **Al**, **koy**veya her ikisini de seçin.

- **Put işlevi**

  Yalnızca ATL arabirimleri. Yazılabilir özelliği ayarlar; diğer bir deyişle, nesnesinin bu `Put` özelliğini ayarlama veya "yerleştirme" yöntemini oluşturur. **Al**, **koy**veya her ikisini de seçin. Bu seçeneği belirlerseniz, yöntemi uygulamak için aşağıdaki iki yöntemden birini kullanabilirsiniz:

  |Seçenek|Açıklama|
  |------------|-----------------|
  |**PropPut**|[Propput](../windows/propput.md) işlevi nesnenin bir kopyasını döndürür. Bu, özelliği yazılabilir yapmanın varsayılan ve en yaygın yoludur.|
  |**PropPutRef**|[Propputref](../windows/propputref.md) işlevi nesnenin kopyasını döndürmek yerine nesnesine bir başvuru döndürür. Başlatma ek yüküne sahip olabilecek büyük yapılar veya diziler gibi nesneler için bu seçeneği kullanmayı düşünün.|

- **Parametre öznitelikleri**

  Yalnızca ATL arabirimleri. **Parametre adı** tarafından belirtilen parametrenin,, her ikisinin `in`de `out`veya None olduğunu ayarlar.

  |Seçenek|Açıklama|
  |------------|-----------------|
  |`in`|Parametrenin çağıran yordamdan çağrılan yordama geçtiğini gösterir.|
  |`out`|İşaretçi parametresinin çağrılan yordamdan çağıran yordama (sunucudan istemciye) döndürüldüğünü gösterir.|

- **Parametre türü**

  Parametrenin veri türünü ayarlar. Listeden türü seçin.

- **Parametre adı**

  Özelliğin parametreleri varsa, özelliği için eklemekte olduğunuz parametrenin adını ayarlar. **Ekle**' yi seçtiğinizde parametre adı **parametre listesinde**görünür.

- **Parametre listesi**

  Özelliğe eklenecek özniteliklerin listesini görüntüler. Listedeki her öğe parametre adı, parametre türü ve özniteliklerden oluşur. Listeyi güncelleştirmek için **Ekle** ve **Kaldır** ' i kullanın.

- **Add**

  Parametre **adı** ve parametre **türü** ' nde belirttiğiniz parametreyi **parametre listesine**ekler. Listeye bir parametre eklemek için **Ekle** ' yi seçin.

- **Kaldır**

  **Parametre listesinde**seçtiğiniz parametreyi kaldırır.

- **Varsayılan özellik**

  Yalnızca MFC görüntüleme arabirimi. Bu özelliği arabirim için varsayılan değer olarak ayarlar. Bir arabirim yalnızca bir varsayılan özelliğe sahip olabilir; Varsayılan özelliği belirttiğinizde, arabirime eklediğiniz diğer özellikler için bu kutu kullanılamaz.

## <a name="idl-attributes-add-property-wizard"></a>IDL öznitelikleri, Özellik Ekleme Sihirbazı

Özellik için herhangi bir arabirim tanım dili (IDL) ayarı belirtmek üzere Özellik Ekleme Sihirbazı ' nın bu sayfasını kullanın.

- `id`

  Özelliği tanımlayan sayısal KIMLIĞI ayarlar. Bu seçenek özel arabirimlerin özellikleri için kullanılamaz. *MIDL başvurusunda* [kimliği](/windows/win32/Midl/id) görüntüleyin.

- `helpcontext`

  Kullanıcının Yardım dosyasında bu özellik hakkında bilgi görüntülemesine imkan tanıyan bir bağlam KIMLIĞI belirtir. *MIDL başvurusunda* [HelpContext](/windows/win32/Midl/helpcontext) bölümüne bakın.

- `helpstring`

  Uygulandığı öğeyi anlatmak için kullanılan bir karakter dizesini belirtir. Varsayılan olarak, `property`&nbsp;*özellikadı&nbsp;* olarak ayarlanır. *MIDL başvurusunda* [HelpString](/windows/win32/Midl/helpstring) ' i inceleyin.

### <a name="other-options"></a>Diğer seçenekler

Tüm seçenekler tüm özellik türleri için kullanılamaz.

|Seçenek|Açıklama|
|------------|-----------------|
|`bindable`|Özelliğin veri bağlamayı desteklediğini belirtir. Bkz. *MIDL başvurusunda* [bağlanabilir](/windows/win32/Midl/bindable) . Özelliğin hisse senedi uygulamasında bu seçenek varsayılan olarak ayarlanır ve değiştirilemez.|
|`defaultbind`|Bu tek, bağlanabilir özelliğin nesneyi en iyi temsil ettiğini belirtir. *MIDL başvurusunda* [defaultbind](/windows/win32/Midl/defaultbind) bölümüne bakın.|
|`displaybind`|Bu özelliğin kullanıcıya bağlanabilir olarak görüntülenmesi gerektiğini gösterir. *MIDL başvurusunda* [displaybind](/windows/win32/Midl/displaybind) bölümüne bakın.|
|`immediatebind`|Veritabanına, veri bağlantılı nesnenin bu özelliğindeki tüm değişikliklerin hemen bildirileceğini belirtir. *MIDL başvurusunda* [immediatebind](/windows/win32/Midl/immediatebind) bakın.|
|`defaultcollelem`|Özelliğin varsayılan koleksiyonun bir öğesi için bir erişimci işlevi olduğunu gösterir. *MIDL başvurusunda* [defaultcollelem](/windows/win32/Midl/defaultcollelem) öğesine bakın.|
|`nonbrowsable`|Bir özellikler tarayıcısında görüntülenmemelidir bir arabirim veya dispınterface üyesini Etiketler. Bkz. *MIDL başvurusunda* [gözatılabilir](/windows/win32/Midl/nonbrowsable) .|
|`requestedit`|Özelliğin `OnRequestEdit` bildirimi desteklediğini gösterir. *MIDL başvurusunda*bkz. [requestedıt](/windows/win32/Midl/requestedit) . Özelliğin hisse senedi uygulamasında bu seçenek varsayılan olarak ayarlanır ve değiştirilemez.|
|`source`|Özelliğin bir üyesinin bir olay kaynağı olduğunu gösterir. *MIDL başvurusundaki* [kaynağı](/windows/win32/Midl/source) görüntüleyin.|
|`hidden`|Özelliğin var olduğunu ancak kullanıcıya dayalı bir tarayıcıda gösterilmemesi gerektiğini gösterir. Bkz. *MIDL başvurusunda* [gizli](/windows/win32/Midl/hidden) .|
|`restricted`|Özelliğin rastgele olarak çağrılamayacağını belirtir. Bkz. *MIDL başvurusunda* [Kısıtlanmış](/windows/win32/Midl/restricted) .|
|`local`|MıDL derleyicisine, özelliğin uzak olmadığını belirtir. *MIDL başvurusunda* [Yerel](/windows/win32/Midl/local) bölümüne bakın.|

## <a name="stock-properties"></a>Hisse senedi özellikleri

[Özellik Ekleme Sihirbazı](#idl-attributes-add-property-wizard)'Nı kullanarak mfc görüntüleme arabirimine bir özellik ekliyorsanız, sihirbazın [adlar](../ide/names-add-property-wizard.md) sayfasındaki **özellik adı** listesinden bir stok özelliği seçebilirsiniz. Bu özellikler aşağıdaki gibidir:

|Özellik adı|Açıklama|
|-------------------|-----------------|
|`Appearance`|Denetimin görünüşünü belirleyen bir değer döndürür veya ayarlar. Denetimin `Appearance` özelliği üç boyutlu görüntüleme efektlerini içerebilir veya atlayabilir. Bu özellik bir çevresel okuma/yazma özelliğidir.|
|`BackColor`|Denetimin çevresel `BackColor` özelliğini bir palet (RGB) rengine veya önceden tanımlanmış bir sistem rengine döndürür ya da ayarlar. Varsayılan olarak, değeri denetimin kapsayıcısının ön plan rengine karşılık gelir. Bu özellik bir çevresel okuma/yazma özelliğidir.|
|`BorderStyle`|Bir denetimin kenarlık stilini döndürür veya ayarlar. Bu özellik bir okuma/yazma özelliğidir.|
|`Caption`|Denetimin `Caption` özelliğini döndürür veya ayarlar. Başlık pencerenin başlığı olur. `Caption`**üye değişkeni** uygulama türü yok.|
|`Enabled`|Denetimin `Enabled` özelliğini döndürür veya ayarlar. Etkin bir denetim, Kullanıcı tarafından oluşturulan olaylara yanıt verebilir.|
|`Font`|Denetimin çevresel yazı tipini döndürür veya ayarlar. Denetimin yazı tipi yoksa null.|
|`ForeColor`|Denetimin çevresel `ForeColor` özelliğini döndürür veya ayarlar.|
|`hWnd`|Denetimin `hWnd` özelliğini döndürür veya ayarlar. `hWnd`**üye değişkeni** uygulama türü yok.|
|`ReadyState`|Denetimin `ReadyState` özelliğini döndürür veya ayarlar. Bir Denetim başlatılmamış, başlatılmış, yüklenmeye, etkileşimli veya tamamlanmış olabilir. Daha fazla bilgi için *Internet SDK 'Sında* [ReadyState](/previous-versions//aa768362\(v=vs.85\)) bölümüne bakın.|
|`Text`|Denetimde bulunan metni döndürür veya ayarlar. `Text`**üye değişkeni** uygulama türü yok.|
