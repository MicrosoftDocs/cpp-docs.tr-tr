---
title: OLE denetim sınıfları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.ole
dev_langs:
- C++
helpviewer_keywords:
- ActiveX classes [MFC]
- custom controls [MFC], classes
- ActiveX controls [MFC], OLE control classes
- ActiveX control classes [MFC]
- OLE controls [MFC], classes
- OLE control classes [MFC]
- reusable component classes [MFC]
ms.assetid: 96495ec3-319e-4163-b839-1af0428ed9dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5dcbda85c33bab37babe5da861067d25cf31e32c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="ole-control-classes"></a>OLE Denetim Sınıfları
Bunlar, OLE denetimleri yazarken kullanmak, birincil sınıflarıdır. `COleControlModule` OLE denetim modülü sınıfında benzer [CWinApp](../mfc/reference/cwinapp-class.md) bir uygulamada sınıfı. Her modül bir veya daha fazla OLE denetimleri uygular; Bu denetimler tarafından temsil edilen `COleControl` nesneleri. Bu denetimleri kullanarak kapsayıcılarına ile iletişim `CConnectionPoint` nesneleri.  
  
 `CPictureHolder` Ve `CFontHolder` sınıfların resimler ve yazı tipleri için COM arabirimleri kapsülleyen sırada `COlePropertyPage` ve `CPropExchange` sınıfları özellik sayfaları ve denetim özelliği kalıcılığını uygulamanıza yardımcı olur.  
  
 [COleControlModule](../mfc/reference/colecontrolmodule-class.md)  
 Değiştirir `CWinApp` OLE denetim modülü için sınıf. Öğesinden türetilen `COleControlModule` OLE denetim modülü nesnesi geliştirmek için sınıf. Üye işlevleri OLE denetiminizin modülü başlatılırken sağlar.  
  
 [COleControl](../mfc/reference/colecontrol-class.md)  
 Öğesinden türetilen `COleControl` OLE denetimi geliştirmek için sınıf. Türetilmiş `CWnd`, bu sınıf Windows pencere nesnesi tüm işlevselliğini artı olay tetikleme ve yöntemleri ve özellikleri destekleme özelliği gibi ek OLE özgü işlevsellik devralır.  
  
 [CConnectionPoint](../mfc/reference/cconnectionpoint-class.md)  
 `CConnectionPoint` Sınıfı bir özel tür bir bağlantı noktası olarak adlandırılan diğer OLE nesneleri ile iletişim kurmak için kullanılan arabirim tanımlar. Bir bağlantı noktası Eylemler olaylarını tetikleme gibi diğer nesneler üzerinde başlatmak ve bildirimleri değiştirin yapabiliyor bir giden arabirimini uygular.  
  
 [CPictureHolder](../mfc/reference/cpictureholder-class.md)  
 Windows Resim nesnesi işlevselliği kapsar ve `IPicture` COM arabirimi; OLE denetimi özel resim özelliği uygulamak için kullanılır.  
  
 [CFontHolder](../mfc/reference/cfontholder-class.md)  
 Bir Windows yazı tipi nesnesi işlevselliği kapsar ve `IFont` COM arabirimi; stok Font özelliği bir OLE denetimi gerçekleştirmek için kullanılır.  
  
 [COlePropertyPage](../mfc/reference/colepropertypage-class.md)  
 Bir iletişim kutusu için benzer bir grafik arabiriminde denetimi bir OLE özelliklerini görüntüler.  
  
 [CPropExchange](../mfc/reference/cpropexchange-class.md)  
 OLE denetimleri için özellik Kalıcılık uyarlamasını destekler. Benzer [CDataExchange](../mfc/reference/cdataexchange-class.md) iletişim kutuları için.  
  
 [CMonikerFile](../mfc/reference/cmonikerfile-class.md)  
 Bir ad veya takma yapabilen bir dize gösterimi alır ve özniteliğinde bir ad olduğu akışa zaman uyumlu olarak bağlar.  
  
 [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)  
 Benzer şekilde çalışır `CMonikerFile`; ancak, akışa özniteliğinde bir ad olduğu bilinen ad zaman uyumsuz olarak bağlar.  
  
 [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)  
 Implements bir OLE zaman uyumsuz olarak yüklenen özelliğini denetler.  
  
 [CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md)  
 Implements bir OLE zaman uyumsuz olarak aktarılır ve bellek dosyasında önbelleğe özelliğini denetler.  
  
 [COleCmdUI](../mfc/reference/colecmdui-class.md)  
 Kapsayıcısının kullanıcı arabiriminde (örneğin, dosya yeni, Aç, yazdırma vb.) kaynaklanan komutları almak için etkin bir belge sağlar ve etkin belgenin kullanıcı arabiriminde kaynaklanan komutları almak için bir kapsayıcı sağlar.  
  
 [COleSafeArray](../mfc/reference/colesafearray-class.md)  
 Diziler rasgele tür ve boyut çalışır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../mfc/class-library-overview.md)

