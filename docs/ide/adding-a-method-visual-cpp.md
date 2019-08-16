---
title: Metot ekleme
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
ms.openlocfilehash: b0c8ddabc4ed08fd217545bad269f0b2e48dd49e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509544"
---
# <a name="add-a-method"></a>Metot ekleme

Projenizdeki bir arabirime bir yöntem eklemek için [Yöntem Ekleme Sihirbazı](#add-method-wizard) ' nı kullanabilirsiniz. Proje arabirimle ilişkili bir sınıf içeriyorsa, sihirbaz sınıfı da değiştirir.

**Nesneniz için bir yöntem eklemek için:**

1. **Sınıf görünümü**, yöntemi eklemek istediğiniz arabirimi göstermek için proje düğümünü genişletin.

   > [!NOTE]
   > Ayrıca, proje ilişkilendirilemediği takdirde, kitaplık düğümünün altında yer alan dispınterfaces 'e Yöntemler ekleyebilirsiniz.

1. Arabirimin adına sağ tıklayın.

1. Kısayol menüsünde, **Ekle**' yi ve ardından **Yöntem Ekle**' yi seçin.

1. Yöntem Ekleme sihirbazında, yöntemi oluşturmak için bilgileri sağlayın.

1. Sihirbazın [IDL öznitelikleri](#idl-attributes-add-method-wizard) sayfasında bu yöntem için herhangi bir arabirim tanımı dili ayarı belirtin.

1. Yöntemi eklemek için **son** ' u seçin.

## <a name="in-this-section"></a>Bu bölümde

- [Yöntem Ekleme Sihirbazı](#add-method-wizard)
- [IDL öznitelikleri, yöntem ekleme Sihirbazı](#idl-attributes-add-method-wizard)

## <a name="add-method-wizard"></a>Yöntem Ekleme Sihirbazı

Arabirime bir yöntem eklemek için bu sihirbazı kullanın. Bir yöntemi eklediğiniz proje türüne veya arabirim türüne bağlı olarak, sihirbaz farklı seçenekleri görüntüler.

### <a name="names"></a>Adlar

- **Dönüş türü**

  Yöntemi tarafından döndürülen veri türü. `HRESULT`Tüm arabirim türleri için önerilir, çünkü hataları döndürmek için standart bir yol sağlar.

  |Arabirim türü|Açıklama|
  |--------------------|-----------------|
  |Çift arabirim|`HRESULT`. Değiştirilemez.|
  |Özel arabirim|`HRESULT`. Değiştirilemez.|
  |Yerel özel arabirim|Kendi dönüş türünü sağlayın veya listeden seçin.|
  |Dispinterface|Kendi dönüş türünü sağlayın veya listeden seçin.|
  |MFC ActiveX denetimi dispınterface|Bir stok yöntemi uygularsanız, dönüş türü uygun değere ayarlanır ve değiştirilemez. **Yöntem adı** listesinden bir yöntem seçerseniz ve **Yöntem türü seç**altında **özel** ' i seçerseniz, listeden bir dönüş türü seçin.|

- **Yöntem adı**

  Metodun adını ayarlar.

  |Arabirim türü|Açıklama|
  |--------------------|-----------------|
  |ATL Dual Interface, özel arabirim ve yerel özel arabirim|Kendi yönteminizin adını sağlayın.|
  |MFC dispınterface|Kendi yöntem adınızı sağlayın veya listeden önerilen bir yöntem adı seçin. Listeden bir ad seçerseniz, **dönüş türü** kutusunda uygun değer görünür ve değiştirilemez olur.|
  |MFC ActiveX denetimi dispınterface|Kendi kendinize girin veya borsa yöntemlerinden birini seçin [Dotıkla](../mfc/reference/colecontrol-class.md#doclick) ve [Yenile](../mfc/reference/colecontrol-class.md#refresh). Daha fazla bilgi için bkz [. MFC ActiveX denetimleri: Stok yöntemleri](../mfc/mfc-activex-controls-adding-stock-methods.md)ekleniyor.|

- **Yöntem türü**

  Yalnızca MFC ActiveX denetimleri için kullanılabilir. Yöntem **adı** kutusuna bir yöntem adı sağlarsanız, listeden bir yöntem seçmek yerine bu kutu kullanılamaz.

  **Yöntem adı** listesindeki yöntemlerden birini seçerseniz, hisse senedi uygulamasını ya da özel bir uygulamayı seçin.

  |Yöntem türü|Açıklama|
  |-----------------|-----------------|
  |**Stok**|Varsayılan. **Yöntem adı** listesinde seçtiğiniz yöntemin hisse senedi uygulamasını ekler. **Stok**' ı seçerseniz **dönüş türü** değiştirilemez.|
  |**Özel**|**Yöntem adı** listesinde seçilen yöntemin saplama uygulamasını ekler. Özel yöntem türleri için kendi dönüş türünü sağlayabilir veya **dönüş türü** listesinden bir tane seçebilirsiniz.|

- **İç ad**

  Yalnızca bir MFC görüntüleme arabirimine eklenen özel yöntemler için kullanılabilir. Dağıtım haritasında kullanılan adı, üst bilgi (. h) dosyasını ve uygulama (. cpp) dosyasını ayarlar. Varsayılan olarak, bu ad **Yöntem adıyla**aynıdır. MFC dispınterface ile çalışıyorsanız veya bir MFC ActiveX denetimi görüntüleme arabirimine özel bir yöntem ekliyorsanız yöntem adını değiştirebilirsiniz.

  |Arabirim türü|Açıklama|
  |--------------------|-----------------|
  |ATL Dual Interface, özel arabirim ve yerel özel arabirim|Kullanılamıyor.|
  |MFC dispınterface|Varsayılan olarak Yöntem adına ayarlanır. Dahili adı düzenleyebilirsiniz.|
  |MFC ActiveX denetimi dispınterface|İç adı yalnızca özel yöntemler için ayarlayabilirsiniz. Stok yöntemleri dahili bir ad kullanmaz.|

- **Parametre öznitelikleri**

  **Parametre adında**belirtilen parametre için ek öznitelikleri ayarlar.

  |Parameter özniteliği|Açıklama|İzin verilen birleşimler|
  |-------------------------|-----------------|--------------------------|
  |**'Ndaki**|Parametrenin çağıran yordamdan çağrılan yordama geçtiğini gösterir.|`in`yalnızca<br /><br /> `in` ve `out`|
  |**Dışı**|İşaretçi parametresinin çağrılan yordamdan çağıran yordama (sunucudan istemciye) döndürüldüğünü gösterir.|`out`yalnızca<br /><br /> `in` ve `out`<br /><br /> `out` ve `retval`|
  |**Retval**|Parametrenin, üyenin dönüş değerini alacağını belirtir.|`retval` ve `out`|

- **Parametre türü**

  Parametrenin veri türünü ayarlar. Listeden türü seçin.

- **Parametre adı**

  Yöntemi aracılığıyla geçirilecek parametrenin adını ayarlar. Adı yazdıktan sonra, yönteminizi kullanarak geçirilecek parametreler listesine eklemek için **Ekle** ' yi seçin. Parametre adı sağlamazsanız, sihirbaz herhangi bir parametre özniteliğini (yalnızca ATL) veya **parametre türü** seçimlerini yoksayar.

  **Ekle**' yi seçtiğinizde parametre adı **parametre listesinde**görünür.

  > [!NOTE]
  > Bir parametre adı girip **Ekle**' yi seçmeden önce **son** ' u seçerseniz, parametre yöntemine eklenmez. Yöntemi bulmanız ve parametresini el ile eklemeniz gerekir.

- **Add**

  Parametre **adı**' nda belirttiğiniz parametreyi ve tür ve parametre özniteliklerini **parametre listesine**ekler. Listeye bir parametre eklemek için **Ekle** ' yi seçin.

- **Kaldır**

  Listedeki **parametre listesinde** seçtiğiniz parametreyi kaldırır.

- **Parametre listesi**

  Tüm parametreleri ve bu yöntem için o anda eklenmiş olan türlerini görüntüler. Parametreleri eklerken, sihirbaz, **parametre listesini** , değiştiricisiyle ve türüyle birlikte her parametreyi görüntüleyecek şekilde günceller.

## <a name="idl-attributes-add-method-wizard"></a>IDL öznitelikleri, yöntem ekleme Sihirbazı

Yöntem için herhangi bir arabirim tanım dili (IDL) ayarı belirtmek üzere Yöntem Ekleme Sihirbazı ' nın bu sayfasını kullanın.

- `id`

  Yöntemini tanımlayan sayısal KIMLIĞI ayarlar. Daha fazla bilgi için bkz. *MIDL başvurusunda* [kimlik](/windows/win32/Midl/id) .

  Bu kutu özel arabirimler için kullanılamaz ve MFC dispınterfaces için kullanılamaz.

- `call_as`

  Bu yerel yöntemin eşleştiribileceği uzak metodun adını belirtir. Daha fazla bilgi için *MIDL başvurusunda* [call_as](/windows/win32/Midl/call-as) bakın.

  MFC dispınterfaces için kullanılamaz.

- `helpcontext`

  Kullanıcının Yardım dosyasında bu yöntemle ilgili bilgileri görüntülemesine imkan tanıyan bir bağlam KIMLIĞI belirtir. Daha fazla bilgi için *MIDL başvurusunda* [HelpContext](/windows/win32/Midl/helpcontext) bölümüne bakın.

  MFC dispınterfaces için kullanılamaz.

- `helpstring`

  Uygulandığı öğeyi anlatmak için kullanılan bir karakter dizesini belirtir. Varsayılan olarak "Yöntem *yöntemi adı*" olarak ayarlanır. Daha fazla bilgi için *MIDL başvurusunda* [HelpString](/windows/win32/Midl/helpstring) ' i inceleyin.

  MFC dispınterfaces için kullanılamaz.

- **Ek öznitelikler**

  MFC dispınterfaces için kullanılamaz.

  |Öznitelik|Açıklama|
  |---------------|-----------------|
  |`hidden`|Yöntemin var olduğunu ancak kullanıcıya dayalı bir tarayıcıda gösterilmemesi gerektiğini gösterir. Daha fazla bilgi için bkz. *MIDL başvurusunda* [gizli](/windows/win32/Midl/hidden) .|
  |`source`|Yöntemin bir üyesinin bir olay kaynağı olduğunu gösterir. Daha fazla bilgi için bkz. *MIDL başvurusu*içindeki [kaynak](/windows/win32/Midl/source) .|
  |`local`|MıDL derleyicisine yöntemin uzak olmadığını belirtir. Daha fazla bilgi için bkz. *MIDL başvurusunda* [Yerel](/windows/win32/Midl/local) .|
  |`restricted`|Metodun rastgele çağrlamayacağını belirtir. Daha fazla bilgi için bkz. *MIDL başvurusunda* [Kısıtlanmış](/windows/win32/Midl/restricted) .|
  |`vararg`|Yöntemin değişken sayıda bağımsız değişken aldığını belirtir. Bunu gerçekleştirmek için son bağımsız değişken, bağımsız değişkenlerin geri kalanını içeren `VARIANT` türde güvenli bir dizi olmalıdır. Daha fazla bilgi için *MIDL başvurusundaki* [vararg](/windows/win32/Midl/vararg) bölümüne bakın.|
