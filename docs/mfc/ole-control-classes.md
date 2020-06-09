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
ms.openlocfilehash: 5aa3899dca5a42cf789dc6dfd4701547495ec618
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617759"
---
# <a name="ole-control-classes"></a>OLE Denetim Sınıfları

Bunlar OLE denetimleri yazarken kullandığınız birincil sınıflardır. `COleControlModule`OLE denetim modülündeki sınıf, bir uygulamadaki [CWinApp](reference/cwinapp-class.md) sınıfına benzer. Her modül bir veya daha fazla OLE denetimini uygular; Bu denetimler nesneler tarafından temsil edilir `COleControl` . Bu denetimler nesneleri kullanarak kapsayıcılarıyla iletişim kurar `CConnectionPoint` .

`CPictureHolder`Ve `CFontHolder` sınıfları, Resimler ve yazı TIPLERI için com arabirimlerini kapsüllarken, `COlePropertyPage` ve `CPropExchange` sınıfları, denetiminiz için özellik sayfaları ve özellik kalıcılığı uygulamanıza yardımcı olur.

[Cotacontrolmodule](reference/colecontrolmodule-class.md)<br/>
`CWinApp`OLE denetim modülünüzün sınıfını değiştirir. `COleControlModule`OLE denetim modülü nesnesi geliştirmek için sınıftan türetirsiniz. OLE denetiminizin modülünü başlatmak için üye işlevleri sağlar.

[COleControl](reference/colecontrol-class.md)<br/>
`COleControl`OLE denetimi geliştirmek için sınıfından türetebilirsiniz. Öğesinden türetildiyse `CWnd` , bu sınıf bir Windows pencere nesnesinin tüm işlevselliğini ve olay başlatma ve yöntem ve özellikleri destekleme özelliği gıbı OLE 'ye özgü diğer işlevleri devralır.

[CConnectionPoint](reference/cconnectionpoint-class.md)<br/>
`CConnectionPoint`Sınıfı, bağlantı noktası olarak adlandırılan DIĞER OLE nesneleriyle iletişim kurmak için kullanılan özel bir arabirim türünü tanımlar. Bir bağlantı noktası, olayları tetikme ve değişiklik bildirimleri gibi diğer nesneler üzerinde eylemleri başlatabilecek bir giden arabirimi uygular.

[Cpictureş](reference/cpictureholder-class.md)<br/>
Bir Windows resim nesnesinin ve `IPicture` com arabiriminin işlevselliğini Kapsüller; OLE denetiminin özel resim özelliğini uygulamak için kullanılır.

[Cfonthdaha eski](reference/cfontholder-class.md)<br/>
Bir Windows yazı tipi nesnesinin ve com arabiriminin işlevselliğini Kapsüller `IFont` ; BIR OLE denetiminin hisse senedi yazı tipi özelliğini uygulamak için kullanılır.

[COlePropertyPage](reference/colepropertypage-class.md)<br/>
Bir OLE denetiminin özelliklerini bir iletişim kutusuna benzer şekilde bir grafik arabirimde görüntüler.

[CPropExchange](reference/cpropexchange-class.md)<br/>
OLE Denetimleriniz için özellik kalıcılığının uygulanmasını destekler. İletişim kutuları için [CDataExchange](reference/cdataexchange-class.md) 'e benzer.

[CMonikerFile](reference/cmonikerfile-class.md)<br/>
Bir bilinen ad veya bir ad olarak bilinen bir dize temsili alır ve bunu, bilinen adın adı olduğu akışa zaman uyumlu bir şekilde bağlar.

[CAsyncMonikerFile](reference/casyncmonikerfile-class.md)<br/>
Benzer şekilde çalışır `CMonikerFile` ; ancak bilinen adı, bilinen adın adı olduğu akışa zaman uyumsuz olarak bağlar.

[CDataPathProperty](reference/cdatapathproperty-class.md)<br/>
Zaman uyumsuz olarak yüklenebilen bir OLE denetim özelliği uygular.

[CCachedDataPathProperty](reference/ccacheddatapathproperty-class.md)<br/>
Zaman uyumsuz olarak aktarılan ve bir bellek dosyasında önbelleğe alınmış bir OLE denetim özelliği uygular.

[COleCmdUI](reference/colecmdui-class.md)<br/>
Etkin bir belgenin kapsayıcının Kullanıcı arabiriminde (FileNew, Open, Print, vb.) kaynaklanan komutları almasına izin verir ve bir kapsayıcının etkin belgenin kullanıcı arabiriminden kaynaklanan komutları almasına izin verir.

[Colet SAFEARRAY](reference/colesafearray-class.md)<br/>
Rastgele tür ve boyut dizileri ile birlikte kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](class-library-overview.md)
