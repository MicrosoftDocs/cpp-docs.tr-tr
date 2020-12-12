---
description: 'Daha fazla bilgi edinin: ActiveX denetimleri oluşturmak için Işlem dizisi'
title: ActiveX Denetimleri Oluşturmak için İşlem Dizisi
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], creating
- ActiveX controls [MFC], creating
- sequence [MFC], for creating ActiveX controls
- OLE controls [MFC], MFC
- sequence [MFC]
ms.assetid: 7d868c53-a0af-4ef6-a89c-e1c03c583a53
ms.openlocfilehash: 15b81716f5feee4dfd4d0ebf47ee4d0d648c4536
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217634"
---
# <a name="sequence-of-operations-for-creating-activex-controls"></a>ActiveX Denetimleri Oluşturmak için İşlem Dizisi

Aşağıdaki tabloda, rol ve Framework 'ün ActiveX denetimleri oluşturma (eski adıyla OLE denetimleri) rolü gösterilmektedir.

### <a name="creating-activex-controls"></a>ActiveX denetimleri oluşturma

|Görev|Bunu yaptığınızda|Çerçeve|
|----------|------------|------------------------|
|Bir ActiveX denetim çerçevesi oluşturun.|Denetiminizi oluşturmak için MFC ActiveX denetimi Sihirbazı 'Nı çalıştırın. Seçenekler sayfalarında istediğiniz seçenekleri belirtin. Seçenekler, projenin, lisansın, altsınıflama ve bir about Box yönteminde denetimin türünü ve adını içerir.|MFC ActiveX denetimi Sihirbazı, uygulama, denetim ve özellik sayfası veya sayfalarınızın kaynak dosyaları da dahil olmak üzere temel işlevlerle ActiveX denetimi için dosyalar oluşturur; kaynak dosyası; Proje dosyası; diğer bir deyişle, tümüne uyarlanmış özellikler.|
|Kendi kodunuzun bir satırını eklemeden denetimin ve ActiveX denetimi sihirbazının ne sunabileceği konusuna bakın.|ActiveX denetimini derleyin ve Internet Explorer veya [tstcon örneği](../overview/visual-cpp-samples.md)ile test edin.|Çalışan denetimin yeniden boyutlandırılması ve taşınması imkanına sahiptir. Ayrıca çağrılabilecek bir **About Box** yöntemi (seçildiyse) vardır.|
|Denetimin yöntemlerini ve özelliklerini uygulayın.|Denetim verilerine sunulan bir arabirim sağlamak için üye işlevleri ekleyerek denetime özgü yöntemlerinizi ve özellikleri uygulayın. Veri yapılarını tutmak için üye değişkenleri ekleyin ve olay işleyicilerini kullanarak olayları tetiklerinizi yapın.|Framework, denetimin olaylarını, özelliklerini ve yöntemlerini desteklemek için bir eşleme tanımladı ve bu, özelliklerin ve yöntemlerin nasıl uygulandığı üzerine odaklanmanızı sağlar. Varsayılan özellik sayfası görüntülenebilir ve bir varsayılan hakkında Box yöntemi sağlanır.|
|Denetimin özellik sayfasını veya sayfalarını oluşturun.|Denetimin özellik sayfası arabirimini görsel olarak düzenlemek için Visual C++ kaynak düzenleyicilerini kullanın:<br /><br />-Ek özellik sayfaları oluşturun.<br />-Bit eşlemler, simgeler ve imleçler oluşturun ve düzenleyin.<br /><br /> Ayrıca, iletişim kutusu düzenleyicisinde Özellik sayfaları da test edebilirsiniz.|MFC Uygulama Sihirbazı tarafından oluşturulan varsayılan kaynak dosyası, ihtiyacınız olan kaynakların çoğunu sağlar. Visual C++, mevcut kaynakları düzenlemenize ve kolayca ve görsel olarak yeni kaynaklar eklemenize olanak tanır.|
|Denetimin olaylarını, yöntemlerini ve özelliklerini test edin.|Denetimi yeniden oluşturun ve İşleyicileriniz doğru şekilde çalışmadığını test etmek için test kapsayıcısını kullanın.|Özellik sayfası arabirimi veya test kapsayıcısı aracılığıyla denetimin yöntemlerini çağırabilir ve özelliklerini düzenleyebilirsiniz. Ayrıca, denetimin kapsayıcısı tarafından alınan denetimden ve bildirimlerden tetiklenen olayları izlemek için test kapsayıcısını kullanın.|

## <a name="see-also"></a>Ayrıca bkz.

[Çerçevede derleme](../mfc/building-on-the-framework.md)<br/>
[MFC uygulamaları oluşturmak için Işlem dizisi](../mfc/sequence-of-operations-for-building-mfc-applications.md)<br/>
[OLE uygulamaları oluşturmak için Işlem dizisi](../mfc/sequence-of-operations-for-creating-ole-applications.md)<br/>
[Veritabanı uygulamaları oluşturmak için Işlem dizisi](../mfc/sequence-of-operations-for-creating-database-applications.md)
