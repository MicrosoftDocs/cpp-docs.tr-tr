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
ms.openlocfilehash: 06940bb72f9113e0a8148e15418504b35fc95099
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62226274"
---
# <a name="add-a-property"></a>Özellik ekleme

Kullanabileceğiniz [Özellik Ekleme Sihirbazı](#names-add-property-wizard) projenize bir arabirimde bir yöntemi eklemek için.

**Nesneniz için bir özellik eklemek için:**

1. İçinde [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code), özellik eklemek istediğiniz arabirimin adını sağ tıklayın.

   > [!NOTE]
   > Ayrıca, proje öznitelikli sürece, kitaplık düğümünün içinde iç içe geçmiş görüntüleme özellikleri ekleyebilirsiniz.

1. Kısayol menüsünden **Ekle**ve ardından **Özellik Ekle**.

1. İçinde [Özellik Ekleme Sihirbazı](#names-add-property-wizard), özellik oluşturmak için bilgileri sağlayın.

1. Bir özellik için arabirim tanımlama dili (IDL) ayarlarını belirtin [IDL öznitelikleri](#idl-attributes-add-property-wizard) Sihirbazı sayfası.

1. Seçin **son** özelliği eklemek için.

`Get` Ve `Put` özelliğinin yöntemlerini, Sınıf Görünümü'nde iki simgeyi altında tanımlanmış olduğu yerlerde arabirimi olarak görüntülenir. Özellik bildiriminde .idl dosyasında görüntülemek için her iki simgesini çift tıklayabilirsiniz.

- ATL arabirimleri için `Get` ve `Put` işlevleri .cpp dosyasına eklenir ve bu işlevlere yönelik başvurulara .h dosyasına eklenir.

- MFC görüntüleme seçerseniz için **üye değişkeni** uygulama türü bir yöntem ve bir değişken, kendisini uygulayan sınıfa eklenir. Seçerseniz **Get/Set yöntemleri** uygulama türü iki yöntem bunu uygulayan bir sınıfa eklenir.

## <a name="in-this-section"></a>Bu bölümde

- [Adlar, Özellik Ekleme Sihirbazı](#names-add-property-wizard)
- [IDL öznitelikleri, Özellik Ekleme Sihirbazı](#idl-attributes-add-property-wizard)
- [Stok özellikleri](#stock-properties)

## <a name="names-add-property-wizard"></a>Adlar, Özellik Ekleme Sihirbazı

Bir özellik için bir arabirim eklemek için bu sihirbazı kullanın.

- **Özellik türü**

  Ekliyorsunuz özelliğin türünü ayarlar. MFC görüntüleme, kendi türü sağlayın veya önceden tanımlanmış bir listeden seçin. Bir özellik, bir stok uygulamasına sağlarsanız **özellik türü** stok türüne ayarlanır ve değişiklik için kullanılamıyor.

- **Özellik adı**

  Özelliğin adını ayarlar. MFC ActiveX denetimleri ile ilişkili görüntü arabirimlerinde, kendi adınızı sağlayabilir veya stok özellik adı önceden tanımlanmış bir listeden seçebilirsiniz. Kendi özellik adı sağlarsanız **hisse senedi** uygulama türü kullanılamaz. Bkz: [stok özellikleri](#stock-properties) listesinde özellikleri açıklaması.

  |Arabirim türü|Açıklama|
  |--------------------|-----------------|
  |ATL çift arabirim, özel arabirim ve yerel özel arabirimi|Bir özellik adı belirtin.|
  |MFC dispinterface, MFC ActiveX denetimi dispinterface|Bir özellik adı belirtin veya listeden bir stok özellik seçin. Listeden bir özellik seçerseniz, uygun değere görünür **özellik türü** kutusu. Bu türü altında yaptığınız seçime bağlı olarak değiştirebileceğiniz **uygulama türü**.|

- **Dönüş türü**

  ATL yalnızca arabirimleri. Özelliğinin dönüş türünü ayarlar. Çift arabirimler için `HRESULT` her zaman dönüş türü ve bu kutusu kullanılamaz. Özel arabirimler için listeden bir dönüş türü seçebilirsiniz. `HRESULT` hatalarını döndürmek için standart bir yolu sağladığından yine de önerilir.

- **Değişken adı**

  Yalnızca MFC görüntüleme. Yalnızca belirlediğinizde kullanılabilir **üye değişkeni** altında **uygulama türü**. Özelliği ilişkili olduğu üye değişkeninin adını ayarlar. Varsayılan olarak, değişken adı kümesine `m_` *PropertyName*. Bu ad düzenleyebilirsiniz.

- **Bildirim işlevi**

  Yalnızca MFC görüntüleme. Yalnızca belirlediğinizde kullanılabilir **üye değişkeni** altında **uygulama türü**. Özellik değişiklikleri bildirim işlevi çağrılan if adını ayarlar. Varsayılan olarak, bildirim işlevin adını ayarlamak `On` *PropertyName*`Changed`. Bu ad düzenleyebilirsiniz.

- **Get işlevi**

  MFC görüntüleme için. Yalnızca belirlediğinizde kullanılabilir **Get/Set yöntemleri** altında **uygulama türü**. Özellik get yapılmaya işlevin adını ayarlar. Varsayılan olarak, adını `Get` işlevi ayarlandığında `Get` *PropertyName*. Bu ad düzenleyebilirsiniz. İşlev adı silerseniz [GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported) arabirimi gönderme eşlemesine eklenir. `Get` *PropertyName* işlevi belirtir özelliği olarak okunabilir.

- **Set işlevi**

  Yalnızca MFC görüntüleme. Yalnızca belirlediğinizde kullanılabilir **Get/Set yöntemleri** altında **uygulama türü**. Özellik ayarlamak için işlevin adını ayarlar. Varsayılan olarak, adını `Set` işlevi ayarlandığında `Set` *PropertyName*. Bu ad düzenleyebilirsiniz. İşlev adı silerseniz [SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported) arabirimi gönderme eşlemesine eklenir. `Set` *PropertyName* işlevi özelliği yazılabilir olduğunu belirtir.

- **Uygulama türü**

  Yalnızca MFC görüntüleme. Nasıl uygulanacağını ekliyorsunuz özelliği belirtir.

  |Uygulama türü|Açıklama|
  |-------------------------|-----------------|
  |**Hisse senedi**|Seçili özellik için bir stok uygulama belirtir **özellik adı**. Varsayılan. Daha fazla bilgi için [stok özellikleri](#stock-properties).<br /><br /> Belirtirseniz **hisse senedi**, ardından **özellik türü**, **parametre türü**, ve **parametre adı** soluklaştırılır.|
  |**Üye değişkeni**|Özellik olarak bir üye değişkeni eklenir belirtir. Özel özellikler veya stok özelliklerinin çoğu üye değişkenleri ekleyebilirsiniz. Belirtemezsiniz **üye değişkeni** için `Caption`, `hWnd`, ve `Text` özellikleri.<br /><br /> Varsayılan adlarla sağlar **değişken adı** ve **bildirim işlevini**. Bu ad düzenleyebilirsiniz.|
  |**Get/Set yöntemleri**|Özellik olarak eklenir belirtir `Get` *PropertyName* ve `Set` *PropertyName* varsayılan işlevler. Bu adları altında görünür **alma işlevi** ve **Set işlevi**.<br /><br /> Varsayılan olarak değiştirebilirsiniz **özellik türü**, Get işlevi için bir değer geçirir. Parametreler için belirtebileceğiniz `Get` ve `Set` işlevleri.|

- **Get işlevi**

  ATL arabirimleri. Özelliği, okunamaz olarak ayarlar; diğer bir deyişle, oluşturduğu `Get` nesneden bu özelliği almak için yöntemi. Seçin **alma**, **Put**, veya her ikisini de.

- **Put işlevi**

  ATL yalnızca arabirimleri. Özelliği yazılabilir ayarlar; diğer bir deyişle, oluşturduğu `Put` ayarlanması veya "ekledikçe," nesnesinin bu özelliği için yöntemi. Seçin **alma**, **Put**, veya her ikisini de. Bu seçeneği belirlerseniz yöntemi uygulamak için aşağıdaki iki yoldan seçebilirsiniz:

  |Seçenek|Açıklama|
  |------------|-----------------|
  |**PropPut**|[PropPut](../windows/propput.md) işlev nesnesinin bir kopyasını döndürür. Varsayılan ve özellik yazılabilir yapmak için en yaygın yolu budur.|
  |**PropPutRef**|[PropPutRef](../windows/propputref.md) işlev nesnesinin kopyasını döndüren yerine nesneye bir başvuru döndürür. Büyük yapılar veya başlatma yükü olabilecek diziler gibi nesneler için bu seçeneği kullanmayı düşünün.|

- **Parametre öznitelikleri**

  ATL yalnızca arabirimleri. Parametresi tarafından belirtilen ayarlar **parametre adı** olduğu `in`, `out`, her ikisi de veya yok.

  |Seçenek|Açıklama|
  |------------|-----------------|
  |`in`|Parametrenin çağıran yordamdan çağrılan yordama geçirildiğini gösterir.|
  |`out`|İşaretçi parametresi çağrılan yordamdan çağıran yordama (sunucudan istemciye) döndürülür gösterir.|

- **Parametre türü**

  Parametrenin veri türünü ayarlar. Türü listeden seçin.

- **Parametre adı**

  Özellik parametrelere sahipse özelliği için eklediğiniz bir parametre adını ayarlar. Seçtiğinizde **Ekle**, parametre adı görünür **parametre listesi**.

- **Parametre listesi**

  Özelliğine eklenecek özniteliklerin listesini görüntüler. Listedeki her öğe, parametre adı, parametre türü ve öznitelikleri oluşur. Kullanım **Ekle** ve **Kaldır** listesini güncelleştirmek için.

- **Add**

  Belirttiğiniz parametre ekler **parametre adı** ve **parametre türü** için **parametre listesi**. Seçin **Ekle** parametre listesine eklenecek.

- **Kaldır**

  Seçtiğiniz parametre kaldırır **parametre listesi**.

- **Varsayılan özellik**

  Yalnızca MFC dispinterface. Bu özellik, arabirim için varsayılan olarak ayarlar. Özelliği yalnızca bir varsayılan arabirim olabilir; Bu kutuyu arabirimi, eklediğiniz diğer tüm özellikler için varsayılan özelliği belirttiğinizde kullanılamaz.

## <a name="idl-attributes-add-property-wizard"></a>IDL öznitelikleri, Özellik Ekleme Sihirbazı

Bir özellik için arabirim tanımlama dili (IDL) ayarlarını belirtmek için bu sayfanın bir özellik Ekleme Sihirbazı'nı kullanın.

- `id`

  Özelliği tanımlayan sayısal bir kimlik ayarlar. Bu seçenek, özel arabirimler özellikleri için kullanılamaz. Bkz: [kimliği](/windows/desktop/Midl/id) içinde *MIDL başvuru*.

- `helpcontext`

  Kullanıcı Yardım dosyasında bu özellik hakkındaki bilgileri görüntüleme sağlayan bir bağlam kimliği belirtir. Bkz: [helpcontext](/windows/desktop/Midl/helpcontext) içinde *MIDL başvuru*.

- `helpstring`

  Uygulandığı öğe açıklamak için kullanılan bir karakter dizesi belirtir. Varsayılan olarak ayarlanmış `property` &nbsp; *özelliği&nbsp;adı*. Bkz: [helpstring](/windows/desktop/Midl/helpstring) içinde *MIDL başvuru*.

### <a name="other-options"></a>Diğer Seçenekler

Tüm seçenekler için tüm özellik türleri kullanılabilir değildir.

|Seçenek|Açıklama|
|------------|-----------------|
|`bindable`|Özelliğin veri bağlamayı desteklediğini belirtir. Bkz: [bağlanabilir](/windows/desktop/Midl/bindable) içinde *MIDL başvuru*. Özelliğin stok uygulaması, bu seçenek varsayılan olarak ayarlanır ve değiştirilemez.|
|`defaultbind`|Bu tek ve bağlanabilir özelliği en iyi nesneyi temsil ettiğini gösterir. Bkz: [defaultbind](/windows/desktop/Midl/defaultbind) içinde *MIDL başvuru*.|
|`displaybind`|Bu özellik kullanıcıya bağlanabilir olarak görüntülenmesi gerektiğini gösterir. Bkz: [displaybind](/windows/desktop/Midl/displaybind) içinde *MIDL başvuru*.|
|`immediatebind`|Veritabanı bu özellik bir veri bağlama nesnesinin yapılan tüm değişikliklerin hemen bildirileceğini belirtir. Bkz: [immediatebind](/windows/desktop/Midl/immediatebind) içinde *MIDL başvuru*.|
|`defaultcollelem`|Özelliğin varsayılan koleksiyonun bir öğesi için bir erişimci işlevi gösterir. Bkz: [defaultcollelem](/windows/desktop/Midl/defaultcollelem) içinde *MIDL başvuru*.|
|`nonbrowsable`|Özellikler tarayıcısında görüntülenen olmamalıdır bir arabirim veya dispinterface üye etiketler. Bkz: [nonbrowsable](/windows/desktop/Midl/nonbrowsable) içinde *MIDL başvuru*.|
|`requestedit`|Özelliğin desteklediğini belirtir `OnRequestEdit` bildirim. Bkz: [requestedit](/windows/desktop/Midl/requestedit) içinde *MIDL başvuru*. Özelliğin stok uygulaması, bu seçenek varsayılan olarak ayarlanır ve değiştirilemez.|
|`source`|Üye özelliğinin bir olay kaynağı olduğunu gösterir. Bkz: [kaynak](/windows/desktop/Midl/source) içinde *MIDL başvuru*.|
|`hidden`|Özelliği var ancak kullanıcıya dayalı tarayıcıda görüntülenen olmamalıdır gösterir. Bkz: [gizli](/windows/desktop/Midl/hidden) içinde *MIDL başvuru*.|
|`restricted`|Özellik rasgele çağrılamaz belirtir. Bkz: [kısıtlı](/windows/desktop/Midl/restricted) içinde *MIDL başvuru*.|
|`local`|MIDL derleyicisine özelliği uzak olmadığını belirtir. Bkz: [yerel](/windows/desktop/Midl/local) içinde *MIDL başvuru*.|

## <a name="stock-properties"></a>Stok özellikleri

Bir MFC dispinterface kullanarak bir özellik ekliyoruz, [Özellik Ekleme Sihirbazı](#idl-attributes-add-property-wizard), stok özelliğinden seçebilirsiniz **özellik adı** listesinde [adları](../ide/names-add-property-wizard.md) sayfası Sihirbaz. Bu özellikler aşağıdaki gibidir:

|Özellik adı|Açıklama|
|-------------------|-----------------|
|`Appearance`|Döndürür veya denetimin görünümünü belirleyen değeri ayarlar. Denetimin `Appearance` özelliği dahil edebilir veya üç boyutlu görüntü etkileri atlayın. Bu özellik, bir ortam okuma/yazma özelliğidir.|
|`BackColor`|Döndürür veya denetimin ortam ayarlar `BackColor` özelliği bir palet (RGB) renk ya da önceden tanımlanmış sistem rengi. Varsayılan olarak, denetimin kapsayıcı ön plan rengini değerine karşılık gelir. Bu özellik, bir ortam okuma/yazma özelliğidir.|
|`BorderStyle`|Döndürür veya bir denetimin kenarlık stilini ayarlar. Bu özellik, bir okuma/yazma özelliğidir.|
|`Caption`|Döndürür veya denetimin ayarlar `Caption` özelliği. Pencerenin başlığı başlıktır. `Caption` hiçbir **üye değişkeni** uygulama türü.|
|`Enabled`|Döndürür veya denetimin ayarlar `Enabled` özelliği. Etkin bir denetim, kullanıcı tarafından oluşturulan olaylara yanıt verebilir.|
|`Font`|Döndürür veya denetimin ortam yazı tipini ayarlar. Denetim yazı tipi yoksa null değeri.|
|`ForeColor`|Döndürür veya denetimin ortam ayarlar `ForeColor` özelliği.|
|`hWnd`|Döndürür veya denetimin ayarlar `hWnd` özelliği. `hWnd` hiçbir **üye değişkeni** uygulama türü.|
|`ReadyState`|Döndürür veya denetimin ayarlar `ReadyState` özelliği. Bir denetim başlatılmamış, başlatılmış, yükleme, etkileşimli veya tam olabilir. Daha fazla bilgi için [READYSTATE](https://msdn.microsoft.com/library/aa768362.aspx) içinde *Internet SDK*.|
|`Text`|Döndürür veya bir denetimde bulunan metni ayarlar. `Text` hiçbir **üye değişkeni** uygulama türü.|
