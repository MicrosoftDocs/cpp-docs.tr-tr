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
ms.openlocfilehash: 6f934c4a5a24c5d54805a60e81cb0afdcdc2c14a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62153326"
---
# <a name="connection-points"></a>Bağlantı Noktaları

Bu makalede, (eski adıyla OLE bağlantı noktaları da bilinir) bağlantı noktalarının uygulanacağı açıklanmaktadır MFC sınıflarını kullanarak `CCmdTarget` ve `CConnectionPoint`.

Geçmişte, Bileşen Nesne Modeli (COM) genel bir mekanizma tanımlanan (`IUnknown::QueryInterface`*) uygulamak ve arabirimleri işlevselliği kullanıma sunma nesnelere izin verilir. Ancak, belirli arabirimleri çağırmak için kendi yeteneği kullanıma sunmak nesnelerine izin karşılık gelen bir mekanizma tanımlanmamış. Diğer bir deyişle, COM nesneleri için gelen işaretçileri tanımlı (Bu nesnenin arabirimlerinin işaretçileri) işlenir ancak giden arabirimleri (işaretçiler nesnesi diğer nesnelerin arabirimlerine tutar) için açık bir modeli yoktu. COM bağlantı noktaları olarak adlandırılır ve bu işlevi destekleyen bir model, artık sahiptir.

Bir bağlantı iki bölümden oluşur: kaynak ve arabirimi uygulayan nesnenin adlı arabirim, çağıran nesneyle havuz çağrılır. Bir bağlantı noktası kaynağı tarafından kullanıma sunulan arabirimidir. Bir bağlantı noktası göstererek kaynak havuzlarını kendisi (kaynak) bağlantıları kurmak sağlar. Mekanizması bağlantı noktası ( `IConnectionPoint` arabirimi), daha sonra havuz arabirimini işaretçisi kaynak nesneye geçirilir. Bu işaretçi, kaynak havuzu'nın uygulama üye işlevleri bir dizi erişim sağlar. Örneğin, havuz tarafından uygulanan bir olay harekete geçirmek için kaynak havuzu'nın uygulama uygun yöntemini çağırabilirsiniz. Aşağıdaki şekilde gösterilmiştir bağlantı noktası açıklanmış.

![Bağlantı noktası uygulanan](../mfc/media/vc37lh1.gif "uygulanan bağlantı noktası") <br/>
Uygulanan bir bağlantı noktası

MFC Bu modele uygulayan [CConnectionPoint](../mfc/reference/cconnectionpoint-class.md) ve [CCmdTarget](../mfc/reference/ccmdtarget-class.md) sınıfları. Türetilen sınıflar `CConnectionPoint` uygulamak `IConnectionPoint` arabirimi, diğer nesnelere bağlantı noktalarını göstermek için kullanılır. Türetilen sınıflar `CCmdTarget` uygulamak `IConnectionPointContainer` arabirimi nesnenin kullanılabilir bağlantı noktaları tüm numaralandırma veya özel bağlantı noktası bulunamıyor.

Sınıfınız içinde uygulanan her bağlantı noktası için bağlantı noktası uygulayan bir bağlantı bölümü bildirmeniz gerekir. Bir veya daha fazla bağlantı noktası uygularsanız, ayrıca tek bir bağlantı eşlemesi sınıfınızda bildirmeniz gerekir. Bir bağlantı eşlemesi, bağlantı noktalarının ActiveX denetimi tarafından desteklenen bir tablodur.

Aşağıdaki örnekler, bir basit bağlantı Haritası ve bir bağlantı noktası göstermektedir. İlk örnek noktası ve bağlantı eşlemesi bildirir; İkinci örnek, nokta ve eşleme uygular. Unutmayın `CMyClass` olmalıdır bir `CCmdTarget`-türetilmiş sınıf. İlk örnekte, kodu sınıf bildiriminde altında eklenir **korumalı** bölümü:

[!code-cpp[NVC_MFCConnectionPoints#1](../mfc/codesnippet/cpp/connection-points_1.h)]

**Begın_connectıon_part** ve **end_connectıon_part** makroları katıştırılmış bir sınıf bildirme `XSampleConnPt` (türetilen `CConnectionPoint`), uygular, bu belirli bağlantı noktası. Herhangi bir geçersiz kılmak istiyorsanız `CConnectionPoint` üye işlevleri veya üye işlevleri kendi ekleme, bunları bu iki makrolar arasında bildirin. Örneğin, `CONNECTION_IID` makrosu geçersiz kılmalar `CConnectionPoint::GetIID` iki Bu makrolar arasında yerleştirildiğinde üye işlevi.

İkinci örnekte, kodu denetimin uygulama dosyasında (.cpp dosyası) eklenir. Bu kod, bağlantı noktası içeren bağlantı eşlemesi uygulayan `SampleConnPt`:

[!code-cpp[NVC_MFCConnectionPoints#2](../mfc/codesnippet/cpp/connection-points_2.cpp)]

İşaret, ek Ekle birden fazla bağlantı sınıfınız varsa **connectıon_part** makroları arasında **begın_connectıon_map** ve **end_connectıon_map** makroları.

Son olarak, bir çağrı ekleyin `EnableConnections` sınıfın oluşturucusunda. Örneğin:

[!code-cpp[NVC_MFCConnectionPoints#3](../mfc/codesnippet/cpp/connection-points_3.cpp)]

Bu kodu ekledikten sonra `CCmdTarget`-türetilmiş sınıf için bir bağlantı noktası sunan `ISampleSink` arabirimi. Aşağıdaki şekil, bu örnek gösterir.

![MFC kullanılarak uygulanan bir bağlantı noktası](../mfc/media/vc37lh2.gif "MFC kullanılarak uygulanan bir bağlantı noktası") <br/>
MFC'de uygulanan bir bağlantı noktası

Genellikle "çok noktaya yayın" bağlantı noktaları desteği — birden çok havuzlarından yayın özelliği için aynı arabirimi bağlı. Aşağıdaki örnek parçası gösterilmiştir çok noktaya yayın bağlantı noktasındaki her bir havuz ile Yinelem tarafından nasıl:

[!code-cpp[NVC_MFCConnectionPoints#4](../mfc/codesnippet/cpp/connection-points_4.cpp)]

Bu örnek, üzerinde bağlantıları geçerli kümesini alır. `SampleConnPt` çağrısı ile bağlantı noktası `CConnectionPoint::GetConnections`. Ardından bağlantılar ve çağrılar aracılığıyla yinelenir `ISampleSink::SinkFunc` her etkin bağlantı.

## <a name="see-also"></a>Ayrıca bkz.

[MFC COM](../mfc/mfc-com.md)
