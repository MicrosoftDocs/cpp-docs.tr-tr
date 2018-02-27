---
title: MFC COM | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MFC COM (MFC)
dev_langs:
- C++
helpviewer_keywords:
- MFC, COM support
- MFC ActiveX controls [MFC], COM support in MFC
- MFC COM [MFC]
- ActiveX controls [MFC], COM object model
- Active technology [MFC]
- COM [MFC], MFC support
ms.assetid: 7646bdcb-3a06-4ed5-9386-9b00f3979dcb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dd9035c7b80b36e8124c827c0b3d1b76c59deb52
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="mfc-com"></a>MFC COM
Çoğu Etkin Şablon kitaplığı (ATL) olarak tasarlanmıştır ancak bir alt kümesini MFC COM, desteklemek için tasarlanmıştır COM programlama için. MFC'nin COM desteği konu bu bölümde açıklanmaktadır  
  
 Etkin teknolojileri (örneğin, ActiveX denetimleri, etkin belge kapsaması, OLE ve benzeri) sahip oldukları dil bağımsız olarak bir ağ ortamında birbiriyle etkileşim kurmak yazılım bileşenleri etkinleştirmek için Bileşen Nesne Modeli (COM) kullanın. oluşturulur. Etkin teknoloji, masaüstü veya Internet üzerinde çalışan uygulamaları oluşturmak için kullanılabilir. Daha fazla bilgi için bkz: [COM giriş](../atl/introduction-to-com.md) veya [Bileşen Nesne modeli](http://msdn.microsoft.com/library/windows/desktop/ms694363).  
  
 Etkin teknoloji aşağıdakiler de dahil olmak üzere, istemci ve sunucu teknolojileri şunları içerir:  
  
-   [Etkin belge kapsaması](../mfc/active-document-containment.md), MFC sürümleri 4.2 desteklenen ve daha sonra kullanıcıların görüntülemesine izin verir [etkin belgeler](../mfc/active-documents.md) (Microsoft Excel veya Word'den dosyaları gibi) ve belgenin yerel tüm arabiriminin etkinleştirin tüm istemci alanını uygulaması bir [etkin belge kapsayıcısı](../mfc/active-document-containers.md) Microsoft Office Binder veya Microsoft Internet Explorer gibi. Tarafından sağlanan belgelerin sırada kapsayıcıları istemcileri hareket [etkin belge sunucuları](../mfc/active-document-servers.md). Etkin belgeler Internet uygulamalarında kullanma ile ilgili daha fazla bilgi için bkz: [Internet'te etkin belgeler](../mfc/active-documents-on-the-internet.md).  
  
-   ActiveX denetimleri, bir Web sitesi gibi kapsayıcıları kullanılabilir etkileşimli nesneleridir. ActiveX denetimleri hakkında daha fazla bilgi için bkz:  
  
    -   [MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)  
  
    -   [Internet'te ActiveX Denetimleri](../mfc/activex-controls-on-the-internet.md)  
  
    -   [Genel Bakış: Internet](../mfc/mfc-internet-programming-basics.md)  
  
    -   [Internet'te kullanılacak varolan bir ActiveX denetimini yükseltme](../mfc/upgrading-an-existing-activex-control.md)  
  
    -   [ActiveX denetimi hata ayıklama](/visualstudio/debugger/how-to-debug-an-activex-control)  
  
-   Etkin komut dosyası, bir tarayıcı veya sunucudan bir veya daha fazla ActiveX denetimlerini tümleşik davranışını denetler. Etkin komut dosyası oluşturma hakkında daha fazla bilgi için bkz: [Internet'te etkin teknoloji](../mfc/active-technology-on-the-internet.md).  
  
-   [Otomasyon](../mfc/automation.md) (önceki adıyla OLE Otomasyon bilinir), bir uygulama için başka bir uygulamaya uygulanan nesneleri değiştirmek için ya da "bunlar işlenebilir nesnelerini ortaya çıkarmak için" mümkün kılar.  
  
     Otomatik nesne yerel veya uzak (başka bir makine bir ağ üzerinden erişilebilir) olabilir. Otomasyon OLE ve COM nesneleri için kullanılabilir.  
  
-   Bu bölümde MFC, örneğin, kullanarak COM bileşenlerini yazma konusunda bilgi de sağlanır. [bağlantı noktaları](../mfc/connection-points.md).  
  
 Konulara bakın ne artık etkin teknoloji olarak adlandırılır ve ne OLE hala adlandırılır bir tartışma için [OLE](../mfc/ole-in-mfc.md).  
  
 Ayrıca, Bilgi Bankası makalesi Q248019 bkz: nasıl yapılır: önlemek sunucu meşgul iletişim kutusu görüntülenmesini sırasında bir uzun COM işlemin.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Etkin Belge Kapsaması](../mfc/active-document-containment.md)  
  
 [Otomatikleştirme](../mfc/automation.md)  
  
 [Bağlantı Noktaları](../mfc/connection-points.md)  
  
 [MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../mfc/mfc-concepts.md)

