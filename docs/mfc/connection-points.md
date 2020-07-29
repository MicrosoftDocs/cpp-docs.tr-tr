---
title: Bağlantı Noktaları
ms.date: 11/19/2018
f1_keywords:
- IConnectionPoint
helpviewer_keywords:
- IConnectionPoint interface
- connections, connection points
- OLE COM connection points
- MFC COM, connection points
- COM, connection points
- interfaces, IConnectionPoint
- MFC, COM support
- connection points [MFC]
- CCmdTarget class [MFC], and connection points
- sinks, connection points
ms.assetid: bc9fd7c7-8df6-4752-ac8c-0b177442c88d
ms.openlocfilehash: c14d8247be2abdf828b88e728bd930691ec6571f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214158"
---
# <a name="connection-points"></a>Bağlantı Noktaları

Bu makalede, MFC sınıflarını ve kullanarak bağlantı noktalarının (eski adı OLE bağlantı noktaları olarak bilinirdi) nasıl uygulanacağı açıklanmaktadır `CCmdTarget` `CConnectionPoint` .

Geçmişte, bileşen nesne modeli (COM), `IUnknown::QueryInterface` nesneleri uygulamak ve arabirimlerde işlevselliği göstermek için izin verilen bir genel mekanizma (*) tanımladı. Ancak, nesnelerin belirli arabirimleri çağırma yeteneklerini kullanıma sunmasına izin veren karşılık gelen bir mekanizma tanımlı değil. Diğer bir deyişle, COM, nesnelere gelen işaretçilerin (Bu nesne arayüzlerinin işaretçileri) nasıl işlendiği, ancak giden arabirimler için açık bir model (nesne diğer nesnelerin arabirimlerine ait olan işaretçiler) ile tanımlanır. COM artık bu işlevselliği destekleyen bağlantı noktaları olarak adlandırılan bir modele sahiptir.

Bir bağlantı iki bölümden oluşur: kaynak adı verilen arabirimi çağıran nesne ve havuz adı verilen arabirimi uygulayan nesne. Bağlantı noktası, kaynak tarafından kullanıma sunulan arabirimdir. Bir bağlantı noktasını ortaya çıkaran bir kaynak, havuza bağlantı kurmasını sağlar (kaynak). Bağlantı noktası mekanizması ( `IConnectionPoint` arabirim) aracılığıyla, havuz arabirimine yönelik bir işaretçi kaynak nesnesine geçirilir. Bu işaretçi, kaynağa, bir üye işlevleri kümesinin havuz uygulamasına erişim sağlar. Örneğin, havuz tarafından uygulanan bir olayı tetikleyerek, kaynak havuzun uygulamasının uygun yöntemini çağırabilir. Aşağıdaki şekilde, yalnızca açıklanan bağlantı noktası gösterilmektedir.

![Uygulanan bağlantı noktası](../mfc/media/vc37lh1.gif "Uygulanan bağlantı noktası") <br/>
Uygulanan bir bağlantı noktası

MFC bu modeli [CConnectionPoint](reference/cconnectionpoint-class.md) ve [CCmdTarget](reference/ccmdtarget-class.md) sınıflarında uygular. `CConnectionPoint` `IConnectionPoint` Diğer nesnelere bağlantı noktalarını göstermek için kullanılan, arabirimini uygulamadan türetilmiş sınıflar. `CCmdTarget` `IConnectionPointContainer` Bir nesnenin kullanılabilir bağlantı noktalarını listeleyebilen veya belirli bir bağlantı noktasını bulabileceğiniz arabirimi uygulama sınıfından türetilmiş sınıflar.

Sınıfınıza uygulanan her bağlantı noktası için, bağlantı noktasını uygulayan bir bağlantı parçası bildirmeniz gerekir. Bir veya daha fazla bağlantı noktası uygularsanız, sınıfınıza tek bir bağlantı eşlemesi de bildirmeniz gerekir. Bağlantı eşlemesi, ActiveX denetimi tarafından desteklenen bağlantı noktalarının bir tablosudur.

Aşağıdaki örneklerde basit bir bağlantı haritası ve bir bağlantı noktası gösterilmektedir. İlk örnek bağlantı eşlemesini ve noktasını bildirir; İkinci örnek, eşlemeyi ve noktasını uygular. ' In `CMyClass` türetilmiş bir sınıf olması gerektiğini unutmayın `CCmdTarget` . İlk örnekte, kod sınıf bildiriminde, bölüm altında eklenir **`protected`** :

[!code-cpp[NVC_MFCConnectionPoints#1](codesnippet/cpp/connection-points_1.h)]

**BEGIN_CONNECTION_PART** ve **END_CONNECTION_PART** makroları, `XSampleConnPt` `CConnectionPoint` Bu bağlantı noktasını uygulayan gömülü bir sınıf (öğesinden türetilir) bildirir. Herhangi bir üye işlevini geçersiz kılmak `CConnectionPoint` veya kendi üye işlevlerini eklemek istiyorsanız, bunları bu iki makro arasında bildirin. Örneğin, `CONNECTION_IID` makro `CConnectionPoint::GetIID` Bu iki makro arasında yerleştirildiğinde üye işlevini geçersiz kılar.

İkinci örnekte, kod denetimin uygulama dosyasına (. cpp dosyası) eklenir. Bu kod, bağlantı noktasını içeren bağlantı haritasını uygular `SampleConnPt` :

[!code-cpp[NVC_MFCConnectionPoints#2](codesnippet/cpp/connection-points_2.cpp)]

Sınıfınız birden fazla bağlantı noktasına sahipse, **BEGIN_CONNECTION_MAP** ve **END_CONNECTION_MAP** makroları arasında ek **CONNECTION_PART** makroları ekleyin.

Son olarak, sınıfının oluşturucusunda öğesine bir çağrı ekleyin `EnableConnections` . Örnek:

[!code-cpp[NVC_MFCConnectionPoints#3](codesnippet/cpp/connection-points_3.cpp)]

Bu kod eklendikten sonra, `CCmdTarget` türetilmiş sınıfınız arabirim için bir bağlantı noktası gösterir `ISampleSink` . Aşağıdaki şekilde bu örnek gösterilmektedir.

![MFC kullanılarak uygulanan bağlantı noktası](../mfc/media/vc37lh2.gif "MFC kullanılarak uygulanan bağlantı noktası") <br/>
MFC ile uygulanan bir bağlantı noktası

Genellikle bağlantı noktaları, "çok noktaya yayını" destekler. aynı arabirime bağlı birden çok havuza yayın yapabilme özelliği. Aşağıdaki örnek parça bir bağlantı noktasındaki her bir havuz üzerinden yineleme yaparak nasıl çok noktaya yayın yapılacağını göstermektedir:

[!code-cpp[NVC_MFCConnectionPoints#4](codesnippet/cpp/connection-points_4.cpp)]

Bu örnek, bağlantı noktasındaki geçerli bağlantı kümesini `SampleConnPt` öğesine çağrısı ile alır `CConnectionPoint::GetConnections` . Daha sonra `ISampleSink::SinkFunc` her etkin bağlantı üzerinde bağlantılar ve çağrılar üzerinden yinelenir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC COM](mfc-com.md)
