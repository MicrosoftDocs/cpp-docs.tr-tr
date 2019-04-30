---
title: Bir yöntem ekleyin
ms.date: 11/09/2018
f1_keywords:
- vc.codewiz.method.overview
- vc.codewiz.method.idlattrib
helpviewer_keywords:
- add method wizard [C++]
- methods [C++], adding
- methods [C++], adding using wizards
- IDL attributes, add method wizard
ms.assetid: 4ba4e45f-fa38-4d5e-af44-cbec0a7ab558
ms.openlocfilehash: 23fb05e633713016b1f6289f73a916502736af10
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346008"
---
# <a name="add-a-method"></a>Bir yöntem ekleyin

Kullanabileceğiniz [yöntem Ekleme Sihirbazı](#add-method-wizard) projenize bir arabirimde bir yöntemi eklemek için. Proje ile ilişkilendirilen bir sınıf içeriyorsa, sihirbaz sınıfı çok değiştirir.

**Nesneniz için bir yöntem eklemek için:**

1. İçinde **sınıf görünümü**, yöntem eklemek istediğiniz arabirim görüntülemesi için proje düğümünü genişletin.

   > [!NOTE]
   > Proje öznitelikli sürece, bu, kitaplık düğümü altında bulunan görüntü arabirimlerinde yöntemler ekleyebilirsiniz.

1. Arabirim adına sağ tıklayın.

1. Kısayol menüsünde **Ekle**ve ardından **Ekle yöntemi**.

1. Yöntem Ekleme Sihirbazı'nda yöntemi oluşturmak için bilgileri sağlayın.

1. Tüm Bu yöntemde için arabirim tanımlama dili ayarlarını belirtin [IDL öznitelikleri](#idl-attributes-add-method-wizard) Sihirbazı sayfası.

1. Seçin **son** yöntemi eklemek için.

## <a name="in-this-section"></a>Bu bölümde

- [Yöntem Ekleme Sihirbazı](#add-method-wizard)
- [IDL öznitelikleri, yöntem Ekleme Sihirbazı](#idl-attributes-add-method-wizard)

## <a name="add-method-wizard"></a>Yöntem Ekleme Sihirbazı

Bir yöntem bir arabirim eklemek için bu sihirbazı kullanın. Proje türü veya bir yöntem eklediğiniz bir arabirim türüne bağlı olarak sihirbazın farklı seçenekleri görüntüler.

### <a name="names"></a>Adlar

- **Dönüş türü**

  Yöntem tarafından döndürülen veri türü. `HRESULT` hatalarını döndürmek için standart bir yol sağladığından, tüm arabirim türleri için önerilir.

  |Arabirim türü|Açıklama|
  |--------------------|-----------------|
  |Çift arabirim|`HRESULT`. Değiştirilemez.|
  |Özel arabirim|`HRESULT`. Değiştirilemez.|
  |Yerel özel arabirimi|Kendi dönüş türü belirtin veya listeden seçin.|
  |Dispinterface|Kendi dönüş türü belirtin veya listeden seçin.|
  |MFC ActiveX denetimi dispinterface|Stok metodu uygularsanız, dönüş türü uygun değere ayarlanır ve değiştirilemez. Bir yöntemi seçerseniz **yöntem adı** listesinde ve seçin **özel** altında **yöntemi türünü seçin**, listeden bir dönüş türü seçin.|

- **Yöntem adı**

  Yöntemin adını ayarlar.

  |Arabirim türü|Açıklama|
  |--------------------|-----------------|
  |ATL çift arabirim, özel arabirim ve yerel özel arabirimi|Kendi yöntem adını belirtin.|
  |MFC dispinterface|Kendi yöntemi adı belirtin veya listeden bir önerilen yöntem adı seçin. Listeden bir ad seçerseniz, uygun değere görünür **dönüş türü** kutusu ve değiştirilemez.|
  |MFC ActiveX denetimi dispinterface|Stok yöntemlerden birini seçin veya kendi sağlamak [DoClick](../mfc/reference/colecontrol-class.md#doclick) ve [Yenile](../mfc/reference/colecontrol-class.md#refresh). Daha fazla bilgi için [MFC ActiveX denetimleri: Stok yöntemler ekleme](../mfc/mfc-activex-controls-adding-stock-methods.md).|

- **Yöntem türü**

  MFC ActiveX denetimleri için kullanılabilir. Yöntem adı'sağlarsanız **yöntem adı** kutusunda, listeden bir yöntem seçmek yerine bu kutuyu kullanılamıyor.

  Metotlarından birini seçerseniz **yöntem adı** listesinde, stok uygulaması ya da özel bir uygulama seçin.

  |Yöntem türü|Açıklama|
  |-----------------|-----------------|
  |**Hisse senedi**|Varsayılan. Seçtiğiniz yöntem stok uygulaması ekler **yöntem adı** listesi. **Dönüş türü** seçerseniz değiştirilemez **hisse senedi**.|
  |**Özel**|Seçilen yöntemin bir saplama uygulaması ekler **yöntem adı** listesi. Özel yöntem türleri için kendi dönüş türü sağlayabilir veya birinden seçebilirsiniz **dönüş türü** listesi.|

- **İç adı**

  Yalnızca bir MFC dispinterface için eklenen özel yöntemler için kullanılabilir. Dağıtım eşlemesi, üstbilgi (.h) dosyası ve uygulama (.cpp) dosyası içinde kullanılan adını ayarlar. Varsayılan olarak, bu adı aynı olan **yöntem adı**. Bir MFC dispinterface ile çalışıyorsanız veya özel bir yöntem için bir MFC ActiveX denetimi dispinterface ekliyorsanız, yöntem adını değiştirebilirsiniz.

  |Arabirim türü|Açıklama|
  |--------------------|-----------------|
  |ATL çift arabirim, özel arabirim ve yerel özel arabirimi|Kullanılabilir değil.|
  |MFC dispinterface|Yöntem adı için varsayılan olarak ayarlayın. İç adını düzenleyebilirsiniz.|
  |MFC ActiveX denetimi dispinterface|Yalnızca özel yöntemler için iç ad ayarlayabilirsiniz. Stok yöntemler, bir iç adını kullanmayın.|

- **Parametre öznitelikleri**

  Herhangi bir ek özniteliği için belirtilen parametre ayarlar **parametre adı**.

  |Parametre özniteliği|Açıklama|İzin verilen birleşimleri|
  |-------------------------|-----------------|--------------------------|
  |**İçinde**|Parametrenin çağıran yordamdan çağrılan yordama geçirildiğini gösterir.|`in` Yalnızca<br /><br /> `in` ve `out`|
  |**Çıkış**|İşaretçi parametresi çağrılan yordamdan çağıran yordama (sunucudan istemciye) döndürülür gösterir.|`out` Yalnızca<br /><br /> `in` ve `out`<br /><br /> `out` ve `retval`|
  |**retval**|Parametrenin, üyenin dönüş değeri alır gösterir.|`retval` ve `out`|

- **Parametre türü**

  Parametrenin veri türünü ayarlar. Türü listeden seçin.

- **Parametre adı**

  Yönteminiz iletilecek parametre adını ayarlar. Adını yazdıktan sonra seçin **Ekle** yönteminiz geçer parametre listesi eklemek için. Parametre adı sağlamazsanız, sihirbazın herhangi bir parametre özniteliği (sadece ATL) göz ardı eder veya **parametre türü** seçimleri.

  Seçtiğinizde **Ekle**, parametre adı görünür **parametre listesi**.

  > [!NOTE]
  > Parametre adı sağlayın ve ardından **son** seçtiğiniz önce **Ekle**, parametre yönteme eklenmez. Yöntemini bulun ve parametre el ile Ekle gerekir.

- **Add**

  Belirttiğiniz parametre ekler **parametre adı**ve bunun türü ve parametre öznitelikleri için **parametre listesi**. Seçin **Ekle** parametre listesine eklenecek.

- **Kaldır**

  Seçtiğiniz parametre kaldırır **parametre listesi** listeden.

- **Parametre listesi**

  Tüm parametreler ve değiştiriciler ve şu anda yöntemi için eklenen türleri görüntüler. Parametre ekleme gibi sihirbaz güncelleştirir **parametre listesi** değiştiricisi ve türü her parametre görüntülenecek.

## <a name="idl-attributes-add-method-wizard"></a>IDL öznitelikleri, yöntem Ekleme Sihirbazı

Yöntem için arabirim tanımlama dili (IDL) ayarlarını belirtmek için bu sayfanın bir yöntem Ekleme Sihirbazı'nı kullanın.

- `id`

  Yükleme yöntemini tanımlayan sayısal bir kimlik ayarlar. Daha fazla bilgi için [kimliği](/windows/desktop/Midl/id) içinde *MIDL başvuru*.

  Bu kutu özel arabirimler için kullanılamaz ve MFC görüntüleme için kullanılamaz.

- `call_as`

  Bu yerel yöntemi eşlenebilir uzak bir yöntem adını belirtir. Daha fazla bilgi için [call_as](/windows/desktop/Midl/call-as) içinde *MIDL başvuru*.

  MFC görüntüleme için kullanılamaz.

- `helpcontext`

  Yardım dosyasında bu yöntem kullanıcı görünümü bilgi sağlayan bir bağlam kimliği belirtir. Daha fazla bilgi için [helpcontext](/windows/desktop/Midl/helpcontext) içinde *MIDL başvuru*.

  MFC görüntüleme için kullanılamaz.

- `helpstring`

  Uygulandığı öğe açıklamak için kullanılan bir karakter dizesi belirtir. Varsayılan olarak Ayarla "yöntemi *yöntem adı*." Daha fazla bilgi için [helpstring](/windows/desktop/Midl/helpstring) içinde *MIDL başvuru*.

  MFC görüntüleme için kullanılamaz.

- **Ek öznitelikler**

  MFC görüntüleme için kullanılamaz.

  |Öznitelik|Açıklama|
  |---------------|-----------------|
  |`hidden`|Yöntem var ancak kullanıcıya dayalı tarayıcıda görüntülenen olmamalıdır gösterir. Daha fazla bilgi için [gizli](/windows/desktop/Midl/hidden) içinde *MIDL başvuru*.|
  |`source`|Bir olay kaynağı yöntemi üyesi olduğunu gösterir. Daha fazla bilgi için [kaynak](/windows/desktop/Midl/source) içinde *MIDL başvuru*.|
  |`local`|MIDL derleyicisine yöntemi uzak olmadığını belirtir. Daha fazla bilgi için [yerel](/windows/desktop/Midl/local) içinde *MIDL başvuru*.|
  |`restricted`|Yöntemi rasgele çağrılamaz belirtir. Daha fazla bilgi için [kısıtlı](/windows/desktop/Midl/restricted) içinde *MIDL başvuru*.|
  |`vararg`|Yöntemi, değişken sayıda bağımsız değişken aldığını belirtir. Bunu yapmak için son bağımsız değişken bir güvenli dizisi olmalıdır `VARIANT` bağımsız değişkenler kalanı içeren türü. Daha fazla bilgi için [vararg](/windows/desktop/Midl/vararg) içinde *MIDL başvuru*.|
