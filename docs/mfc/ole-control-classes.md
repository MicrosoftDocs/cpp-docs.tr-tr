---
title: OLE Denetim Sınıfları
ms.date: 11/04/2016
f1_keywords:
- vc.classes.ole
helpviewer_keywords:
- ActiveX classes [MFC]
- custom controls [MFC], classes
- ActiveX controls [MFC], OLE control classes
- ActiveX control classes [MFC]
- OLE controls [MFC], classes
- OLE control classes [MFC]
- reusable component classes [MFC]
ms.assetid: 96495ec3-319e-4163-b839-1af0428ed9dd
ms.openlocfilehash: 86470c3e3e66d6aee2ce532570cea096641d2c1d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304567"
---
# <a name="ole-control-classes"></a>OLE Denetim Sınıfları

Bunlar, OLE denetimleri yazarken kullanmak, birincil sınıflardır. `COleControlModule` Bir OLE denetim modülü sınıfında benzer [CWinApp](../mfc/reference/cwinapp-class.md) uygulama içindeki. Her modül bir veya daha fazla OLE denetimlerini uygular; Bu denetimler tarafından temsil edilen `COleControl` nesneleri. Bu denetimleri kullanarak kendi kapsayıcılarla iletişim `CConnectionPoint` nesneleri.

`CPictureHolder` Ve `CFontHolder` sınıfları, resimleri ve yazı tipleri için COM arabirimleri Kapsüller sırada `COlePropertyPage` ve `CPropExchange` sınıflar özellik sayfaları ve özellik Kalıcılık denetiminiz için uygulamanıza yardımcı olur.

[COleControlModule](../mfc/reference/colecontrolmodule-class.md)<br/>
Değiştirir `CWinApp` , bir OLE denetim modülü için sınıf. Öğesinden türetilen `COleControlModule` bir OLE denetim modülü nesnesi geliştirmek için sınıf. OLE denetim modülü başlatmak için bu üye işlevleri sağlar.

[COleControl](../mfc/reference/colecontrol-class.md)<br/>
Öğesinden türetilen `COleControl` bir OLE denetim geliştirmek için sınıf. Türetilmiş `CWnd`, bu sınıf Windows pencere nesnesi tüm işlevselliğinin yanı sıra olay tetikleyicisinin tetikleme ve yöntemleri ve özellikleri destekleme özelliği gibi ek OLE özel işlevler devralır.

[CConnectionPoint](../mfc/reference/cconnectionpoint-class.md)<br/>
`CConnectionPoint` Sınıf, arabirim bir bağlantı noktası olarak adlandırılan diğer OLE nesneleri ile iletişim kurmak için kullanılan özel bir tür tanımlar. Bir bağlantı noktası olayları tetikleme gibi diğer nesneler üzerinde eylem başlatmak ve değişiklik bildirimleri giden bir arabirim uygular.

[CPictureHolder](../mfc/reference/cpictureholder-class.md)<br/>
Bir Windows Resim nesnesi işlevselliğini kapsüller ve `IPicture` COM arabirimi; özel resim özelliği bir OLE denetimi gerçekleştirmek için kullanılır.

[CFontHolder](../mfc/reference/cfontholder-class.md)<br/>
Bir Windows yazı tipi nesnesinin işlevselliğini kapsüller ve `IFont` COM arabirimi; stok yazı tipi özellik bir OLE denetimi gerçekleştirmek için kullanılır.

[COlePropertyPage](../mfc/reference/colepropertypage-class.md)<br/>
İletişim kutusuna benzer bir grafik arabiriminde denetimi bir OLE özelliklerini görüntüler.

[CPropExchange](../mfc/reference/cpropexchange-class.md)<br/>
OLE denetimleriniz için özellik sürekliliğin uygulanmasını destekler. Alınmak üzere [CDataExchange](../mfc/reference/cdataexchange-class.md) iletişim kutuları için.

[CMonikerFile](../mfc/reference/cmonikerfile-class.md)<br/>
Bir bilinen ad veya bir bilinen adına yapabilen bir dize gösterimini alır ve takma ad olan akışa zaman uyumlu olarak bağlar.

[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)<br/>
Benzer şekilde çalışır `CMonikerFile`; ancak, takma ad olan akış için bilinen ad zaman uyumsuz olarak bağlar.

[CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)<br/>
Uygulayan bir OLE denetim zaman uyumsuz olarak yüklenebilen özelliği.

[CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md)<br/>
Uygulayan bir OLE denetim, zaman uyumsuz olarak aktarılabilen ve bir bellek dosyasında önbelleğe özelliği.

[Colecmduı](../mfc/reference/colecmdui-class.md)<br/>
Kapsayıcısının kullanıcı arabiriminde (örneğin, dosya yeni, açık, yazdırma ve benzeri) kaynaklanan komutları almak üzere bir etkin belgeyi sağlar ve etkin belgenin kullanıcı arabiriminde kaynaklanan komutları almak bir kapsayıcı sağlar.

[COleSafeArray](../mfc/reference/colesafearray-class.md)<br/>
Rastgele tür ve boyut dizileri ile çalışır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)
