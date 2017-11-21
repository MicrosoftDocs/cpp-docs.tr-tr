---
title: "Bileşik belge desteği, MFC Uygulama Sihirbazı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.mfc.exe.compdoc
dev_langs: C++
ms.assetid: 42e1af83-12c4-438d-92eb-13835afdb148
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 952f27b0c6717d23395453e5159e125370a76804
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compound-document-support-mfc-application-wizard"></a>Birleşik Belge Desteği, MFC Uygulama Sihirbazı
MFC Uygulama Sihirbazı'nı bu sayfada seviyesi için uygulamanızın bileşik ve etkin belge desteği sağlar. gösterir. Uygulamanızı bileşik belgeleri ve belge şablonları desteklemek için belge/görünüm mimarisinin desteklemesi gerekir.  
  
 Varsayılan olarak, uygulama hiçbir birleşik belge desteği içerir. Bu varsayılanı kabul ederseniz, uygulamanızın etkin belgeler veya bileşik dosyalar desteklemez.  
  
 **Bileşik belge desteği**  
 Uygulamanızı kapsayıcı desteği, sunucu desteği veya her ikisini sağlayıp sağlamadığını belirler. Bu alan hakkında daha fazla bilgi için bkz:  
  
-   [Kapsayıcılar: bir kapsayıcı uygulama](../../mfc/containers-implementing-a-container.md)  
  
-   [Sunucular: sunucu uygulama](../../mfc/servers-implementing-a-server.md)  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Yok**|Nesne Bağlama ve Katıştırma (OLE) desteği gösterir. Varsayılan olarak, Uygulama Sihirbazı'nı ActiveX desteği olmayan bir uygulama oluşturur.|  
|**Kapsayıcı**|Bağlantılı ve katıştırılmış nesneler içeriyor.|  
|**Mini sunucu**|Uygulama oluşturabileceğiniz ve yönetebileceğiniz bileşik belge nesneleri gösterir. Mini sunucuları çalıştıramazsınız Not tek başına ve yalnızca katıştırılmış öğeleri destekler.|  
|**Tam sunucu**|Uygulama oluşturabileceğiniz ve yönetebileceğiniz bileşik belge nesneleri gösterir. Tüm sunucuları tek başına ve hem bağlantılı hem öğeleri katıştırılmış destek çalıştırabilir.|  
|**Kapsayıcı/tam sunucu**|Uygulama bir kapsayıcı ve sunucu uygulanıp uygulanamayacağını gösterir. Bir kapsayıcı kendi belgelerine katıştırılmış veya bağlı öğeleri içeren bir uygulamadır. Bir sunucu kapsayıcı uygulamaları tarafından kullanım için Otomasyon öğeleri oluşturan bir uygulamadır.|  
  
 **Ek Seçenekler**  
 Uygulamanızı etkin belgeler destekleyip desteklemediğini belirtir. Bkz: [etkin belgeler](../../mfc/active-documents.md) bu özellik hakkında daha fazla bilgi için.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Etkin belge sunucusu**|Uygulama oluşturma ve etkin belgeleri yönetmek gösterir. Bu seçeneği belirlerseniz, etkin belgeyi sunucunuz için bir dosya uzantısı belirtmelisiniz **dosya uzantısı** kutusunda [belge şablonu dizeleri](../../mfc/reference/document-template-strings-mfc-application-wizard.md) Sihirbazı sayfası. Bkz: [etkin belge sunucuları](../../mfc/active-document-servers.md) daha fazla bilgi için.|  
|**Etkin belge kapsayıcısı**|Uygulamanın kendi çerçevesinde etkin belgeler içerebilir gösterir. Etkin belgeler, örneğin, Internet Explorer belgeleri ya da Microsoft Word dosyaları veya Excel elektronik tablolar gibi Office belgeleri içerebilir. Bkz: [etkin belge kapsaması](../../mfc/active-document-containment.md) daha fazla bilgi için.|  
|**Bileşik dosyalar için destek**|Bileşik dosya biçimini kullanarak kapsayıcı uygulamanın belgeleri seri değildir. Bu seçenek belleğe nesnelerini içeren tüm bir dosyayı yüklenmesini zorlar. Tek tek nesnelerin artımlı kaydeder kullanılabilir değil. Bir nesne değişti ve daha sonra kaydedilmiş dosyasındaki tüm nesneler kaydedilir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)

