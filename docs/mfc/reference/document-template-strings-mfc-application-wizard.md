---
title: Belge şablonu dizeleri, MFC Uygulama Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfc.exe.doctemp
dev_langs:
- C++
helpviewer_keywords:
- MFC Application Wizard, document template strings
ms.assetid: 8109f662-3182-4682-977a-2503321c678a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a2b1e30ac1e4381cdcd80eddd7fdd4ea27bde5a4
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700576"
---
# <a name="document-template-strings-mfc-application-wizard"></a>Belge Şablonu Dizeleri, MFC Uygulama Sihirbazı
Bu sayfada MFC Uygulama Sihirbazı sağlayın veya belge yönetimi ve yerelleştirme yardımcı olması için aşağıdaki seçeneklerden daraltın. Belge şablonu dizeleri içeren uygulamalar için kullanılabilir **belge/görünüm mimarisi desteği** içinde [uygulama türü](../../mfc/reference/application-type-mfc-application-wizard.md). İletişim kutuları için kullanılamaz. Çoğu belge şablonu dizeleri, görünür ve uygulamanın kullanıcılar tarafından kullanılan olduğundan, bunlar içine yerelleştirilmiş olduğunu **kaynak dili** belirtilen **uygulama türü** Sihirbazı sayfası.  
  
- **Yerelleştirilmemiş dizeleri**

   Kullanıcı belgeleri oluşturma ve uygulamaları için geçerlidir. Kullanıcılar açın, yazdırma ve bir dosya uzantısı ve dosya türü kimliği sağlarsanız belgeleri daha kolayca Kaydet Sistemi yerine kullanıcı tarafından kullanıldığı için bu öğeleri yerelleştirilmedi.  
  
   |Seçenek|Açıklama|  
   |------------|-----------------|  
   |**Dosya uzantısı**|Kullanıcı uygulamayı kullanırken kaydeder belgeleri ile ilişkili dosya uzantısı belirler. Örneğin, projeniz pencere öğesi ise, dosya uzantısı .wgt adlandırabilirsiniz. (Dosya uzantısı girdiğinizde dönem eklemeyin.)<br /><br /> Bir dosya uzantısı sağlarsanız, Gezgini kullanıcı bir yazıcı simgesini belge simgesi düştüğünde uygulamanızı çalıştırmak zorunda kalmadan, uygulamanızın belgeleri yazdırabilirsiniz.<br /><br /> Bir uzantı belirtmezseniz, bir kullanıcı bir dosya uzantısı dosyalarını kaydederken belirtmeniz gerekir. Sihirbaz, bir varsayılan dosya uzantısı sağlamaz.|  
   |**Dosya türü kimliği**|Etiket, belge türü için sistem kayıt defterinde ayarlar.|  
  
- **Yerelleştirilmiş dizeleri**

   Okuma ve uygulamanın kullanıcı tarafından kullanılan dizelerin yerelleştirilmiş belge ve uygulama ile ilişkilendirilmiş dizeleri üretir.  
  
   |Seçenek|Açıklama|  
   |------------|-----------------|  
   |**Dil**|Dizeleri görüntülendiği altındaki tüm kutuları için dil belirten **yerelleştirilmiş dizeleri**. Bu kutudaki değeri değiştirmek için uygun dil altında seçin **kaynak dili** içinde [uygulama türü](../../mfc/reference/application-type-mfc-application-wizard.md) MFC Uygulama Sihirbazı sayfası.|  
   |**Ana çerçeve resim yazısı**|Ana uygulama çerçevesinin üstte görüntülenecek metni ayarlar. Varsayılan olarak, proje adı.|  
   |**Belge türü adı**|Bir belge uygulamasının altında gruplandırılabilir belge türünü tanımlar. Varsayılan olarak, proje adı. Varsayılan değiştirilmesi, bu iletişim kutusunda diğer seçenekleri değiştirmez.|  
   |**Filtre adı**|Dosya türünüze dosyaları bulmak için kullanıcılarınızın belirtebilir adını ayarlar. Bu seçenek kullanılabilir **dosya türü** ve **farklı kaydetme türü** standart Windows seçeneklerinde **açık** ve **Kaydet** iletişim kutuları. Sağlanan uzantı varsayılan, proje adı yanı sıra dosyaları tarafından ardından **dosya uzantısı**. Örneğin, projeniz pencere öğesi olarak adlandırılır ve .wgt, dosya uzantısı ise **filtre adı** pencere öğesi dosyaları (*.wgt) varsayılan olarak açıktır.|  
   |**Dosya yeni kısa adı**|Standart Windows içinde görünen adını ayarlar **yeni** iletişim kutusunda, yeni bir belge şablonu birden fazla ise. Uygulamanız bir [Otomasyon sunucusu](../../mfc/automation-servers.md), bu ad, Otomasyon nesnesi kısa adı olarak kullanılır. Varsayılan olarak, proje adı.|  
   |**Dosya türü uzun adı**|Dosya türü adı, sistem kayıt defterinde ayarlar. Uygulamanız Otomasyon sunucusu ise, bu ad, Otomasyon nesnesi uzun adı olarak kullanılır. Varsayılan olarak, artı proje adı. Belge.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)

