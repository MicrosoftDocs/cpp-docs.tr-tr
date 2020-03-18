---
title: OLE Denetim Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX classes [MFC]
- custom controls [MFC], classes
- ActiveX controls [MFC], OLE control classes
- ActiveX control classes [MFC]
- OLE controls [MFC], classes
- OLE control classes [MFC]
- reusable component classes [MFC]
ms.assetid: 96495ec3-319e-4163-b839-1af0428ed9dd
ms.openlocfilehash: 47c28520d592c4bd49ab6cb40edbb2f5ddf59846
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447640"
---
# <a name="ole-control-classes"></a>OLE Denetim Sınıfları

Bunlar OLE denetimleri yazarken kullandığınız birincil sınıflardır. OLE denetim modülündeki `COleControlModule` sınıfı, bir uygulamadaki [CWinApp](../mfc/reference/cwinapp-class.md) sınıfına benzer. Her modül bir veya daha fazla OLE denetimini uygular; Bu denetimler `COleControl` nesneleri tarafından temsil edilir. Bu denetimler `CConnectionPoint` nesneleri kullanarak kapsayıcılarıyla iletişim kurar.

`CPictureHolder` ve `CFontHolder` sınıfları, Resimler ve yazı tipleri için COM arabirimlerini kapsüllarken, `COlePropertyPage` ve `CPropExchange` sınıfları denetiminiz için özellik sayfaları ve özellik kalıcılığı uygulamanıza yardımcı olur.

[Cotacontrolmodule](../mfc/reference/colecontrolmodule-class.md)<br/>
OLE denetim modülünüzün `CWinApp` sınıfını değiştirir. OLE denetim modülü nesnesi geliştirmek için `COleControlModule` sınıfından türetebilirsiniz. OLE denetiminizin modülünü başlatmak için üye işlevleri sağlar.

[COleControl](../mfc/reference/colecontrol-class.md)<br/>
OLE denetimi geliştirmek için `COleControl` sınıfından türetebilirsiniz. `CWnd`türetilir, bu sınıf bir Windows pencere nesnesinin tüm işlevselliğini ve olay başlatma ve yöntem ve özellikleri destekleme gibi diğer OLE 'ye özgü işlevleri devralır.

[CConnectionPoint](../mfc/reference/cconnectionpoint-class.md)<br/>
`CConnectionPoint` sınıfı, bağlantı noktası olarak adlandırılan diğer OLE nesneleriyle iletişim kurmak için kullanılan özel bir arabirim türünü tanımlar. Bir bağlantı noktası, olayları tetikme ve değişiklik bildirimleri gibi diğer nesneler üzerinde eylemleri başlatabilecek bir giden arabirimi uygular.

[Cpictureş](../mfc/reference/cpictureholder-class.md)<br/>
Bir Windows resim nesnesinin ve `IPicture` COM arabiriminin işlevselliğini Kapsüller; OLE denetiminin özel resim özelliğini uygulamak için kullanılır.

[Cfonthdaha eski](../mfc/reference/cfontholder-class.md)<br/>
Windows yazı tipi nesnesinin işlevlerini ve `IFont` COM arabirimini kapsar; bir OLE denetiminin hisse senedi yazı tipi özelliğini uygulamak için kullanılır.

[COlePropertyPage](../mfc/reference/colepropertypage-class.md)<br/>
Bir OLE denetiminin özelliklerini bir iletişim kutusuna benzer şekilde bir grafik arabirimde görüntüler.

[CPropExchange](../mfc/reference/cpropexchange-class.md)<br/>
OLE Denetimleriniz için özellik kalıcılığının uygulanmasını destekler. İletişim kutuları için [CDataExchange](../mfc/reference/cdataexchange-class.md) 'e benzer.

[CMonikerFile](../mfc/reference/cmonikerfile-class.md)<br/>
Bir bilinen ad veya bir ad olarak bilinen bir dize temsili alır ve bunu, bilinen adın adı olduğu akışa zaman uyumlu bir şekilde bağlar.

[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)<br/>
`CMonikerFile`benzer şekilde çalışır; Ancak, bilinen adı, bilinen adın bir ad olduğu akışa zaman uyumsuz olarak bağlar.

[CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)<br/>
Zaman uyumsuz olarak yüklenebilen bir OLE denetim özelliği uygular.

[CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md)<br/>
Zaman uyumsuz olarak aktarılan ve bir bellek dosyasında önbelleğe alınmış bir OLE denetim özelliği uygular.

[COleCmdUI](../mfc/reference/colecmdui-class.md)<br/>
Etkin bir belgenin kapsayıcının Kullanıcı arabiriminde (FileNew, Open, Print, vb.) kaynaklanan komutları almasına izin verir ve bir kapsayıcının etkin belgenin kullanıcı arabiriminden kaynaklanan komutları almasına izin verir.

[Colet SAFEARRAY](../mfc/reference/colesafearray-class.md)<br/>
Rastgele tür ve boyut dizileri ile birlikte kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../mfc/class-library-overview.md)
