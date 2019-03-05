---
title: 'Otomasyon istemcileri: Tür kitaplıklarını kullanma'
ms.date: 11/04/2016
f1_keywords:
- MkTypLib
helpviewer_keywords:
- clients, Automation
- dispatch class [MFC]
- Automation clients, type libraries
- type libraries, Automation clients
- ODL (Object Description Language)
- ODL files
- classes [MFC], dispatch
- MkTypLib tool
- .odl files
ms.assetid: d405bc47-118d-4786-b371-920d035b2047
ms.openlocfilehash: 32179f3913b52ca46f9ea7314b9957f4f4970713
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57282948"
---
# <a name="automation-clients-using-type-libraries"></a>Otomasyon istemcileri: Tür kitaplıklarını kullanma

Otomasyon istemcileri istemcileridir sunucularının nesneleri değiştirmek için sunucu nesneleri özellikler ve yöntemler hakkında bilgi olması gerekir. Özellikleri, veri türlerine sahip; yöntemler, genellikle dönüş değerleri ve parametreleri kabul eder. İstemci, sunucu nesne türü için statik olarak bağlamak için bunların hepsi veri türleri hakkında daha fazla bilgi gerektirir.

Bu tür bilgiler, çeşitli yollarla bilinen yapılabilir. Önerilen yöntem, bir tür kitaplığı oluşturmaktır.

Hakkında bilgi için [MkTypLib](/windows/desktop/Midl/differences-between-midl-and-mktyplib), Windows SDK'sı bakın.

Visual C++ tür kitaplığı dosyası okuma ve türetilen bir gönderme sınıf oluşturma [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md). Bu sınıfın bir nesnesi, özelliklerini ve bu sunucu nesnesinin çoğaltma işlemlerini sahiptir. Bu nesnenin özellikleri ve işlemleri uygulamanızı çağırır ve işlevsellik öğesinden devralınan `COleDispatchDriver` sırayla bunları sunucu nesnesine yönlendiren OLE sistem çağrıları yönlendirir.

Projeyi oluşturduğunuzda Otomasyon eklemeyi seçtiyseniz visual C++, sizin için otomatik olarak bu tür kitaplığı dosyası tutar. Her yapı işleminin bir parçası olarak, .tlb dosyasının MkTypLib ile oluşturulur.

### <a name="to-create-a-dispatch-class-from-a-type-library-tlb-file"></a>Bir tür kitaplığı (.tlb) dosyasından bir dağıtım sınıfı oluşturmak için

1. Sınıf Görünümü veya Çözüm Gezgini'nde, projeye sağ tıklayıp **Ekle** ve ardından **sınıfı Ekle** kısayol menüsünde.

1. İçinde **sınıfı Ekle** iletişim kutusunda **Visual c + +/ MFC** sol bölmedeki klasör. Seçin **gelen MFC sınıfı TypeLib** simgesine tıklayın ve sağ bölmede **açık**.

1. İçinde **Typelib sihirbazın sınıfı Ekle** iletişim kutusunda, bir tür kitaplığından seçin **kullanılabilir tür kitaplıklarını** aşağı açılan listesi. **Arabirimleri** seçilen tür kitaplığının kullanılabilir arabirimleri kutusu görüntüler.

    > [!NOTE]
    >  Birden fazla tür kitaplığından arabirimleri seçebilirsiniz.

   Arabirimleri seçin, bunları çift tıklatın veya **Ekle** düğmesi. Bunu yaptığınızda gönderme sınıflarının adları görünür **sınıfları oluşturulan** kutusu. Sınıf adları düzenleyebileceğiniz `Class` kutusu.

   **Dosya** kutusu içinde sınıf bildirilmesi dosyayı görüntüler. (Bu dosya adı da düzenleyebilirsiniz). Mevcut dosyaları ya da proje dizininin dışında bir dizinde yazılan üst bilgi ve uygulama bilgilerinin isterseniz diğer dosyalar seçmek için Gözat düğmesini de kullanabilirsiniz.

    > [!NOTE]
    >  Seçilen arabirimleri için gönderme sınıfların tümü, burada belirtilen dosyanın yerleştirilir. Ayrı üst bilgilerinde bildirilmesi için arabirimleri istiyorsanız, oluşturmak istediğiniz her bir üst bilgi dosyası için bu sihirbazı çalıştırmanız gerekir.

    > [!NOTE]
    >  Bazı tür kitaplığı bilgisi dosyalarıyla depolanabilir. DLL. OCX veya. OLB dosya uzantıları.

1. **Son**'a tıklayın.

   Sihirbazı'nı, ardından belirtilen sınıf ve dosya adlarını kullanarak, gönderme sınıflar için kod yazacaksınız.

## <a name="see-also"></a>Ayrıca bkz.

[Otomasyon İstemcileri](../mfc/automation-clients.md)
