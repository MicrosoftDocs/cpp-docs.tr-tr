---
title: 'Kapsayıcılar: bir kapsayıcı uygulama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- applications [OLE], OLE container
- OLE containers [MFC], implementing
ms.assetid: af1e2079-619a-4eac-9327-985ad875823a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d3693cb7d52a048045f4745b69b45cacc4defc75
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="containers-implementing-a-container"></a>Kapsayıcılar: Bir Kapsayıcı Uygulama
Bu makalede, bir kapsayıcı uygulama yordamı özetler ve açıklamalarının kapsayıcıları uygulama hakkında ayrıntılı sağlayan diğer makalelere işaret eder. Ayrıca, uygulamak istediğiniz isteğe bağlı bazı OLE özellikleri ve bu özellikler açıklayan makaleleri listeler.  
  
#### <a name="to-prepare-your-cwinapp-derived-class"></a>CWinApp türetilmiş sınıf hazırlamak için  
  
1.  OLE kitaplıklarının çağırarak başlatma **Afxoleınit** içinde `InitInstance` üye işlevi.  
  
2.  Çağrı `CDocTemplate::SetContainerInfo` içinde `InitInstance` menü ve Hızlandırıcı atamak için yerinde katıştırılmış öğeyi olduğunda kullanılan kaynaklar etkinleştirildi. Bu konu hakkında daha fazla bilgi için bkz: [etkinleştirme](../mfc/activation-cpp.md).  
  
 Bir kapsayıcı uygulaması oluşturmak için MFC Uygulama Sihirbazı'nı kullandığınızda, bu özellikleri sizin için otomatik olarak sağlanır. Bkz: [bir MFC EXE Program oluşturma](../mfc/reference/mfc-application-wizard.md).  
  
#### <a name="to-prepare-your-view-class"></a>View sınıfı hazırlamak için  
  
1.  Seçilen öğeleri bir işaretçi tutarak izlemek ya da liste, seçili öğeler için birden çok seçim destekliyorsa işaretçileri. `OnDraw` İşlevi tüm OLE öğeleri çizin gerekir.  
  
2.  Geçersiz kılma `IsSelected` kendisine geçirilen öğe şu anda seçili olup olmadığını denetlemek için.  
  
3.  Uygulama bir **OnInsertObject** görüntülenecek ileti işleyicisi **Nesne Ekle** iletişim kutusu.  
  
4.  Uygulama bir `OnSetFocus` odak görünümünden bir yerinde etkin OLE aktarmak için işleyici katıştırılmış öğesi ileti.  
  
5.  Uygulama bir `OnSize` içeren görünümünün boyutundaki değişikliği yansıtacak şekilde kendi dikdörtgeni değiştirmek için ihtiyaç duyduğu bir OLE bildirmek için ileti işleyicisi öğesi katıştırılmış.  
  
 Bu özellikler uyarlamasını önemli ölçüde sonraki bir uygulamadan değiştiğinden, Uygulama Sihirbazı'nı temel bir uygulama sağlar. Büyük olasılıkla düzgün çalışması için uygulamanızın almak için bu işlevler özelleştirme gerekecektir. Bu örneği için bkz: [KAPSAYICI](../visual-cpp-samples.md) örnek.  
  
#### <a name="to-handle-embedded-and-linked-items"></a>Katıştırılmış ve bağlantılı öğeler işlemek için  
  
1.  Öğesinden bir sınıf türetin [COleClientItem](../mfc/reference/coleclientitem-class.md). Bu sınıfın nesnelerini katıştırılmış veya OLE belgenize bağlantılı bir öğeyi temsil eder.  
  
2.  Geçersiz kılma **değiştiğinde**, `OnChangeItemPosition`, ve `OnGetItemPosition`. Bu işlevler boyutlandırma, konumlandırma ve katıştırılmış ve bağlantılı öğeler değiştirme işleyin.  
  
 Uygulama Sihirbazı'nı sizin için sınıf elde ancak büyük olasılıkla geçersiz kılma gerekecek **değiştiğinde** ve diğer işlevleri önceki yordamda 2. adımda ile listelenir. Bu işlevler farklı bir uygulamadan diğerine uygulanır için iskelet uygulamaları çoğu uygulama için özelleştirilmiş gerekiyor. Bu örnekler için MFC bkz [DRAWCLI](../visual-cpp-samples.md) ve [KAPSAYICI](../visual-cpp-samples.md).  
  
 OLE desteği için kapsayıcı uygulamanın menü yapısının bir öğe sayısı eklemeniz gerekir. Bunlar hakkında daha fazla bilgi için bkz: [menüler ve kaynaklar: kapsayıcı ekleme](../mfc/menus-and-resources-container-additions.md).  
  
 Aşağıdaki özelliklerden bazıları kapsayıcı uygulamanızda desteklemeyi isteyebilirsiniz:  
  
-   Katıştırılmış öğeyi düzenlerken yerinde etkinleştirme.  
  
     Daha fazla bilgi için bkz: [etkinleştirme](../mfc/activation-cpp.md).  
  
-   Bir sunucu uygulamasından bir seçim bırakarak oluşturma OLE öğeleri.  
  
     Daha fazla bilgi için bkz: [sürükleme ve bırakma (OLE)](../mfc/drag-and-drop-ole.md).  
  
-   Katıştırılmış nesneler ya da birleşimi kapsayıcı/sunucu uygulamaları bağlantılar.  
  
     Daha fazla bilgi için bkz: [kapsayıcılar: Gelişmiş Özellikler](../mfc/containers-advanced-features.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kapsayıcıları](../mfc/containers.md)   
 [Kapsayıcılar: İstemci Öğeleri](../mfc/containers-client-items.md)

