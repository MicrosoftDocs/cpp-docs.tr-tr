---
title: Belge Şablonu Dizeleri, MFC Sınıf Ekleme Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.mfc.simple.doctemp
helpviewer_keywords:
- MFC Add Class Wizard, document control strings
ms.assetid: 14e1c834-5e79-4dbd-811f-ec8f0a9cdcb2
ms.openlocfilehash: de0b483b6b3d242ee05680c47ae29ed675d54a36
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62322431"
---
# <a name="document-template-strings-mfc-add-class-wizard"></a>Belge Şablonu Dizeleri, MFC Sınıf Ekleme Sihirbazı

Sihirbazın bu sayfası yalnızca aşağıdaki ölçütleri karşılayan sınıflar için kullanılabilir:

- MFC projesinin belge/görünüm mimarisinin destekler.

- Yeni sınıfın temel sınıf [CFormView](../../mfc/reference/cformview-class.md).

- Onay kutusunu **oluşturmak DocTemplate kaynakları** üzerinde teslim edildi **adları** bölümünü [MFC Sınıf Sihirbazı](../../mfc/reference/mfc-add-class-wizard.md).

Sihirbaz, Form görünümü tasarımı, yönetim ve yerelleştirme ile yardımcı olması aşağıdaki değerleri için varsayılan değerleri sağlar. Çoğu belge şablonu dizeleri, görünür ve form denetiminin kullanıcı tarafından kullanılan olduğundan, bunlar içine yerelleştirilmiş olduğunu **kaynak dili** belirtilen [uygulama türleri](../../mfc/reference/application-type-mfc-application-wizard.md) MFC Uygulama Sihirbazı sayfası Projenin oluşturulduğu zaman.

> [!NOTE]
>  Türetilmiş sınıflar için sihirbaz otomatik yazdırma desteği sağlamaz `CFormView`.

Bkz: [belge şablonları ve belge/görünüm oluşturma işlemi](../../mfc/document-templates-and-the-document-view-creation-process.md) daha fazla bilgi için.

## <a name="nonlocalized-strings"></a>Yerelleştirilmemiş dizeleri

Kullanıcı belgeleri oluşturma ve uygulamaları için geçerlidir. Kullanıcılar açabilir ve belge türü bir dosya uzantısı ve dosya türü kimliği varsa belgeleri daha kolayca kaydedin Sistemi yerine kullanıcı tarafından kullanıldığı için bu öğeleri yerelleştirilmedi.

- **Dosya uzantısı**

   Bu form uygulama için belge türü ile ilişkili dosya uzantısı belirler. Dosya uzantısı varsayılan sınıf adını temel alarak. Örneğin, yeni MFC sınıfı adlandırılmışsa `CWidget`, varsayılan olarak, dosya uzantısıdır. WID Dosya uzantısı dosya filtreleri kullanılır ve **açık** ve **Kaydet** iletişim kutuları.

   Dosya uzantısı değiştirirseniz, değişikliğin yansıtılır **filtre adı** kutusu.

   > [!NOTE]
   > Varsayılan dosya uzantısını değiştirirseniz, süre dahil değildir.

- **Dosya türü kimliği**

   Etiket, belge türü için sistem kayıt defterinde ayarlar.

## <a name="localized-strings"></a>Yerelleştirilmiş dizeleri

Formlar ve okuma ve uygulamanın kullanıcı tarafından kullanılan dizelerin yerelleştirilmiş belgelerin ilişkili dizeleri üretir.

- **Belge türü adı**

   Bir belge uygulamasının altında gruplandırılabilir belge türünü tanımlar. Varsayılan olarak, sınıfın adını temel alır. Örneğin, yeni MFC sınıfı adlandırılmışsa **CWidget**, varsayılan olarak, belge türü pencere öğesi adıdır. Varsayılan değiştirilmesi, bu iletişim kutusunda diğer seçenekleri değiştirmez.

- **Filtre adı**

   Belirtilen dosya türlerinin bulmak için kullanıcıları belirtebilir adını ayarlar. Bu seçenek kullanılabilir **dosya türü** ve **farklı kaydetme türü** standart Windows seçeneklerinde **açık** ve **Kaydet** iletişim kutuları. Varsayılan olarak, ad proje adına dayalı yanı sıra dosya, uzantısı tarafından izlenen gösterilir **dosya uzantısı**. Örneğin, projeniz pencere öğesi olarak adlandırılır ve .wid, dosya uzantısı ise **filtre adı** pencere öğesi dosyaları (*.wid) varsayılan olarak açıktır.

- **Dosya yeni kısa adı**

   Standart Windows içinde görünen adını ayarlar **yeni** iletişim kutusunda, projeyi birden çok belge şablonu varsa. Uygulamanız bir [Otomasyon sunucusu](../../mfc/automation-servers.md), bu ad, Otomasyon nesnesi kısa adı olarak kullanılır. Varsayılan olarak, bu ad sınıf adına göre temel alır.

- **Dosya türü uzun adı**

   Dosya türü adı, sistem kayıt defterinde ayarlar. Uygulamanız Otomasyon sunucusu ise, bu ad, Otomasyon nesnesi uzun adı olarak kullanılır. Varsayılan olarak, bu ad, sınıf adı artı temel alır. Belge. Örneğin, sınıf adı ise `CWidget`, **dosya türü uzun adı** pencere öğesi belgesi.

- **Belge sınıfı**

   Projenin belge sınıfı gösterir. Varsayılan olarak, bu sınıf ana uygulamanın belge sınıfı bağlantısında listelendiği gibi [gözden geçirme oluşturulan sınıflar](../../mfc/reference/generated-classes-mfc-application-wizard.md) MFC Uygulama Sihirbazı sayfası. Projede diğer belge sınıfları eklediyseniz başka bir belge sınıfı listeden seçebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Sınıf Ekleme Sihirbazı](../../mfc/reference/mfc-add-class-wizard.md)<br/>
[MFC sınıfı](../../mfc/reference/adding-an-mfc-class.md)<br/>
[Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)
