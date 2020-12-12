---
description: 'Daha fazla bilgi edinin: belge şablonu dizeleri, MFC Uygulama Sihirbazı'
title: Belge Şablonu Dizeleri, MFC Uygulama Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.doctemp
helpviewer_keywords:
- MFC Application Wizard, document template strings
ms.assetid: 8109f662-3182-4682-977a-2503321c678a
ms.openlocfilehash: 839626915b5e60dd47182dd42f1182a092f0b3ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219921"
---
# <a name="document-template-strings-mfc-application-wizard"></a>Belge Şablonu Dizeleri, MFC Uygulama Sihirbazı

MFC Uygulama Sihirbazı 'nın bu sayfasında belge yönetimi ve Yerelleştirmede yardımcı olması için aşağıdaki seçenekleri sağlayın veya daraltın. Belge şablonu dizeleri, [uygulama türünde](../../mfc/reference/application-type-mfc-application-wizard.md) **belge/görünüm mimarisi desteğini** içeren uygulamalar için kullanılabilir. İletişim kutuları için kullanılamaz. Çoğu belge şablonu dizesi görünür ve uygulamanın kullanıcıları tarafından kullanıldığından, sihirbazın **uygulama türü** sayfasında belirtilen **kaynak diline** yerelleştirilir.

- **Yerelleştirilen olmayan dizeler**

   Kullanıcı belgeleri oluşturan uygulamalar için geçerlidir. Bir dosya uzantısı ve dosya türü KIMLIĞI sağlarsanız, kullanıcılar belgelerinizi daha kolay bir şekilde açabilir, yazdırabilir ve kaydedebilir. Bu öğeler, Kullanıcı tarafından değil, sistem tarafından kullanıldıkları için yerelleştirilmez.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Dosya Uzantısı**|Uygulamayı kullanırken kullanıcının kaydettiği belgelerle ilişkili dosya uzantısını ayarlar. Örneğin, projeniz pencere öğesi olarak adlandırılmışsa, dosya uzantısını. wgt olarak adlandırın. (Dosya uzantısını girerken, dönemi eklemeyin.)<br /><br /> Bir dosya uzantısı sağlarsanız, Kullanıcı bir yazıcı simgesinde belge simgesini bırakıdüğünde, uygulamanız uygulamanızı başlatmadan uygulamanızın belgelerini yazdırabilir.<br /><br /> Uzantı belirtmezseniz, kullanıcının dosyaları kaydederken bir dosya uzantısı belirtmesi gerekir. Sihirbaz varsayılan bir dosya uzantısı sağlamıyor.|
   |**Dosya türü KIMLIĞI**|Belge türünün etiketini sistem kayıt defterinde ayarlar.|

- **Yerelleştirilmiş dizeler**

   Uygulamanın kullanıcıları tarafından okunan ve kullanılan belge ve belgeyle ilişkili dizeleri üretir, bu nedenle dizeler yerelleştirilir.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Dil**|**Yerelleştirilmiş dizeler** altındaki tüm kutular için dizelerin gösterileceği dili gösterir. Bu kutudaki değeri değiştirmek için, MFC Uygulama Sihirbazı 'nın [uygulama türü](../../mfc/reference/application-type-mfc-application-wizard.md) sayfasında **Kaynak dili** altında uygun dili seçin.|
   |**Ana çerçeve başlığı**|Ana uygulama çerçevesinin üst kısmında görünen metni ayarlar. Varsayılan olarak, proje adı.|
   |**Belge türü adı**|Uygulamanın bir belgesinin gruplandırılabileceği belge türünü tanımlar. Varsayılan olarak, proje adı. Varsayılan değer değiştirildiğinde, bu iletişim kutusunda başka herhangi bir seçenek değişmez.|
   |**Filtre adı**|Kullanıcılarınızın dosya türü dosyalarını bulmak için belirte, adını belirler. Bu seçenek, standart Windows **Aç** ve farklı **Kaydet** iletişim kutularında **tür dosyaları** ve **farklı kaydet** seçenekleri arasından kullanılabilir. Varsayılan olarak, proje adı ve dosyaları, ardından **Dosya uzantısında** sağlanmış olan uzantısı izler. Örneğin, projeniz pencere öğesi olarak adlandırılmışsa ve dosya uzantısı. wgt ise, **filtre adı** varsayılan olarak pencere öğesi dosyaları (*. wgt) olur.|
   |**Dosya yeni kısa adı**|Birden çok yeni belge şablonu varsa, standart Windows **Yeni** iletişim kutusunda görünen adı ayarlar. Uygulamanız bir [Otomasyon sunucusu](../../mfc/automation-servers.md)ise, bu ad Otomasyon nesnenizin kısa adı olarak kullanılır. Varsayılan olarak, proje adı.|
   |**Dosya türü uzun adı**|Dosya türü adını sistem kayıt defterinde ayarlar. Uygulamanız bir Otomasyon sunucusu ise, bu ad Otomasyon nesnenizin uzun adı olarak kullanılır. Varsayılan olarak, proje adı artı. Belgedeki.|

## <a name="see-also"></a>Ayrıca bkz.

[MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)
