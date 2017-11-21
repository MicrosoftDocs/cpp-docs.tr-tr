---
title: "Bağlantı noktaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IConnectionPoint
dev_langs: C++
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
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a96c3ebe943e2ede844c554cf943555e2aa83fc6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="connection-points"></a>Bağlantı Noktaları
Bu makalede, bağlantı noktaları (önceki adıyla OLE bağlantı noktaları bilinir) uygulamak açıklanmaktadır MFC sınıfları kullanarak `CCmdTarget` ve `CConnectionPoint`.  
  
 Geçmişte, Bileşen Nesne Modeli (COM) genel bir mekanizma tanımlı (**IUnknown::QueryInterface**) uygulamak ve arabirimleri işlevselliği kullanıma sunmak nesneleri izin veriliyor. Ancak, belirli arabirimleri çağırmak için kendi yeteneği kullanıma sunmak nesnelerine izin karşılık gelen bir mekanizma tanımlanmadı. Diğer bir deyişle, COM nesnelerine nasıl gelen işaretçileri tanımlı (o nesne arabirimleri işaretçiler) işlendi, ancak giden arabirimleri (nesne tutan diğer nesneleri arabirimlerine işaretçileri) için açık bir model içermiyor. COM bağlantı noktaları olarak adlandırılır ve bu işlevselliğini destekleyen bir model, artık sahiptir.  
  
 Bir bağlantı iki bölümden oluşur: kaynak ve arabirimini uygulayan nesne adında arabirimi çağırma nesnesi havuz olarak adlandırılır. Bir bağlantı noktası, kaynak tarafından kullanıma sunulan arabirimidir. Bir bağlantı noktası göstererek bir kaynak havuzlarını kendisini (kaynak) bağlantı sağlar. Mekanizması bağlantı noktası ( **IConnectionPoint** arabirimi), havuz arayüzü için bir işaretçi kaynak nesneye iletilir. Bu işaretçinin üye işlevleri kümesinin bir havuz kullanıcının uygulamaya erişimi olan kaynak sağlar. Örneğin, havuzu tarafından uygulanan bir olay tetikleyin için kaynak havuzu 's uygulama uygun yöntemini çağırabilirsiniz. Aşağıdaki şekilde gösterilmektedir bağlantı noktası yalnızca açıklanan.  
  
 ![Bağlantı noktası uygulanan](../mfc/media/vc37lh1.gif "vc37lh1")  
Uygulanan bir bağlantı noktası  
  
 MFC uygulayan Bu modelde [CConnectionPoint](../mfc/reference/cconnectionpoint-class.md) ve [CCmdTarget](../mfc/reference/ccmdtarget-class.md) sınıfları. Türetilmiş sınıflar **CConnectionPoint** uygulamak **IConnectionPoint** diğer nesnelere bağlantı noktalarını göstermek için kullanılan arabirim. Türetilmiş sınıflar `CCmdTarget` uygulamak **IConnectionPointContainer** nesnenin kullanılabilir bağlantı noktaları tümünün listeleme veya özel bağlantı noktasını Bul arabirimi.  
  
 Sınıfınızda uygulanan her bağlantı noktası için bağlantı noktası uygulayan bir bağlantı bölümü bildirilmelidir. Bir veya daha fazla bağlantı noktaları uygularsanız, ayrıca bir tek bağlantı harita sınıfınızda bildirmeniz gerekir. Bir bağlantı eşleme bağlantı noktaları ActiveX denetimi tarafından desteklenen bir tablosu verilmiştir.  
  
 Aşağıdaki örnekler, bir basit bağlantı harita ve bir bağlantı noktası gösterir. İlk örnek noktası ve bağlantı harita bildirir; İkinci örnek harita ve noktası uygular. Unutmayın `CMyClass` olmalıdır bir `CCmdTarget`-türetilmiş sınıf. İlk örnekte kodu sınıfı bildiriminde altında eklenir **korumalı** bölümü:  
  
 [!code-cpp[NVC_MFCConnectionPoints#1](../mfc/codesnippet/cpp/connection-points_1.h)]  
  
 `BEGIN_CONNECTION_PART` Ve **end_connectıon_part** makroları katıştırılmış bir sınıf bildirme `XSampleConnPt` (türetilmiş `CConnectionPoint`), Implements bu belirli bağlantı noktası. Herhangi bir geçersiz kılmak istiyorsanız `CConnectionPoint` üye işlevleri veya kendi üye işlevleri eklemek için bu iki makrolar arasında bildirin. Örneğin, `CONNECTION_IID` makrosu geçersiz kılmaları `CConnectionPoint::GetIID` bu iki makrolar arasında yerleştirildiğinde üye işlevi.  
  
 İkinci örnekte kodu denetimin uygulama dosyası (.cpp dosyası) eklenir. Bu kod bağlantı noktası'nı içeren bağlantı harita uygulayan `SampleConnPt`:  
  
 [!code-cpp[NVC_MFCConnectionPoints#2](../mfc/codesnippet/cpp/connection-points_2.cpp)]  
  
 Sınıfınızda birden fazla bağlantı noktası, ek Ekle olup olmadığını `CONNECTION_PART` makrolar arasında `BEGIN_CONNECTION_MAP` ve `END_CONNECTION_MAP` makroları.  
  
 Son olarak, bir çağrı ekleyin `EnableConnections` sınıfının oluşturucusunda. Örneğin:  
  
 [!code-cpp[NVC_MFCConnectionPoints#3](../mfc/codesnippet/cpp/connection-points_3.cpp)]  
  
 Bu kod eklendikten sonra `CCmdTarget`-türetilmiş bir sınıf için bir bağlantı noktası sunan **ISampleSink** arabirimi. Aşağıdaki şekilde, bu örnek gösterilmektedir.  
  
 ![MFC kullanılarak uygulanan bağlantı noktası](../mfc/media/vc37lh2.gif "vc37lh2")  
MFC ile uygulanan bir bağlantı noktası  
  
 Genellikle, bağlantı noktaları "çok noktaya yayın" desteği — birden çok havuzlarını yayın özelliği aynı arabirime bağlı. Aşağıdaki örnek parça gösteren bir bağlantı noktası üzerinde her havuz üzerinden yineleme tarafından çok noktaya yayın nasıl:  
  
 [!code-cpp[NVC_MFCConnectionPoints#4](../mfc/codesnippet/cpp/connection-points_4.cpp)]  
  
 Bu örnek, üzerinde bağlantıları geçerli kümesini alır. `SampleConnPt` çağrısıyla bağlantı noktası `CConnectionPoint::GetConnections`. Ardından çağrıları ve bağlantıları tekrarlanan **ISampleSink::SinkFunc** her etkin bir bağlantı üzerinde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC COM](../mfc/mfc-com.md)

