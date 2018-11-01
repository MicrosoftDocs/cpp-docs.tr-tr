---
title: 'MFC ActiveX Denetimleri: ActiveX Denetiminde Veri Bağlama İşlemini Kullanma'
ms.date: 09/12/2018
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
ms.openlocfilehash: 54cfbc6d31c0c86163400df691dec47e0c093d36
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50603664"
---
# <a name="mfc-activex-controls-using-data-binding-in-an-activex-control"></a>MFC ActiveX Denetimleri: ActiveX Denetiminde Veri Bağlama İşlemini Kullanma

ActiveX denetimleri daha güçlü kullanımlarını sağlayan bir veritabanında belirli bir alanla bağlamak için denetimin bir özelliğine veri bağlama biridir. Bir kullanıcı bu bağlı özelliğin veri değiştirdiğinde, Denetim veritabanı ve kayıt alanı güncelleştirilmesi istekleri bildirir. Veritabanı denetimi başarılı veya başarısız istek sonra bildirir.

>[!IMPORTANT]
> ActiveX yeni geliştirme projeleri için kullanılmaması gereken eski bir teknolojidir. ActiveX yerine geçen modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimlerini](activex-controls.md).

Bu makale, görevin denetim yan kapsar. Veri bağlama etkileşimleri veritabanı ile uygulama denetim kapsayıcısı sorumluluğundadır. Veritabanı etkileşimleri kapsayıcınızda nasıl yönettiğiniz, bu belgenin kapsamı dışındadır olduğu. Veri bağlama için denetimin nasıl hazırlamanız bu makalenin geri kalanında açıklanmıştır.

![Bir veri kavramsal diyagramı&#45;bağlı denetim](../mfc/media/vc374v1.gif "vc374v1") veriye bağlı denetim kavramsal diyagramı

`COleControl` Sınıfı uygulamak için kolay bir işlem bağlama verilerini iki üye işlevleri sağlar. İlk işlev [BoundPropertyRequestEdit](../mfc/reference/colecontrol-class.md#boundpropertyrequestedit), özellik değerini değiştirmek için izin istemek için kullanılır. [BoundPropertyChanged](../mfc/reference/colecontrol-class.md#boundpropertychanged), ikinci işlev, özellik değeri başarıyla değiştirildikten sonra çağırılır.

Bu makalede, aşağıdaki konular ele alınmaktadır:

- [Bağlanabilir bir stok özelliği oluşturma](#vchowcreatingbindablestockproperty)

- [Bağlanabilir alma/ayarlama yöntemi oluşturma](#vchowcreatingbindablegetsetmethod)

##  <a name="vchowcreatingbindablestockproperty"></a> Bağlanabilir bir stok özelliği oluşturma

Size daha isteyeceksinizdir olmasına rağmen bir verilere bağlı stok özelliği oluşturmak mümkün bir [bağlanabilir alma/ayarlama yöntemi](#vchowcreatingbindablegetsetmethod).

> [!NOTE]
>  Stok özellikleri sahip `bindable` ve `requestedit` varsayılan öznitelikler.

#### <a name="to-add-a-bindable-stock-property-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı'nı kullanarak bağlanabilir bir stok özelliği eklemek için

1. Bir proje kullanmaya başlamak [MFC ActiveX Denetim Sihirbazı](../mfc/reference/mfc-activex-control-wizard.md).

1. Denetiminiz için arabirimin düğümüne sağ tıklayın.

   Bu kısayol menüsü açılır.

1. Kısayol menüsünden tıklayın **Ekle** ve ardından **Özellik Ekle**.

1. Girişlerden birini **özellik adı** aşağı açılan listesi. Örneğin, seçebileceğiniz **metin**.

   Çünkü **metin** bir stok özelliği **bağlanabilir** ve **requestedit** öznitelikleri zaten denetlenir.

1. Aşağıdaki onay kutularından birini seçin **IDL öznitelikleri** sekmesi: **displaybind** ve **defaultbind** öznitelikleri, projenin özellik tanımı eklemek için. IDL dosyası. Bu öznitelikler denetim kullanıcıya görünür yapabilir ve stok özelliği varsayılan bağlanılabilir özellik.

Bu noktada, denetim bir veri kaynağından verileri görüntüleyebilirsiniz, ancak kullanıcı veri alanlarını güncelleştirmeniz mümkün olmayacaktır. Ayrıca verileri güncelleştirme, değişiklik yapabilmek için denetim istiyorsanız `OnOcmCommand` [OnOcmCommand](../mfc/mfc-activex-controls-subclassing-a-windows-control.md) işlevi şu şekilde aramak için:

[!code-cpp[NVC_MFC_AxData#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]

Artık denetim kaydolacak proje oluşturabilirsiniz. Bir iletişim kutusu denetimi eklediğinizde **veri alanı** ve **veri kaynağı** özellikler eklendi ve artık bir veri kaynağı ve Denetimde görüntülenecek alan seçebilirsiniz.

##  <a name="vchowcreatingbindablegetsetmethod"></a> Bağlanabilir alma/ayarlama yöntemi oluşturma

Bir veri alma/ayarlama yöntemi bağlantılı yanı sıra da oluşturabilirsiniz bir [bağlanılabilir stok özellik](#vchowcreatingbindablestockproperty).

> [!NOTE]
>  Bu yordamı, bir Windows denetimini alt sınıflara ayıran proje bir ActiveX denetimi olduğunu varsayar.

#### <a name="to-add-a-bindable-getset-method-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı'nı kullanarak bir bağlanabilir alma/ayarlama yöntemini eklemek için

1. Denetiminizin proje yükleyin.

1. Üzerinde **denetim ayarları** sayfasında, denetimi alt pencere sınıfı seçin. Örneğin, bir düzenleme denetimini alt sınıf isteyebilirsiniz.

1. Denetiminizin proje yükleyin.

1. Denetiminiz için arabirimin düğümüne sağ tıklayın.

   Bu kısayol menüsü açılır.

1. Kısayol menüsünden tıklayın **Ekle** ve ardından **Özellik Ekle**.

1. Özellik adı, türü **özellik adı** kutusu. Kullanım `MyProp` bu örneğin.

1. Bir veri türünden seçin **özellik türü** aşağı açılan liste kutusu. Kullanım **kısa** bu örneğin.

1. İçin **uygulama türü**, tıklayın **Get/Set yöntemleri**.

9. IDL öznitelikleri sekmesinden aşağıdaki onay kutularını işaretleyin: **bağlanabilir**, **requestedit**, **displaybind**, ve **defaultbind** eklemek için Projenin özellik tanımı öznitelikleri. IDL dosyası. Bu öznitelikler denetim kullanıcıya görünür yapabilir ve stok özelliği varsayılan bağlanılabilir özellik.

10. **Son**'a tıklayın.

11. Gövde metni değiştirme `SetMyProp` aşağıdaki kodu içeren işlev:

   [!code-cpp[NVC_MFC_AxData#2](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_2.cpp)]

12. Parametre geçirilen `BoundPropertyChanged` ve `BoundPropertyRequestEdit` işlevleri, dispid özelliğinin id() özniteliği için bir özellik için geçirilen parametre. IDL dosyası.

13. Değiştirme [OnOcmCommand](../mfc/mfc-activex-controls-subclassing-a-windows-control.md) aşağıdaki kodu içerecek şekilde işlev:

   [!code-cpp[NVC_MFC_AxData#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]

14. Değiştirme `OnDraw` aşağıdaki kodu içeren işlev:

   [!code-cpp[NVC_MFC_AxData#3](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_3.cpp)]

15. Üye değişkenleri aşağıdaki tanımları (oluşturucular), denetim sınıfı için üst bilgi dosyası üst bilgi dosyasının ortak bölümüne ekleyin:

   [!code-cpp[NVC_MFC_AxData#4](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_4.h)]

16. Aşağıdaki satırı son satırında olun `DoPropExchange` işlevi:

   [!code-cpp[NVC_MFC_AxData#5](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_5.cpp)]

17. Değiştirme `OnResetState` aşağıdaki kodu içeren işlev:

   [!code-cpp[NVC_MFC_AxData#6](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_6.cpp)]

18. Değiştirme `GetMyProp` aşağıdaki kodu içeren işlev:

   [!code-cpp[NVC_MFC_AxData#7](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_7.cpp)]

Artık denetim kaydolacak proje oluşturabilirsiniz. Bir iletişim kutusu denetimi eklediğinizde **veri alanı** ve **veri kaynağı** özellikler eklendi ve artık bir veri kaynağı ve Denetimde görüntülenecek alan seçebilirsiniz.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)

