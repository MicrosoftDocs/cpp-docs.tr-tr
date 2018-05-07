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
ms.openlocfilehash: 7d6039459eed097af5e927c4bd2f30d3e7c3c4bc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="document-template-strings-mfc-application-wizard"></a>Belge Şablonu Dizeleri, MFC Uygulama Sihirbazı
MFC Uygulama Sihirbazı'nın bu sayfasında, sağlayın veya belge yönetimi ve yerelleştirme yardımcı olması için aşağıdaki seçeneklerden daraltın. Belge şablonu dizeleri içeren uygulamalar için kullanılabilir **belge/görünüm mimarisi desteği** içinde [uygulama türü](../../mfc/reference/application-type-mfc-application-wizard.md). İletişim kutuları için kullanılamaz. Çoğu belge şablonu dizeleri görünür ve uygulamanın kullanıcılar tarafından kullanılan olduğundan, bunlar içine yerelleştirilmiştir **kaynak dili** belirtilen **uygulama türü** Sihirbazı sayfası.  
  
 **Yerelleştirilmemiş dizeleri**  
 Kullanıcı belgeleri oluşturmak uygulamalar için geçerlidir. Kullanıcılar açabilir, yazdırma ve bir dosya uzantısı ile bir dosya türü kimliği sağlarsanız, belgeleri daha kolayca kaydetme Sistemi yerine kullanıcı tarafından kullanıldığı için bu öğeler yerelleştirilmiş değil.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Dosya uzantısı**|Kullanıcı uygulamayı kullanırken kaydeder belgeleri ile ilişkili dosya uzantısı ayarlar. Örneğin, projenizin pencere öğesi olarak adlandırılmışsa, dosya uzantısı .wgt adlandırabilirsiniz. (Dosya uzantısı girdiğinizde, dönem eklemeyin.)<br /><br /> Bir dosya uzantısı sağlarsanız, Explorer kullanıcı bir yazıcı simgesine belge simgesi düştüğünde uygulamanızı başlatmadan uygulamanızın belgeleri yazdırabilirsiniz.<br /><br /> Uzantı belirtmezseniz, bir kullanıcının bir dosya uzantısı dosyaları kaydederken belirtmeniz gerekir. Sihirbaz, bir varsayılan dosya uzantısı sağlamaz.|  
|**Dosya türü kimliği**|Etiket belge türü için sistem kayıt defterinde ayarlar.|  
  
 **Yerelleştirilmiş dizeleri**  
 Dizeleri okuma ve dizeleri yerelleştirilmiş uygulamanın kullanıcılar tarafından kullanılan belge ve uygulama ile ilişkili üretir.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Dil**|Dizeleri görüntüleneceği altındaki tüm kutuları için dili gösterir **dizeleri yerelleştirilmiş**. Bu kutudaki değer değiştirmek için uygun dili altında seçin **kaynak dili** içinde [uygulama türü](../../mfc/reference/application-type-mfc-application-wizard.md) MFC Uygulama Sihirbazı sayfası.|  
|**Ana çerçeve açıklamalı alt yazı**|Ana uygulama çerçevesi üst kısmında görünen metin ayarlar. Varsayılan olarak, proje adı.|  
|**Belge türü adı**|Bir belge uygulamasının altında gruplandırılabilir belge türünü tanımlar. Varsayılan olarak, proje adı. Varsayılan değiştirme bu iletişim kutusundaki diğer seçenekler değiştirmez.|  
|**Filtre adı**|Dosya, dosya türü bulmak için kullanıcılarınızın belirtebilir adını ayarlar. Bu seçenek kullanılabilir **dosya türü** ve **farklı türde Kaydet** standart Windows seçeneklerinde **açık** ve **Farklı Kaydet** iletişim kutuları. Varsayılan, proje adı artı dosyaları tarafından ve arkasından sağlanan uzantı **dosya uzantısı**. Örneğin, projenizin pencere öğesi olarak adlandırılır ve .wgt, dosya uzantısı ise **filtre adı** pencere öğesi dosyaları (*.wgt) varsayılan olarak açıktır.|  
|**Dosya yeni kısa ad**|Standart Windows görünen adını ayarlar `New` iletişim kutusunda, yeni birden çok belge şablonu ise. Uygulamanız ise bir [Otomasyon sunucusu](../../mfc/automation-servers.md), bu ad, Otomasyon nesnesi kısa adı olarak kullanılır. Varsayılan olarak, proje adı.|  
|**Dosya türü uzun adı**|Dosya türü adı Sistem kayıt defterinde ayarlar. Uygulamanız bir Otomasyon sunucusu ise, bu ad, Otomasyon nesnesi uzun adı olarak kullanılır. Varsayılan olarak, artı proje adı. Belge.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)

