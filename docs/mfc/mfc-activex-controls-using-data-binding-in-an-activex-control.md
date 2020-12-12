---
description: 'Daha fazla bilgi edinin: MFC ActiveX denetimleri: ActiveX denetiminde veri bağlamayı kullanma'
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
ms.openlocfilehash: eb6a6ea52dee7aaf1fcb4c9f15db89cfa5f25deb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206090"
---
# <a name="mfc-activex-controls-using-data-binding-in-an-activex-control"></a>MFC ActiveX Denetimleri: ActiveX Denetiminde Veri Bağlama İşlemini Kullanma

ActiveX denetimlerinin daha güçlü kullanımlarının biri, bir denetimin özelliğinin bir veritabanındaki belirli bir alanla bağlantılı olmasına izin veren veri bağlamadır. Bir Kullanıcı bu bağlantılı özelliğindeki verileri değiştirdiğinde, denetim veritabanına ve kayıt alanının güncelleştirildiği isteklere bildirir. Veritabanı daha sonra isteğin başarı veya başarısızlık denetimini bilgilendirir.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılması gereken eski bir teknolojidir. ActiveX 'in yerini alan modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimleri](activex-controls.md).

Bu makalede, görevinizdeki denetim tarafı ele alınmaktadır. Veri bağlama etkileşimlerinin veritabanı ile uygulanması, Denetim kapsayıcısının sorumluluğundadır. Kapsayıcıınızda veritabanı etkileşimlerini yönetme işlemi, bu belgenin kapsamı dışındadır. Veri bağlama denetimini nasıl hazırlayacağınız, bu makalenin geri kalanında açıklanmaktadır.

![Bir veri&#45;bağlantılı denetimin kavramsal diyagramı](../mfc/media/vc374v1.gif "Bir veri&#45;bağlantılı denetimin kavramsal diyagramı") <br/>
Data-Bound denetiminin kavramsal diyagramı

`COleControl`Sınıfı, veri bağlamayı uygulamak için kolay bir işlem yapan iki üye işlevi sağlar. İlk işlev olan [Boundpropertyrequestedıt](reference/colecontrol-class.md#boundpropertyrequestedit), özellik değerini değiştirmek için izin istemek üzere kullanılır. [BoundPropertyChanged](reference/colecontrol-class.md#boundpropertychanged), ikinci işlev, özellik değeri başarıyla değiştirildikten sonra çağrılır.

Bu makalede aşağıdaki konular ele alınmaktadır:

- [Bağlanabilir hisse senedi özelliği oluşturma](#vchowcreatingbindablestockproperty)

- [Bağlanabilir get/set yöntemi oluşturma](#vchowcreatingbindablegetsetmethod)

## <a name="creating-a-bindable-stock-property"></a><a name="vchowcreatingbindablestockproperty"></a> Bağlanabilir hisse senedi özelliği oluşturma

[Bağlanabilir bir get/set yöntemi](#vchowcreatingbindablegetsetmethod)istediğinizden daha büyük olsa da, veri bağlantılı bir stok özelliği oluşturmak mümkündür.

> [!NOTE]
> Hisse senedi özellikleri `bindable` `requestedit` Varsayılan olarak ve özniteliklerine sahiptir.

#### <a name="to-add-a-bindable-stock-property-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı 'Nı kullanarak bağlanabilir bir hisse senedi özelliği eklemek için

1. [MFC ActiveX Denetim Sihirbazı 'nı](reference/mfc-activex-control-wizard.md)kullanarak bir proje başlatın.

1. Denetiminizin arabirim düğümüne sağ tıklayın.

   Bu, kısayol menüsünü açar.

1. Kısayol menüsünde, **Ekle** ' ye ve ardından **Özellik Ekle**' ye tıklayın.

1. **Özellik adı** açılır listesinden girdilerden birini seçin. Örneğin, **metin**' i seçebilirsiniz.

   **Metin** bir stok özelliği olduğundan, **bağlanabilir** ve **requestedıt** öznitelikleri zaten işaretlendi.

1. Öznitelikleri, projenin içindeki Özellik tanımına eklemek için **IDL öznitelikleri** sekmesinden aşağıdaki onay kutularını seçin: **displaybind** ve **defaultbind** . IDL dosyası. Bu öznitelikler, denetimi kullanıcıya görünür hale getirir ve stok özelliğini varsayılan bağlanabilir özelliği yapar.

Bu noktada, denetiminiz veri kaynağındaki verileri görüntüleyebilir, ancak kullanıcı veri alanlarını güncelleştiremez. Denetiminizin verileri de güncelleştirebilmesini istiyorsanız, `OnOcmCommand` [OnOcmCommand](mfc-activex-controls-subclassing-a-windows-control.md) işlevini aşağıdaki gibi görünecek şekilde değiştirin:

[!code-cpp[NVC_MFC_AxData#1](codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]

Artık, denetimi kaydeden projeyi oluşturabilirsiniz. Denetimi bir iletişim kutusuna eklediğinizde, **veri alanı** ve **veri kaynağı** özellikleri eklenir ve artık denetimde görüntülenecek bir veri kaynağı ve alanı seçebilirsiniz.

## <a name="creating-a-bindable-getset-method"></a><a name="vchowcreatingbindablegetsetmethod"></a> Bağlanabilir get/set yöntemi oluşturma

Veri bağlantılı get/set yöntemine ek olarak, [bağlanabilir bir stok özelliği](#vchowcreatingbindablestockproperty)de oluşturabilirsiniz.

> [!NOTE]
> Bu yordam, bir Windows denetimini alt sınıflara uygulayan bir ActiveX Denetim projenize sahip olduğunuzu varsayar.

#### <a name="to-add-a-bindable-getset-method-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı 'nı kullanarak bağlanabilir bir get/set yöntemi eklemek için

1. Denetiminizin projesini yükleyin.

1. **Denetim ayarları** sayfasında, denetimin alt sınıfı olarak bir pencere sınıfı seçin. Örneğin, bir düzenleme denetimini alt sınıflara ayırmak isteyebilirsiniz.

1. Denetiminizin projesini yükleyin.

1. Denetiminizin arabirim düğümüne sağ tıklayın.

   Bu, kısayol menüsünü açar.

1. Kısayol menüsünde, **Ekle** ' ye ve ardından **Özellik Ekle**' ye tıklayın.

1. **Özellik adı kutusuna özelliğin** adını yazın. `MyProp`Bu örnek için kullanın.

1. **Özellik türü** açılan liste kutusundan bir veri türü seçin. **`short`** Bu örnek için kullanın.

1. **Uygulama türü** Için, **get/set yöntemleri**' ne tıklayın.

1. Öznitelikleri projenin içindeki Özellik tanımına eklemek için IDL öznitelikleri sekmesinden aşağıdaki onay kutularını seçin: **bağlanabilir**, **requestedıt**, **displaybind** ve **defaultbind** . IDL dosyası. Bu öznitelikler, denetimi kullanıcıya görünür hale getirir ve stok özelliğini varsayılan bağlanabilir özelliği yapar.

1. **Finish (Son)** düğmesine tıklayın.

1. `SetMyProp`İşlevin gövdesini aşağıdaki kodu içerecek şekilde değiştirin:

   [!code-cpp[NVC_MFC_AxData#2](codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_2.cpp)]

1. Ve işlevlerine geçirilen parametresi, `BoundPropertyChanged` `BoundPropertyRequestEdit` içindeki özelliği için ID () özniteliğine geçirilen parametre olan özelliğinin DISPID 'dir. IDL dosyası.

1. [OnOcmCommand](mfc-activex-controls-subclassing-a-windows-control.md) işlevini aşağıdaki kodu içerecek şekilde değiştirin:

   [!code-cpp[NVC_MFC_AxData#1](codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]

1. `OnDraw`İşlevi aşağıdaki kodu içerecek şekilde değiştirin:

   [!code-cpp[NVC_MFC_AxData#3](codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_3.cpp)]

1. Üstbilgi dosyasının genel bölümüne denetim sınıfınızın başlık dosyasını ekleyin, üye değişkenleri için aşağıdaki tanımları (oluşturucular) ekleyin:

   [!code-cpp[NVC_MFC_AxData#4](codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_4.h)]

1. İşlevdeki son satırı aşağıdaki satırı yapın `DoPropExchange` :

   [!code-cpp[NVC_MFC_AxData#5](codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_5.cpp)]

1. `OnResetState`İşlevi aşağıdaki kodu içerecek şekilde değiştirin:

   [!code-cpp[NVC_MFC_AxData#6](codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_6.cpp)]

1. `GetMyProp`İşlevi aşağıdaki kodu içerecek şekilde değiştirin:

   [!code-cpp[NVC_MFC_AxData#7](codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_7.cpp)]

Artık, denetimi kaydeden projeyi oluşturabilirsiniz. Denetimi bir iletişim kutusuna eklediğinizde, **veri alanı** ve **veri kaynağı** özellikleri eklenir ve artık denetimde görüntülenecek bir veri kaynağı ve alanı seçebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)
