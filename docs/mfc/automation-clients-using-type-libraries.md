---
title: 'Otomasyon Istemcileri: Tür kitaplıklarını kullanma'
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
ms.openlocfilehash: 480f8fca46b13d445f372311ed837475c71a1e9d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509225"
---
# <a name="automation-clients-using-type-libraries"></a>Otomasyon Istemcileri: Tür kitaplıklarını kullanma

İstemci sunucularının nesnelerini işlerinize yönelik olarak, Otomasyon istemcilerinin sunucu nesnelerinin özellikleri ve yöntemleriyle ilgili bilgileri olması gerekir. Özellikler veri türlerine sahiptir; yöntemler genellikle değerleri döndürür ve parametreleri kabul eder. İstemci, sunucu nesne türüne statik olarak bağlamak için bunların tümünün veri türleri hakkında bilgi gerektirir.

Bu tür bilgileri çeşitli yollarla tanınsunulabilir. Önerilen yol, bir tür kitaplığı oluşturmaktır.

[MkTypLib](/windows/win32/Midl/differences-between-midl-and-mktyplib)hakkında daha fazla bilgi için Windows SDK bakın.

Görsel C++ , bir tür kitaplığı dosyasını okuyabilir ve [cotadispatchsürücüden](../mfc/reference/coledispatchdriver-class.md)türetilmiş bir dağıtım sınıfı oluşturabilir. Bu sınıfın bir nesnesi, sunucu nesnesinin özelliklerini ve işlemlerini çoğaltma özelliklerine sahiptir. Uygulamanız bu nesnenin özelliklerini ve işlemlerini çağırır ve devralınan `COleDispatchDriver` işlevler bu çağrıları OLE sistemine yönlendirmiş ve bu da sunucu nesnesine yönlendirmelidir.

Proje C++ oluşturulduğunda Otomasyon dahil etmek istiyorsanız görsel bu tür kitaplığı dosyasını sizin için otomatik olarak korur. Her bir derleme kapsamında,. tlb dosyası MkTypLib ile oluşturulur.

### <a name="to-create-a-dispatch-class-from-a-type-library-tlb-file"></a>Bir tür kitaplığı (. tlb) dosyasından bir dağıtım sınıfı oluşturmak için

1. Sınıf Görünümü veya Çözüm Gezgini, projeye sağ tıklayın ve **Ekle** ' ye tıklayın ve ardından kısayol menüsünde **Sınıf Ekle** ' ye tıklayın.

1. **Sınıf Ekle** iletişim kutusunda sol bölmedeki  **C++Visual/MFC** klasörünü seçin. Sağ bölmedeki **TypeLib simgesinden MFC sınıfını** seçin ve **Aç**' a tıklayın.

1. **TypeLib 'Den sınıf ekleme Sihirbazı** iletişim kutusunda, **kullanılabilir tür kitaplıkları** açılan listesinden bir tür kitaplığı seçin. **Arabirimler** kutusu, seçilen tür kitaplığı için kullanılabilen arabirimleri görüntüler.

    > [!NOTE]
    >  Birden fazla tür kitaplığından arabirimler seçebilirsiniz.

   Arabirimleri seçmek için, çift tıklayın veya **Ekle** düğmesine tıklayın. Bunu yaptığınızda, dağıtım sınıflarının adları **oluşturulan sınıflar** kutusunda görünür. `Class` Kutudaki sınıf adlarını düzenleyebilirsiniz.

   **Dosya** kutusu, sınıfın bildirildiği dosyayı görüntüler. (Bu dosya adını da düzenleyebilirsiniz). Üstbilgi ve uygulama bilgilerinin varolan dosyalarda veya proje dizini dışında bir dizinde yazılmasını isterseniz, diğer dosyaları seçmek için de gözatın düğmesini de kullanabilirsiniz.

    > [!NOTE]
    >  Seçili arabirimlerin tüm dağıtım sınıfları burada belirtilen dosyaya yerleştirilecek. Arabirimlerin ayrı üstbilgilere bildirilmesini istiyorsanız, oluşturmak istediğiniz her üstbilgi dosyası için bu Sihirbazı çalıştırmanız gerekir.

    > [!NOTE]
    >  Bazı tür kitaplığı bilgileri ile dosyalarında depolanabilir. DLL,. OCX veya. OLB dosya uzantıları.

1.           **Son**'a tıklayın.

   Sihirbaz daha sonra, belirtilen sınıf ve dosya adlarını kullanarak dağıtım sınıflarınızın kodunu yazar.

## <a name="see-also"></a>Ayrıca bkz.

[Otomasyon İstemcileri](../mfc/automation-clients.md)
