---
title: "ActiveX denetimleri oluşturmak için işlem dizisi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], creating
- ActiveX controls [MFC], creating
- sequence [MFC], for creating ActiveX controls
- OLE controls [MFC], MFC
- sequence [MFC]
ms.assetid: 7d868c53-a0af-4ef6-a89c-e1c03c583a53
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1e16254d7be929596d1205fa22cb5d62323d077d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="sequence-of-operations-for-creating-activex-controls"></a>ActiveX Denetimleri Oluşturmak için İşlem Dizisi
Aşağıdaki tabloda, ActiveX denetimleri (önceden OLE denetimleri biliniyordu) oluşturmada rolünüze ve framework'ün rol gösterir.  
  
### <a name="creating-activex-controls"></a>ActiveX denetimleri oluşturma  
  
|Görev|Bunu|Framework mu|  
|----------|------------|------------------------|  
|ActiveX denetimi framework oluşturun.|Denetim oluşturmak için MFC ActiveX Denetim Sihirbazı'nı çalıştırın. Seçenekler sayfalarında istediğiniz seçenekleri belirtin. Seçenekler, proje, lisans, sınıflara ve hakkında kutusunu yöntemi denetiminin adını ve türünü dahil.|MFC ActiveX Denetim Sihirbazı'nı dosyaları bir ActiveX denetimi için uygulamanızı, Denetim ve özellik sayfası veya sayfaları için kaynak dosyaları içeren temel işlevsellikten oluşturur; kaynak dosyası; bir proje dosyası; ve diğer tüm uyarlanmış, belirtimleri.|  
|Bkz. satır kendi kodunuzu eklemeden ne denetimi ve ActiveX Denetim Sihirbazı'nı sunar.|ActiveX denetimi oluşturmak ve Internet Explorer ile test veya [TSTCON örnek](../visual-cpp-samples.md).|Çalışan denetimi yeniden boyutlandırılabilir ve taşınmış özelliğine sahiptir. Ayrıca sahip bir **hakkında kutusunu** çağrılabilir (seçilirse) yöntemi.|  
|Denetimin yöntemleri ve özellikleri uygular.|Özel denetim yöntemleri ve özellikleri denetimin verileri için sunulan bir arabirim sağlamak için üye işlevleri ekleyerek uygulayın. Veri yapıları tutun ve siz karar verirken olayları tetiklenecek olay işleyicilerini kullanmak için üye değişkenleri ekleyin.|Çerçeve denetim olayları, özellikleri ve yöntemleri, nasıl özellikleri ve yöntemleri uygulanan üzerinde odaklanmanızı bırakarak desteklemek için bir harita zaten tanımlanmış. Varsayılan özellik sayfasında görüntülenebilir ve varsayılan bir hakkında kutusunu yöntemi sağlanır.|  
|Denetimin özellik sayfa veya sayfaları oluşturun.|Visual C++ kaynak düzenleyicileri görsel olarak denetimin özellik sayfası arabirimini düzenlemek için kullanın:<br /><br /> -Ek özellik sayfaları oluşturun.<br />-Oluşturun ve bit eşlemler, simgeler ve İmleçler düzenleyin.<br /><br /> Özellik sayfaları iletişim kutusu Düzenleyicisi'nde de test edebilirsiniz.|MFC Uygulama Sihirbazı tarafından oluşturulan varsayılan kaynak dosyası ihtiyacınız olan kaynakları çoğunu sağlar. Visual C++, var olan kaynakların düzenleyebilir ve kolayca ve görsel olarak yeni kaynakları ekleyebilirsiniz olanak tanır.|  
|Denetim olayları, yöntemleri ve özellikleri sınayın.|Denetim yeniden oluşturun ve Test kapsayıcısı, işleyicilerin doğru şekilde çalıştığını sınamak için kullanın.|Denetimin yöntemleri çağırma ve özelliklerini Test kapsayıcısı veya özellik sayfasında arabirimi aracılığıyla arabirimidir. Ayrıca, Test kapsayıcısı izleme denetimden tetiklenen olayları ve bildirimleri denetimin kapsayıcı tarafından alınan için kullanın.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Framework'te derleme](../mfc/building-on-the-framework.md)   
 [MFC uygulamaları oluşturmak için işlem dizisi](../mfc/sequence-of-operations-for-building-mfc-applications.md)   
 [OLE uygulamaları oluşturmak için işlem dizisi](../mfc/sequence-of-operations-for-creating-ole-applications.md)   
 [Veritabanı Uygulamaları Oluşturmak için İşlem Dizisi](../mfc/sequence-of-operations-for-creating-database-applications.md)

