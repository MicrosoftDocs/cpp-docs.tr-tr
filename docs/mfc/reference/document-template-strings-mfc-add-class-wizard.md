---
title: "Belge şablonu dizeleri, MFC sınıf Ekleme Sihirbazı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.class.mfc.simple.doctemp
dev_langs:
- C++
helpviewer_keywords:
- MFC Add Class Wizard, document control strings
ms.assetid: 14e1c834-5e79-4dbd-811f-ec8f0a9cdcb2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3a9d37b1a886c28d267cd7a387317edce6bf7f3a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="document-template-strings-mfc-add-class-wizard"></a>Belge Şablonu Dizeleri, MFC Sınıf Ekleme Sihirbazı
Sihirbazın bu sayfası yalnızca aşağıdaki ölçütleri toplantı sınıflar için kullanılabilir:  
  
-   MFC projesine belge/görünüm mimarisi destekler.  
  
-   Taban sınıf yeni sınıfın [Cformview'yu](../../mfc/reference/cformview-class.md).  
  
-   Onay kutusunu **oluşturmak DocTemplate kaynakları** üzerinde işaretli **adları** bölümünü [MFC Sınıf Sihirbazı](../../mfc/reference/mfc-add-class-wizard.md).  
  
 Sihirbaz Form görünümü tasarımı, yönetim ve yerelleştirme yardımcı olması için aşağıdaki değerleri için varsayılan ayarları sağlar. Çoğu belge şablonu dizeleri görünür ve formun kullanıcılar tarafından kullanılan olduğundan, bunlar içine yerelleştirilmiştir **kaynak dili** belirtilen [uygulama türleri](../../mfc/reference/application-type-mfc-application-wizard.md) MFC Uygulama Sihirbazı sayfası Proje oluşturulduğu.  
  
> [!NOTE]
>  Türetilmiş sınıflar için sihirbazın otomatik yazdırma destek sağlamaz `CFormView`.  
  
 Bkz: [belge şablonları ve belge/görünüm oluşturma işlemi](../../mfc/document-templates-and-the-document-view-creation-process.md) daha fazla bilgi için.  
  
## <a name="nonlocalized-strings"></a>Yerelleştirilmemiş dizeleri  
 Kullanıcı belgeleri oluşturmak uygulamalar için geçerlidir. Kullanıcılar açabilir ve belge türü bir dosya uzantısı ile bir dosya türü kimliği varsa belgeleri daha kolayca kaydetme Sistemi yerine kullanıcı tarafından kullanıldığı için bu öğeler yerelleştirilmiş değil.  
  
 **Dosya uzantısı**  
 Bu form uygulama için belge türüyle ilişkili dosya uzantısı ayarlar. Dosya uzantısı varsayılan sınıf adını temel alarak. Örneğin, yeni MFC sınıfı adlı **CWidget**, varsayılan olarak, dosya uzantısıdır. WID Dosya uzantısı dosya filtreleri kullanılır ve **açık** ve **Farklı Kaydet** iletişim kutuları.  
  
 Dosya uzantısını değiştirirseniz, değişikliğin yansıtılmıştır **filtre adı** kutusu.  
  
> [!NOTE]
>  Varsayılan dosya uzantısını değiştirirseniz, dönem dahil etmeyin.  
  
 **Dosya türü kimliği**  
 Etiket belge türü için sistem kayıt defterinde ayarlar.  
  
## <a name="localized-strings"></a>Yerelleştirilmiş dizeleri  
 Formlar ve okuma ve dizeleri yerelleştirilmiş uygulamanın kullanıcılar tarafından kullanılan belgeler ilişkili dizeleri üretir.  
  
 **Belge türü adı**  
 Bir belge uygulamasının altında gruplandırılabilir belge türünü tanımlar. Varsayılan olarak, bu sınıfın adını temel alır. Örneğin, yeni MFC sınıfı adlı **CWidget**, varsayılan olarak, belge türü pencere öğesi adıdır. Varsayılan değiştirme bu iletişim kutusundaki diğer seçenekler değiştirmez.  
  
 **Filtre adı**  
 Belirtilen dosya türlerinin bulmak için kullanıcıların belirtebilir adını ayarlar. Bu seçenek kullanılabilir **dosya türü** ve **farklı türde Kaydet** standart Windows seçeneklerinde **açık** ve **Farklı Kaydet** iletişim kutuları. Varsayılan olarak, ad proje adına göre temel alır ve uzantısı tarafından izlenen dosyaları, belirtilen **dosya uzantısı**. Örneğin, projenizin pencere öğesi olarak adlandırılır ve .wid, dosya uzantısı ise **filtre adı** pencere öğesi dosyaları (*.wid) varsayılan olarak açıktır.  
  
 **Dosya yeni kısa ad**  
 Standart Windows görünen adını ayarlar `New` iletişim kutusu, projenin birden çok belge şablonu varsa. Uygulamanız ise bir [Otomasyon sunucusu](../../mfc/automation-servers.md), bu ad, Otomasyon nesnesi kısa adı olarak kullanılır. Varsayılan olarak, bu ad sınıf adını temel alır.  
  
 **Dosya türü uzun adı**  
 Dosya türü adı Sistem kayıt defterinde ayarlar. Uygulamanız bir Otomasyon sunucusu ise, bu ad, Otomasyon nesnesi uzun adı olarak kullanılır. Varsayılan olarak, bu ad, sınıf adı artı temel alır. Belge. Örneğin, sınıf adı ise **CWidget**, **dosya türü uzun adı** pencere öğesi belgedir.  
  
 **Belge sınıfı**  
 Projenin belge sınıfı gösterir. Varsayılan olarak, bu sınıfı ana uygulamanın belge, içinde listelenen sınıftır [gözden geçirme oluşturulan sınıflar](../../mfc/reference/generated-classes-mfc-application-wizard.md) MFC Uygulama Sihirbazı sayfası. Diğer belge sınıfları projede eklediyseniz başka bir belge sınıfı listeden seçebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC sınıf Ekleme Sihirbazı](../../mfc/reference/mfc-add-class-wizard.md)   
 [MFC sınıfı](../../mfc/reference/adding-an-mfc-class.md)   
 [Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)
