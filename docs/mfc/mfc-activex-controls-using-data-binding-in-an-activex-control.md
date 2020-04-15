---
title: 'MFC ActiveX Denetimleri: ActiveX Denetiminde Veri Bağlama İşlemini Kullanma'
ms.date: 11/19/2018
f1_keywords:
- bindable
- requestedit
- defaultbind
- displaybind
- dispid
helpviewer_keywords:
- MFC ActiveX controls [MFC], data binding
- data binding [MFC], MFC ActiveX controls
- data-bound controls [MFC], MFC ActiveX controls
- controls [MFC], data binding
- bound controls [MFC], MFC ActiveX
ms.assetid: 476b590a-bf2a-498a-81b7-dd476bd346f1
ms.openlocfilehash: 41ac0180242aea3143a1df2c32dc81fb18cd7dca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370789"
---
# <a name="mfc-activex-controls-using-data-binding-in-an-activex-control"></a>MFC ActiveX Denetimleri: ActiveX Denetiminde Veri Bağlama İşlemini Kullanma

ActiveX denetimlerinin en güçlü kullanımlarından biri, denetimin bir özelliğinin veritabanındaki belirli bir alana bağlanmasını sağlayan veri bağlamadır. Bir kullanıcı bu bağlı özellikteki verileri değiştirirse, denetim veritabanını bilgilendirir ve kayıt alanının güncelleştirilmesini ister. Veritabanı daha sonra isteğin başarısını veya başarısızlığını denetler.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılmaması gereken eski bir teknolojidir. ActiveX'in yerini alabilecek modern teknolojiler hakkında daha fazla bilgi için [ActiveX Denetimleri'ne](activex-controls.md)bakın.

Bu makale, görevinizin denetim tarafını kapsar. Veritabanı ile veri bağlama etkileşimleri uygulanması denetim kapsayıcısorumluluğundadır. Kapsayıcınızdaki veritabanı etkileşimlerini nasıl yönetmiş olduğunuz bu belgenin kapsamı dışındadır. Veri bağlama için denetimi nasıl hazırlayacağınız bu makalenin geri kalanında açıklanmıştır.

![Bir veri&#45;bağlı denetiminin kavramsal diyagramı](../mfc/media/vc374v1.gif "Bir veri&#45;bağlı denetiminin kavramsal diyagramı") <br/>
Veriye Bağlı Kontrolün Kavramsal Diyagramı

Sınıf, `COleControl` veri bağlamayı kolay bir işlem yapan iki üye işlev sağlar. İlk işlev, [BoundPropertyRequestEdit](../mfc/reference/colecontrol-class.md#boundpropertyrequestedit), özellik değerini değiştirmek için izin istemek için kullanılır. İkinci işlev olan [BoundPropertyChanged,](../mfc/reference/colecontrol-class.md#boundpropertychanged)özellik değeri başarıyla değiştirildikten sonra çağrılır.

Bu makalede aşağıdaki konular ele:

- [Bindable Stok Özelliği Oluşturma](#vchowcreatingbindablestockproperty)

- [Bindable Get/Set Yöntemi Oluşturma](#vchowcreatingbindablegetsetmethod)

## <a name="creating-a-bindable-stock-property"></a><a name="vchowcreatingbindablestockproperty"></a>Bindable Stok Özelliği Oluşturma

Bağlayıcı bir [get/set yöntemi](#vchowcreatingbindablegetsetmethod)isteme olasılığınız daha yüksek olsa da, verilere bağlı bir stok özelliği oluşturmak mümkündür.

> [!NOTE]
> Stok özellikleri `bindable` varsayılan `requestedit` olarak ve öznitelikleri ne var.

#### <a name="to-add-a-bindable-stock-property-using-the-add-property-wizard"></a>Özellik Ekle Sihirbazı'nı kullanarak bağlanabilir bir stok özelliği eklemek için

1. [MFC ActiveX Denetim Sihirbazı'nı](../mfc/reference/mfc-activex-control-wizard.md)kullanarak proje başlatın.

1. Denetiminiz için arabirim düğümüne sağ tıklayın.

   Bu kısayol menüsünü açar.

1. Kısayol menüsünden **Ekle'yi** tıklatın ve ardından **Özellik Ekle'yi**tıklatın.

1. **Özellik Adı** açılır listesinden girişlerden birini seçin. Örneğin, **Metin'i**seçebilirsiniz.

   **Metin** bir stok özelliği olduğundan, **bağlanabilir** ve **istenen** öznitelikleri zaten denetlenir.

1. **IDL Öznitelikleri** sekmesinden aşağıdaki onay kutularını seçin: projenin özelliği tanımına öznitelikleri eklemek için **displaybind** ve **defaultbind.** IDL dosyası. Bu öznitelikler denetimi kullanıcı tarafından görünür hale getirmek ve stok özelliği varsayılan bağlanabilir özelliği olun.

Bu noktada, denetiminiz bir veri kaynağından veri görüntüleyebilir, ancak kullanıcı veri alanlarını güncelleştiremez. Denetiminizin verileri de güncelleyebilmesini istiyorsanız, `OnOcmCommand` [OnOcmCommand](../mfc/mfc-activex-controls-subclassing-a-windows-control.md) işlevini aşağıdaki gibi görünecek şekilde değiştirin:

[!code-cpp[NVC_MFC_AxData#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]

Artık denetimi kaydedecek projeyi oluşturabilirsiniz. Denetimi bir iletişim kutusuna eklediğinizde, **Veri Alanı** ve **Veri Kaynağı** özellikleri eklenmiş olur ve artık denetimde görüntülenecek bir veri kaynağı ve alan seçebilirsiniz.

## <a name="creating-a-bindable-getset-method"></a><a name="vchowcreatingbindablegetsetmethod"></a>Bindable Get/Set Yöntemi Oluşturma

Veriye bağlı get/set yöntemine ek olarak, [bağlanabilir](#vchowcreatingbindablestockproperty)bir stok özelliği de oluşturabilirsiniz.

> [!NOTE]
> Bu yordam, windows denetimi alt sınıfları bir ActiveX denetim proje varsayıyor.

#### <a name="to-add-a-bindable-getset-method-using-the-add-property-wizard"></a>Özellik Ekle Sihirbazı'nı kullanarak bağlayıcı kutulanabilir get/set yöntemi eklemek için

1. Denetiminizin projesini yükleyin.

1. Denetim **Ayarları** sayfasında, denetim için alt sınıf için bir pencere sınıfı seçin. Örneğin, bir EDIT denetimini alt sınıfa almak isteyebilirsiniz.

1. Denetiminizin projesini yükleyin.

1. Denetiminiz için arabirim düğümüne sağ tıklayın.

   Bu kısayol menüsünü açar.

1. Kısayol menüsünden **Ekle'yi** tıklatın ve ardından **Özellik Ekle'yi**tıklatın.

1. **Özellik Adı** kutusuna özellik adını yazın. Bu `MyProp` örnek için kullanın.

1. **Özellik Türü** açılır liste kutusundan bir veri türü seçin. Bu örnek için **kısa** kullanın.

1. **Uygulama Türü** **için, Yöntemleri Al/Ayarla'yı**tıklatın.

1. IDL Öznitelikleri sekmesinden aşağıdaki onay kutularını seçin: **bindable**, **requestedit**, **displayedd**, ve **varsayılan bindirilmiş** projenin özelliği tanımına öznitelikleri eklemek için . IDL dosyası. Bu öznitelikler denetimi kullanıcı tarafından görünür hale getirmek ve stok özelliği varsayılan bağlanabilir özelliği olun.

1. **Son**'a tıklayın.

1. `SetMyProp` Aşağıdaki kodu içererek işlevin gövdesini değiştirin:

   [!code-cpp[NVC_MFC_AxData#2](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_2.cpp)]

1. Parametre geçirilen `BoundPropertyChanged` ve `BoundPropertyRequestEdit` işlevleri özelliği, hangi parametre id() özelliği için geçirilen parametre dispid olduğunu . IDL dosyası.

1. [OnOcmCommand](../mfc/mfc-activex-controls-subclassing-a-windows-control.md) işlevini aşağıdaki kodu içererek değiştirin:

   [!code-cpp[NVC_MFC_AxData#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]

1. `OnDraw` İşlevi aşağıdaki kodu içererek değiştirin:

   [!code-cpp[NVC_MFC_AxData#3](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_3.cpp)]

1. Üstbilgi dosyasının ortak bölümüne denetim sınıfınız için üstbilgi dosyası, üye değişkenler için aşağıdaki tanımları (oluşturucular) ekleyin:

   [!code-cpp[NVC_MFC_AxData#4](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_4.h)]

1. Aşağıdaki satırı `DoPropExchange` işlevdeki son satır yapın:

   [!code-cpp[NVC_MFC_AxData#5](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_5.cpp)]

1. `OnResetState` İşlevi aşağıdaki kodu içererek değiştirin:

   [!code-cpp[NVC_MFC_AxData#6](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_6.cpp)]

1. `GetMyProp` İşlevi aşağıdaki kodu içererek değiştirin:

   [!code-cpp[NVC_MFC_AxData#7](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_7.cpp)]

Artık denetimi kaydedecek projeyi oluşturabilirsiniz. Denetimi bir iletişim kutusuna eklediğinizde, **Veri Alanı** ve **Veri Kaynağı** özellikleri eklenmiş olur ve artık denetimde görüntülenecek bir veri kaynağı ve alan seçebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Kontrolleri](../mfc/mfc-activex-controls.md)
