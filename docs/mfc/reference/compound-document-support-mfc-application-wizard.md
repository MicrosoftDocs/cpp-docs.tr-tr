---
description: 'Daha fazla bilgi edinin: bileşik belge desteği, MFC Uygulama Sihirbazı'
title: Birleşik Belge Desteği, MFC Uygulama Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.compdoc
ms.assetid: 42e1af83-12c4-438d-92eb-13835afdb148
ms.openlocfilehash: 5ccd95812c7b8a4379528b4c784a3d7ca09f538f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331368"
---
# <a name="compound-document-support-mfc-application-wizard"></a>Birleşik Belge Desteği, MFC Uygulama Sihirbazı

MFC Uygulama Sihirbazı 'nın bu sayfasında, uygulamanızın bileşik ve etkin belge desteğini hangi düzeye sağladığını belirtin. Uygulamanız, bileşik belge ve belge şablonlarını desteklemek için belge/görünüm mimarisini desteklemelidir.

Varsayılan olarak, uygulama hiçbir bileşik belge desteği içermez. Bu varsayılanı kabul ediyorsanız, uygulamanız etkin belgeleri veya bileşik dosyaları desteklemez.

- **Birleşik belge desteği**

  Uygulamanızın kapsayıcı desteğini, sunucu desteğini veya her ikisini de sağladığını belirler. Bu alan hakkında daha fazla bilgi için bkz.

  - [Kapsayıcılar: kapsayıcı uygulama](../../mfc/containers-implementing-a-container.md)

  - [Sunucular: sunucu uygulama](../../mfc/servers-implementing-a-server.md)

  |Seçenek|Açıklama|
  |------------|-----------------|
  |**Hiçbiri**|Nesne bağlama ve Katıştırma (OLE) için destek bulunmadığını gösterir. Varsayılan olarak, uygulama Sihirbazı ActiveX desteği olmayan bir uygulama oluşturur.|
  |**Kapsayıcı**|Bağlı ve katıştırılmış nesneleri içerir.|
  |**Mini sunucu**|Uygulamanın bileşik belge nesneleri oluşturup yönetebileceğini belirtir. Mini sunucuların tek başına çalıştırılmadığını ve yalnızca katıştırılmış öğeleri desteklediğini unutmayın.|
  |**Tam sunucu**|Uygulamanın bileşik belge nesneleri oluşturup yönetebileceğini belirtir. Tam sunucular tek başına çalıştırabilir ve hem bağlantılı hem de katıştırılmış öğeleri destekleyebilir.|
  |**Kapsayıcı/tam sunucu**|Uygulamanın hem kapsayıcı hem de sunucu olduğunu gösterir. Kapsayıcı, katıştırılmış veya bağlantılı öğeleri kendi belgelerine birleştiresağlayan bir uygulamadır. Sunucu, kapsayıcı uygulamaları tarafından kullanılmak üzere Otomasyon öğeleri oluşturabileceğiniz bir uygulamadır.|

- **Ek seçenekler**

  Uygulamanızın etkin belgeleri destekleyip desteklemediğini gösterir. Bu özellik hakkında daha fazla bilgi için bkz. [etkin belgeler](../../mfc/active-documents.md) .

  |Seçenek|Açıklama|
  |------------|-----------------|
  |**Etkin belge sunucusu**|Uygulamanın etkin belgeler oluşturup yönetebileceğini belirtir. Bu seçeneği belirlerseniz, sihirbazın [belge şablonu dizeleri](../../mfc/reference/document-template-strings-mfc-application-wizard.md) sayfasındaki **Dosya Uzantısı** kutusunda etkin belge sunucunuz için bir dosya uzantısı belirtmeniz gerekir. Daha fazla bilgi için bkz. [etkin belge sunucuları](../../mfc/active-document-servers.md) .|
  |**Etkin belge kapsayıcısı**|Uygulamanın, çerçevesinin içinde etkin belgeler içerebileceğini gösterir. Etkin belgeler, örneğin Internet Explorer belgeleri veya Microsoft Word dosyaları ya da Excel elektronik tabloları gibi Office belgeleri dahil olabilir. Daha fazla bilgi için bkz. [etkin belge kapsamı](../../mfc/active-document-containment.md) .|
  |**Bileşik dosyalar için destek**|, Bileşik dosya biçimi kullanılarak kapsayıcı uygulamanın belgelerini serileştirmez. Bu seçenek, nesneleri içeren bir dosyanın tamamını belleğe yüklemeye zorlar. Tek tek nesnelere artımlı kaydetme yok. Bir nesne değiştirilirse ve daha sonra kaydedilmişse, dosyadaki tüm nesneler kaydedilir.|

## <a name="see-also"></a>Ayrıca bkz.

[MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)
