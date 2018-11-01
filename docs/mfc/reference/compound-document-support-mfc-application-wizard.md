---
title: Birleşik Belge Desteği, MFC Uygulama Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.compdoc
ms.assetid: 42e1af83-12c4-438d-92eb-13835afdb148
ms.openlocfilehash: 572bb10d8aa2af38858bac50f795fb660d5476b1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543045"
---
# <a name="compound-document-support-mfc-application-wizard"></a>Birleşik Belge Desteği, MFC Uygulama Sihirbazı

MFC Uygulama Sihirbazı bu sayfada, hangi düzeye bileşik ve etkin belge desteği uygulamanızın sağladığı gösterir. Uygulamanızı bileşik belgeleri ve belge şablonları desteklemek için belge/görünüm mimarisini desteklemelidir.

Varsayılan olarak, uygulamanın bileşik belge desteği içerir. Bu varsayılanı kabul ederseniz, uygulamanız etkin belgeler veya bileşik dosyalar desteklemez.

- **Birleşik belge desteği**

   Uygulamanızı kapsayıcı desteği, sunucu desteği veya her ikisi de görüntüleyip görüntülemeyeceğini belirler. Bu alan hakkında daha fazla bilgi için bkz:

   - [Kapsayıcılar: Bir Kapsayıcı Uygulama](../../mfc/containers-implementing-a-container.md)

   - [Sunucular: Sunucu Uygulama](../../mfc/servers-implementing-a-server.md)

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Yok**|Nesne Bağlama ve Katıştırma (OLE) desteği gösterir. Varsayılan olarak, Uygulama Sihirbazı'nı ActiveX desteği olmayan bir uygulama oluşturur.|
   |**Kapsayıcı**|Bağlantılı veya katıştırılmış nesneleri içerir.|
   |**Mini sunucu**|Uygulama oluşturabilir ve yönetebilirsiniz bileşik belge nesneleri gösterir. Mini sunucuların çalıştıramazsınız Not, tek başına duramaz ve yalnızca katıştırılmış öğeleri destekler.|
   |**Tam sunucu**|Uygulama oluşturabilir ve yönetebilirsiniz bileşik belge nesneleri gösterir. Tüm sunucuları tek başına ve hem bağlantılı hem de katıştırılmış öğeleri destek çalıştırabilir.|
   |**Kapsayıcı/tam sunucu**|Uygulama bir kapsayıcı hem bir sunucu uygulanıp uygulanamayacağını gösterir. Uygulamanın kendi belgelerine gömülü veya bağlantılı öğeleri içeren bir kapsayıcıdır. Bir sunucu kapsayıcı uygulamalar tarafından kullanım için Otomasyon öğeleri oluşturan bir uygulamadır.|

- **Ek Seçenekler**

   Uygulamanız etkin belgeler destekleyip desteklemediğini belirtir. Bkz: [etkin belgeler](../../mfc/active-documents.md) bu özellik hakkında daha fazla bilgi.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Etkin belge sunucusu**|Uygulama oluşturma ve yönetme etkin belgeler gösterir. Bu seçeneği belirlerseniz, etkin belgeyi sunucunuz için bir dosya uzantısı belirtmelisiniz **dosya uzantısı** kutusunda [belge şablonu dizeleri](../../mfc/reference/document-template-strings-mfc-application-wizard.md) Sihirbazı sayfası. Bkz: [etkin belge sunucuları](../../mfc/active-document-servers.md) daha fazla bilgi için.|
   |**Etkin belge kapsayıcısı**|Uygulamanın kendi çerçevesi içindeki etkin belgeler içerebilir gösterir. Etkin belgeler, örneğin, Internet Explorer belge veya Microsoft Word dosyaları ya da Excel elektronik Office belgeleri içerebilir. Bkz: [etkin belge kapsaması](../../mfc/active-document-containment.md) daha fazla bilgi için.|
   |**Bileşik dosyalar için destek**|Bileşik dosya biçimini kullanarak kapsayıcı uygulamasının belgeleri serileştirilecek değil. Bu seçenek belleğe nesnelerini içeren bütün dosyasını yüklenmesini zorlar. Tek tek nesneler için artımlı kaydeder kullanılabilir değil. Bir nesne değiştirilir ve daha sonra kaydedilmiş dosyasındaki tüm nesneler kaydedilir.|

## <a name="see-also"></a>Ayrıca Bkz.

[MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)

