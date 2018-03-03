---
title: "Otomasyon istemcileri: Tür kitaplıklarını kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MkTypLib
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b63f6d05415b163e523589756ba2eb67ab2c61a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="automation-clients-using-type-libraries"></a>Otomasyon İstemcileri: Tür Kitaplıklarını Kullanma
Otomasyon istemcileri istemcileridir sunucuları nesneleri yönetmek için sunucu nesneleri özellikleri ve yöntemleri hakkında bilgi olması gerekir. Özellikler veri türlerine sahip; yöntemleri genellikle dönüş değerleri ve parametreleri kabul eder. İstemci, sunucu nesnesi türü için statik olarak bağlamak için tüm bunların veri türleri hakkında bilgi gerektirir.  
  
 Bu tür bilgiler çeşitli yollarla bilinen yapılabilir. Tür kitaplığı oluşturmak için önerilen yoldur bakın.  
  
 Hakkında bilgi için [MkTypLib](http://msdn.microsoft.com/library/windows/desktop/aa366797), Windows SDK konusuna bakın.  
  
 Visual C++ bir tür kitaplığı dosyasını okumak ve türetilen gönderme sınıf oluşturma [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md). Bu sınıfın bir nesnesi özelliklerini ve bu sunucu nesnesinin çoğaltma işlemlerini sahiptir. Bu nesnenin özelliklerini ve işlemlerini uygulamanızı çağırır ve işlevsellik devralınan `COleDispatchDriver` bu sırayla bunları sunucu nesnesine yönlendiren OLE sistem çağrıları yönlendirir.  
  
 Proje oluşturduğunuzda Otomasyon içerecek şekilde seçtiyseniz visual C++, sizin için otomatik olarak bu tür kitaplığı dosyası sağlar. Her yapı bir parçası olarak .tlb dosyası ile MkTypLib oluşturulacak.  
  
### <a name="to-create-a-dispatch-class-from-a-type-library-tlb-file"></a>Tür kitaplığı (.tlb) dosyasından dispatch sınıfı oluşturmak için  
  
1.  Sınıf Görünümü veya Çözüm Gezgini'nde, projeye sağ tıklayın ve **Ekle** ve ardından **sınıfı Ekle** kısayol menüsünde.  
  
2.  İçinde **sınıfı Ekle** iletişim kutusunda **Visual c + +/ MFC** sol bölmede klasör. Seçin **gelen MFC sınıfı TypeLib** simgesine tıklayın ve sağ bölmede **açık**.  
  
3.  İçinde **Typelib sihirbazın sınıfı ekleme** iletişim kutusunda, bir tür kitaplığından seçin **kullanılabilir tür kitaplıklarının** aşağı açılan liste. **Arabirimleri** kutusu seçili tür kitaplığı için kullanılabilir arabirimleri görüntüler.  
  
    > [!NOTE]
    >  Birden fazla tür kitaplığından arabirimleri seçebilirsiniz.  
  
     Arabirimleri seçin, bunları çift tıklatın veya **Ekle** düğmesi. Bunu yaptığınızda, adları gönderme sınıfları için görünür **sınıflar** kutusu. Sınıf adları düzenleyebilirsiniz `Class` kutusu.  
  
     **Dosya** kutusu içinde sınıf bildirilebilir dosya görüntüler. (Bu dosya adı da düzenleyebilirsiniz). Var olan dosyaların veya proje dizininin dışında bir dizinde yazılmış üstbilgi ve uygulama bilgilerinin tercih ederseniz, diğer dosyaları seçmek için Gözat düğmesini de kullanabilirsiniz.  
  
    > [!NOTE]
    >  Seçili arabirimleri için tüm gönderme sınıfları burada belirtilen dosyaya sokar. Ayrı üstbilgilerinde belirtilecek arabirimler istiyorsanız, oluşturmak istediğiniz her üstbilgi dosyası için bu sihirbazı çalıştırmanız gerekir.  
  
    > [!NOTE]
    >  Bazı tür kitaplığı bilgileri dosyalarıyla depolanabilir. DLL. OCX veya. OLB dosya uzantıları.  
  
4.  **Son**'a tıklayın.  
  
     Sihirbaz sonra belirtilen sınıf ve dosya adlarını kullanarak, gönderme sınıfları için kod yazacaksınız.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Otomasyon İstemcileri](../mfc/automation-clients.md)

