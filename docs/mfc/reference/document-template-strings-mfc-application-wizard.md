---
title: Belge Şablonu Dizeleri, MFC Uygulama Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.doctemp
helpviewer_keywords:
- MFC Application Wizard, document template strings
ms.assetid: 8109f662-3182-4682-977a-2503321c678a
ms.openlocfilehash: 563cdf51c8104035fe29cb2e11d6c2bc8155d97b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62322481"
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

## <a name="see-also"></a>Ayrıca bkz.

[MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)
